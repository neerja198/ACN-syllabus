---
_db_id: 959
content_type: project
flavours:
- any_language
prerequisites:
  hard:
  - topics/intro-to-assertive-programming
  - projects/oop/animals/part2
submission_type: repo
title: Bank accounts - part 1
---

You have just been hired by a fin-tech startup. Your mission is to build a bank. It's going to be a cute little bank, real banks are waaaay more complicated.

## Directory structure 

### Python


Your directory structure should look like this:

```

├── banking
│   └── bank_account.py
├── setup.py
├── requirements.txt
├── .gitignore
└── tests
  └── ???

```

Please use `pytest` to test your work.


### JavaScript 

Your directory structure should look like this:

```
├── spec
|   ├── support
|   |   └── jasmine.json
|   └── ???
├── src
|   └── bank_account.js
└── package.json
```

Please test your work using jasmine.

### Java

Please make use of Gradle to set up your project structure. 
Your project name should be `banking`.

Make sure that all of the classes you define are within the `banking` package. Do this by including a package declaration at the top of each of your java files.


## How interest works

Let's say you have a bank account with an interest rate of 12% (that's really high, lucky you) and you have $1000 in your bank account. How much interest would you earn in one month?

12% of $1000 = (1000/100) x 12 = 120. So in a year you would earn $120. So in one month you would earn $10. 

So if you just left your bank account alone for a while then here is how the balance would look over time:

- Month 0: $1000
- Month 1: $1010
- Month 2: $1020.1
- Month 3: $1030.301
- Month 4: $1040.60401

Notice that we aren't just adding $10 every month. The interest is being calculated based on what is currently in the account at any point in time. This is called compounding interest. If you don't know about compounding interest it would be good to learn a bit about financial literacy. 

## Create a bank account class

Create a class called BankAccount

A Bank Account has the following properties:
- `balance`: This is the amount of money stored in the bank account.
- `interest rate`: This shows how much interest gets earned per year. An interest rate of `3.5` means you would get 3.5% interest per year

Add the following functions:

- `deposit` - This function should take in a single positive number. That number should get added to tha BankAccount's balance. 
- `withdraw` - This function should take in a single positive number. That number should be subtracted from the BankAccount's balance
- `compound_interest` - this will calculate the interest for the month and add it to the balance.

Here is some pseudocode:

```
account = new BankAccount(interest_rate=12) # when a bank account is constructed, you must set the interest rate
account.deposit(1500)
print(account.balance) # this will print 1500
account.withdraw(500)
print(account.balance) # this will print 1000
account.compound_interest()
print(account.balance) # this will print 1010
```

## Decimals 

Computers are good at a lot of things. But things can get a little bit weird when it comes to floating point numbers.

Whenever you are dealing with financial applications you need to make sure you are using high accuracy numbers. Different languages do things differently.

### Python

Please make use of [Decimal](https://docs.python.org/3/library/decimal.html). The documentation explains the problem.

### JavaScript

[This Stackoverflow question](https://stackoverflow.com/questions/11695618/dealing-with-float-precision-in-javascript) explains the problem. 

Please make use of [Decimal.js](https://github.com/MikeMcl/decimal.js/).


### Java 

[This Stackoverflow question](https://stackoverflow.com/questions/322749/retain-precision-with-double-in-java) explains the problem.

You will need to make use of the [BigDecimal](https://docs.oracle.com/javase/8/docs/api/java/math/BigDecimal.html) class for your numbers.

## Important

This is a bank so you have to take things very seriously. It's critical that you test all your work, test coverage should be 100%.

Also, please make use of assertions within your code to make sure that errors are raised if you try to:

- withdraw a negative amount
- deposit a negative amount
- withdraw more money than you have
- set a negative interest rate