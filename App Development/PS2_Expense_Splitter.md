# Group Expense Splitter – PS2

**Difficulty:** Beginner–Intermediate

## Problem Statement

Splitting food bills, travel costs, and shared purchases among friends often leads to confusing calculations. Build a mobile app that records group expenses and clearly shows who owes whom, without relying on a server.

## Objectives

- Practice managing related data across multiple screens.
- Implement reliable calculations and input validation.
- Persist group and expense data locally.

## Features

- Create groups and add or remove members.
- Add an expense with a title, amount, payer, and participating members.
- Split an expense equally among selected participants.
- Show each member's net balance (amount owed or receivable).
- Display an expense history for each group.
- Suggest a set of payments to settle outstanding balances.
- Allow editing or deleting an expense and recalculate balances correctly.

## Tech Stack (Example)

- **Frontend:** Kotlin / Java (Android Studio), Flutter (Dart), or React Native
- **Storage:** SQLite / Room or equivalent local database

## Notes

- Equal splits are sufficient; percentage or custom splits are optional.
- The app can be fully offline. No payment integration is expected.
- Handle edge cases such as zero/negative amounts, rounding, and an expense involving only some members.
- Settlement suggestions need to be correct, not necessarily mathematically minimal.
