import csv
import matplotlib.pyplot as plt
import statistics

//start with $10000, and split them evenly into the strategy account and the money-market account
strategy = 5000
bond = 5000
monthly_bond_return = 0.01495 / 12
returns = []
NAV = []

//This is unfinished. It depends on the output of back-testing
returns = []

//Every month the strategy account exceeds $10000, withdraw (strategy - 10000). Every month it falls below $5000, top up to $5000. 
for i in range(len(returns)):
    strategy *= (1 + float(returns[i])/100)
    bond *= (1+ monthly_bond_return)
    NAV.append(strategy + bond)
    if strategy < 5000:
        bond += strategy - 5000
        strategy = 5000
    elif strategy > 10000:
        bond += strategy - 10000
        strategy = 10000
    else:
        continue

//Calculate and plot
change = []
for i in range(len(returns)-1):
    change.append((NAV[i+1]-NAV[i])/NAV[i])
mean = sum(change) / len(change)
sd = statistics.stdev(change)
sharpe = (mean - monthly_bond_return) / sd

plt.plot(NAV)
plt.show()
print(NAV)
print(change)
print(mean)
print(sd)
print(sharpe)
