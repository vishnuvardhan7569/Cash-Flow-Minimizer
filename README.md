
# 💸 Cash Flow Minimizer System

This is a C++ project that minimizes the number of financial transactions among multiple banks using various payment methods. The goal is to settle debts while minimizing the number of total cash flows required, even when banks have different or incompatible payment modes.

## 🔧 Features

* Calculates **net cash flow** for each bank
* Minimizes the **number of transactions** needed for settlement
* Supports **multiple payment modes** per bank
* Uses a **central "World Bank"** as an intermediary when direct payment is not possible due to incompatible modes
* Interactive console-based input system

## 📌 How It Works

* Each bank has:

  * A name
  * A set of supported payment types (e.g., PayTM, GooglePay, etc.)
* Debts between banks are represented as transactions in a graph.
* A greedy algorithm attempts to minimize the number of transactions needed to settle all debts by:

  * Finding the most positive and negative net balances
  * Matching them through common payment modes
  * Falling back to the World Bank when no direct method exists

## 📥 Input Format

You'll be prompted for:

1. Number of banks
2. For each bank:

   * Name and number of payment modes it supports
   * The names of the payment modes
3. Number of transactions
4. For each transaction:

   * Debtor bank, creditor bank, and the transaction amount

## 📤 Sample Input

```
5
World_Bank 2 Google_Pay PayTM
Bank_B 1 Google_Pay
Bank_C 1 Google_Pay
Bank_D 1 PayTM
Bank_E 1 PayTM
4
Bank_B World_Bank 300
Bank_C World_Bank 700
Bank_D Bank_B 500
Bank_E Bank_B 500
```

## ✅ Sample Output

```
The transactions for minimum cash flow are as follows :

Bank_B pays Rs 300 to World_Bank via Google_Pay
Bank_C pays Rs 700 to World_Bank via Google_Pay
World_Bank pays Rs 500 to Bank_D via PayTM
World_Bank pays Rs 500 to Bank_E via PayTM
```

## 🛠 Technologies Used

* C++ (Standard Library)
* STL containers like `vector`, `set`, `unordered_map`

## 🚀 Getting Started

1. **Compile the code**
   Use any standard C++ compiler. Example with g++:

   ```bash
   g++ min-cash-flow.cpp -o cashflow
   ```

2. **Run the program**

   ```bash
   ./cashflow
   ```

3. **Follow on-screen prompts** to enter bank and transaction data.

## 📄 License

This project is open-source and available under the MIT License.


