 

![](Dashboard/Attachments/Template_Gallery_Covers.png)

![](Dashboard/Attachments/positive-dynamic.png)

# Balance Your Portfolio

|   |   |
|---|---|
|![](Dashboard/Attachments/clock_gray%2028.svg)Created|@January 16, 2022 9:22 PM|
|![](Dashboard/Attachments/list_gray%20731.svg)Tags||

[![](Dashboard/Attachments/Screen_Shot_2021-05-15_at_5.06.40_PM.png)](Balance%20Your%20Portfolio/Screen_Shot_2021-05-15_at_5.06.40_PM.png)

![](Dashboard/Attachments/scanner.png)

Duplicate the template [here](https://notion.so/ETF-and-Stock-Rebalancer-d2a65fcb436e45b5867217e5d79be270)

[![](Dashboard/Attachments/investment-portfolio--v1%201.png)ETF and Stock Rebalancer](Balance%20Your%20Portfolio/ETF%20and%20Stock%20Rebalancer%205d0fa6bc4c2c480384a22796368ca277.html)

On your journey to financial independence, it's crucial for your portfolio to be aligned according to your plans for the future. This template will make sure your investment portfolio is balanced the way you need it to, making sure you're on track to achieve your financial goals.

_==Note: This template is based on Canadian ETFs and account types; however, asset class names can be easily changed and customized to better suit you!==_

## Accounts

The accounts that are used to hold the different items in your portfolio. This breakdown will help filter and sort the items held in your portfolio database.

Properties:

- `Name`

- `Type`

- `Portfolio Investments` (Relation)

## Asset Classes

An asset class is a group of investments that have similar characteristics and are subject to the same laws and regulations ([Source](https://www.investopedia.com/terms/a/assetclasses.asp)). It's important to have a balance between them that fits the risk you are willing to take as well as your time to retirement.

A target, in the form of a percentage, should be set for each of the asset classes.

The asset classes considered in this database are:

- Canadian Equity

- Fixed Income

- U.S. Equity

- International Equity

- Emerging Markets

- Cryptocurrency

Properties:

- `Name`

- `Target`: Holdings objective for a given asset class.

- `Actual`: Real holdings for a given asset class.

- `Action`: If applicable, whether you need to buy or sell more of a particular asset class as well as how much. Will display a yellow symbol to warn when the difference between target and action surpasses the value set as marginally acceptable (default 3%).

- `🟡 % Diff`: Point at which the difference between the target and the actual value is marginally acceptable. Default is 3%.

- `🔴 % Diff`: Point at which the difference between the target and the actual value is unacceptable. Default is 5%.

- `Status`: 🟢, 🟡 or 🔴 depending on the difference between target and actual values.

- `Portfolio Investments` (Relation)

- Rollups for each asset class, used for other calculations.

## Portfolio

The main database in this template. This is a list of every asset in your portfolio, and it should be the database you interact with and update the most.

Every item in the portfolio should correspond to at least one asset — although they often fit multiple (e.g. ETFs). It is very important you specify the distribution across all asset classes available such that the sum is 100%.

Properties:

- `Name`

- `Ticker`

- `Market Value`

- `% Fixed Income`

- `% Canadian Equity`

- `% U.S. Equity`

- `% International Equity`

- `% Emerging Markets`

- `Cryptocurrency`

- `Account` (Relation)

- `Status`: 🟢 or 🔴 when the asset allocation percentages do not add up to 100%.

- `Asset Classes`: Every entry in this database must contain all asset classes available in order for it to be included in the balancing calculations. To help with this, there is a "New Entry" template that can be used to create new items, which contains all relations it needs. Moreover, because a filter selecting all asset classes has been set, they will be added to any new row that is added.

---

---