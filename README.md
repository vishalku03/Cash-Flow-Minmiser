# Cash Flow Minimiser

[![Live App](https://img.shields.io/badge/Live-App-00bfff)](https://cash-flow-minmiser.vercel.app)

This project allows users to **split expenses with friends or colleagues**.  
If a group needs to share the cost of a particular bill, the Cash Flow Minimiser ensures that **everyone who paid gets reimbursed correctly**.  
It also calculates the **minimum number of transactions** required to settle debts.

---

## Demo

Check the live app here: [https://cash-flow-minmiser.vercel.app](https://cash-flow-minmiser.vercel.app)

---

## Video Demo

![Demo Video](https://user-images.githubusercontent.com/76661350/151113470-62df1428-0c25-4019-a5ee-25353530752.mp4)

---

## Installation

Clone the repository:  
```bash
git clone https://github.com/vishalku03/Cash-Flow-Minmiser.git
cd Cash-Flow-Minmiser


Check package.json file and ensure scripts are notated as below:

```
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
```


Delete the node_modules folder and any 'lock' files such as 
yarn.lock or package-lock.json if present.

Install required packages<br/>
`npm install`

Run the server<br/>
`npm start`

## How does it work?
Approach to solving this problem:
First, we take in all the transactions and exchanges that have happened among the group of people. We use a function which is used to calculate every individual's net balance. 

Based on their net balances, we can segregate the people into 2 categories - 
<ul>
<li>those under credit </li>
<li>those under debit</li>
</ul>


How Cash Flow Minimiser Works

A person is classified under credit if their net balance is greater than 0, meaning they are owed money.
Similarly, a person falls under debit if their net balance is less than 0, meaning they owe money to others.

If a person’s net balance is 0, they are considered settled and do not participate in further transactions.

Example
--------

Suppose Tarun pays ₹100 to Yash:

Tarun’s net balance becomes +100 → he is under credit and is to be reimbursed.

Yash’s net balance becomes -100 → he is under debit and needs to repay Tarun.

Once the transaction is completed, both their balances return to 0, meaning they are settled.

Settlement Algorithm---
---------------------

From the list of debtors, select the person with the largest debit.

From the list of creditors, select the person with the largest credit.

Settle these two amounts against each other.

Repeat this process for the next largest credit and debit until all individuals are fully settled.

Implementation:
-------------

This process is efficiently implemented using a Max Heap, which allows the algorithm to always pick the largest credit and largest debit at each step.
<<<<<<< HEAD
This is the approach followed in the Cash F
=======
This is the approach followed in the Cash Flow Minimiser to minimize the number of transactions needed to settle all balances.
>>>>>>> f7d83ee40df4abb4e0fd6fc006a983f30c8624a1
