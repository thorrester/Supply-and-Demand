# Variety of plots for supply and demand using Matplotlib

import matplotlib.pyplot as plt
%matplotlib inline
import pandas as pd
import numpy as np
import seaborn as sn
import random as rn

#Normal Market

demand1 = np.arange(1000, 100, -100) #x
price1 = np.arange(10, 100, 10) #y


supply = np.arange(100, 1000, 100)
price_supply = np.arange(10, 100, 10)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))


plt.plot(demand1, price1, 'red', supply, price_supply, 'dodgerblue', linewidth=5.0)
plt.plot([0, 570], [55, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([560, 560], [0, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)

plt.annotate('Demand', xy=(1020,10))
plt.annotate('Supply', xy=(910,90))
plt.annotate('EQ', xy=(580,54))

plt.xlabel('Quantity (# of rides)')
plt.ylabel('Price (per ride)')
plt.title('Market Rides')



plt.axis((0, 1200, 0, 100))

plt.show
plt.savefig('Market_Rides.png', dpi=600)

# Shifting demand with a price cieling

demand1 = np.arange(1000, 200, -125) #x
price1 = np.arange(450, 1150, 100) #y

demand2 = np.arange(1500, 700, -125) #x
price2 = np.arange(450, 1150, 100) #y

supply = np.arange(200, 1000, 125)
price_supply = np.arange(450, 1150, 100)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))

plt.plot(demand1, price1, 'red', demand2, price2, 'red', supply, price_supply, 'dodgerblue', linewidth=5.0)
plt.plot([0, 600], [770, 770], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([600, 600], [0, 770], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 850], [970, 970], color = 'grey', linestyle = 'dashed',linewidth = 2)
plt.plot([850, 850], [0, 970], color = 'grey', linestyle = 'dashed',linewidth = 2)
plt.plot([0, 1200], [900, 900], color = 'black',linewidth = 2)

plt.annotate('D0', xy=(1020,450))
plt.annotate('D1', xy=(1520,450))
plt.annotate('Price Ceiling', xy=(1220,895))
plt.annotate('Supply', xy=(960,1050))
plt.annotate('EQ1', xy=(630,760))
plt.annotate('EQ2', xy=(890,960))


plt.axis((0, 1600, 400, 1100))

plt.show

# With Strike
demand1 = np.arange(1000, 100, -100) #x
price1 = np.arange(10, 100, 10) #y


supply = np.arange(100, 1000, 100)
price_supply = np.arange(10, 100, 10)

supply2 = np.arange(100, 1000, 100)
price_supply2 = np.arange(30, 120, 10)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))

t = ('A strike would create a left shift \n in the supply line, as there would \n be a reduced quantity of available \ntaxis.'
      '\n\n The equilibrium would shift left \n to EQ1, and price and quantity \n would shift to P1 and Q1, \n respectively.' )

plt.plot(demand1, price1, 'red', supply, price_supply, 'dodgerblue', supply2, price_supply2, 'dodgerblue', linewidth=5.0)
plt.plot([0, 570], [55, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([560, 560], [0, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([450, 450], [0, 64], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 450], [64, 64], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.text(900, 40, t, ha='left', wrap=True)


plt.annotate('Demand 0', xy=(1020,10))
plt.annotate('Supply 0', xy=(910,90))
plt.annotate('Supply 1', xy=(590,95))
plt.annotate('EQ0', xy=(580,54))
plt.annotate('EQ1', xy=(490,64))
plt.annotate('P0', xy=(5,56))
plt.annotate('P1', xy=(5,65))
plt.annotate('Q0', xy=(580,1))
plt.annotate('Q1', xy=(455,1))


plt.xlabel('Quantity (# of rides)')
plt.ylabel('Price (per ride)')
plt.title('Market Rides (With Strike)')



plt.axis((0, 1500, 0, 100))

plt.show
plt.savefig('Market_Rides(Strike).png', dpi=600)

#Price Cieling
demand1 = np.arange(1000, 100, -100) #x
price1 = np.arange(10, 100, 10) #y


supply = np.arange(100, 1000, 100)
price_supply = np.arange(10, 100, 10)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))



plt.plot(demand1, price1, 'red', supply, price_supply, 'dodgerblue', linewidth=5.0)
plt.plot([0, 570], [55, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([560, 560], [0, 55], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([450, 450], [0, 45], color = 'blACK', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 1000], [45, 45], color = 'blACK', linewidth = 2)
plt.plot([655, 655], [0, 45], color = 'blACK', linestyle = 'dashed', linewidth = 2)
plt.plot([450, 655], [20, 20], color = 'blACK', linewidth = 2)


plt.annotate('Demand', xy=(1020,10))
plt.annotate('Supply', xy=(910,90))
plt.annotate('EQ (with 25% price increase)', xy=(580,54))
plt.annotate('18% Price ceiling', xy=(910,40))
plt.annotate('QS', xy=(460,41))
plt.annotate('QD', xy=(600,41))
plt.annotate('Shortage', xy=(500,20), xytext=(300,10),
            arrowprops={'arrowstyle': '-|>'}, va='center')

plt.xlabel('Quantity (# of rides)')
plt.ylabel('Price (per ride)')
plt.title('Market Rides (with Price Ceiling)')



plt.axis((0, 1200, 0, 100))

plt.show
plt.savefig('Market_Rides(Ceiling).png', dpi=600)

# Licenses with initial quota

demand1 = np.arange(3600, 0, -400) #x
price1 = np.arange(20, 200, 20) #y


supply = np.arange(400, 4000, 400)
price_supply = np.arange(20, 200, 20)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))


plt.plot(demand1, price1, 'red', supply, price_supply, 'dodgerblue', linewidth=5.0)
plt.plot([0, 2000], [100, 100], color = 'grey', linestyle = 'dashed', linewidth = 1.5)
plt.plot([2000, 2000], [0, 100], color = 'grey', linestyle = 'dashed', linewidth = 1.5)

plt.plot([750, 750], [40, 200], color = 'dodgerblue', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 750], [160, 160], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 750], [40, 40], color = 'grey', linestyle = 'dashed', linewidth = 2)



plt.annotate('Demand', xy=(3520,10))
plt.annotate('Supply', xy=(3520,170))
plt.annotate('Supply \nQuota 0', xy=(770,180))

plt.annotate('EQ', xy=(2080,98))
plt.annotate('QS0', xy=(750,33))

plt.annotate('QD0', xy=(800,160))


plt.xlabel('Quantity (# of licenses)')
plt.ylabel('Price (per license)')
plt.title('Taxi Licenses')
plt.annotate('Quota Wedge', xy=(250,40), xytext=(500,10),
            arrowprops={'arrowstyle': '-|>'}, va='center')


plt.axis((0, 4000, 0, 200))

plt.show
plt.savefig('Taxi_License(original).png', dpi=600)

# Licenses with new quota

demand1 = np.arange(3600, 0, -400) #x
price1 = np.arange(20, 200, 20) #y


supply = np.arange(400, 4000, 400)
price_supply = np.arange(20, 200, 20)

x1 = [0, 800]
y1 = [800, 800]

plt.figure(figsize=(8, 6))


plt.plot(demand1, price1, 'red', supply, price_supply, 'dodgerblue', linewidth=5.0)
plt.plot([0, 2000], [100, 100], color = 'grey', linestyle = 'dashed', linewidth = 1.5)
plt.plot([2000, 2000], [0, 100], color = 'grey', linestyle = 'dashed', linewidth = 1.5)

plt.plot([750, 750], [40, 200], color = 'dodgerblue', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 750], [160, 160], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 750], [40, 40], color = 'grey', linestyle = 'dashed', linewidth = 2)
plt.plot([1500, 1500], [75, 200], color = 'dodgerblue', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 1500], [75, 75], color = 'black', linestyle = 'dashed', linewidth = 2)
plt.plot([0, 1500], [125, 125], color = 'black', linestyle = 'dashed', linewidth = 2)


plt.annotate('Demand', xy=(3520,10))
plt.annotate('Supply', xy=(3520,170))
plt.annotate('Supply \nQuota 0', xy=(770,180))
plt.annotate('Supply \nQuota 1', xy=(1520,180))
plt.annotate('EQ', xy=(2080,98))
plt.annotate('QS0', xy=(750,33))
plt.annotate('QD1', xy=(1550,125))
plt.annotate('QD0', xy=(800,160))
plt.annotate('QS1', xy=(1520,72))

plt.xlabel('Quantity (# of licenses)')
plt.ylabel('Price (per license)')
plt.title('Taxi Licenses')
plt.annotate('Quota Wedge', xy=(250,40), xytext=(500,10),
            arrowprops={'arrowstyle': '-|>'}, va='center')


plt.axis((0, 4000, 0, 200))

plt.show
plt.savefig('Taxi_License.png', dpi=600)