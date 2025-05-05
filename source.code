# AI-Stack
import matplotlib.pyplot as plt

class Stock:
    def _init_(self, name, price):
        self.name = name
        self.price = price

    def update_price(self):
        # Simulate stock price change
        change = random.uniform(-0.05, 0.05)  # Â±5% change
        self.price *= (1 + change)

class Portfolio:
    def _init_(self):
        self.holdings = {}
        self.cash = 10000  # Start with $10,000

    def buy_stock(self, stock, amount):
        cost = stock.price * amount
        if self.cash >= cost:
            self.cash -= cost
            if stock.name in self.holdings:
                self.holdings[stock.name] += amount
            else:
                self.holdings[stock.name] = amount
            print(f"Bought {amount} shares of {stock.name} at ${stock.price:.2f} each.")
        else:
        print("Not enough cash to buy the stock.")

    def sell_stock(self, stock, amount):
        if stock.name in self.holdings and self.holdings[stock.name] >= amount:
            revenue = stock.price * amount
            self.cash += revenue
            self.holdings[stock.name] -= amount
            print(f"Sold {amount} shares of {stock.name} at ${stock.price:.2f} each.")
        else:
            print("Not enough shares to sell.")

    def portfolio_value(self, stock_prices):
        value = self.cash
        for stock_name, amount in self.holdings.items():
            value += stock_prices[stock_name] * amount
        return value

def simulate_market():
    # Create a few stocks
    stocks = [Stock("AAPL", 150), Stock("GOOG", 2800), Stock("TSLA", 700)]
    stock_prices = {stock.name: stock.price for stock in stocks}

    portfolio = Portfolio()
    days = 30
    portfolio_values = []

    for day in range(days):
        print(f"\nDay {day + 1}:")
        for stock in stocks:
            stock.update_price()
            stock_prices[stock.name] = stock.price
            print(f"{stock.name}: ${stock.price:.2f}")
              # Simulate portfolio actions
        if day % 5 == 0:  # Buy stock every 5 days
            portfolio.buy_stock(stocks[0], 5)  # Buy 5 shares of the first stock

        if day % 7 == 0:  # Sell stock every 7 days
            portfolio.sell_stock(stocks[1], 2)  # Sell 2 shares of the second stock

        # Track portfolio value
        value = portfolio.portfolio_value(stock_prices)
        portfolio_values.append(value)
        print(f"Portfolio value: ${value:.2f}")

    # Plot portfolio value over time
    plt.plot(range(days), portfolio_values)
    plt.title("Portfolio Value Over Time")
    plt.xlabel("Days")
    plt.ylabel("Value in $")
    plt.show()

if _name_ == "_main_":
    simulate_market()

xternal/downloads/1000210629
