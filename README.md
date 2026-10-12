# M-Pesa Reader

A simple web app that reads your M-Pesa messages and shows you where your money actually goes.

## What It Does

You copy your M-Pesa inbox messages and paste them into the page. The app reads each message, pulls out the amount, the type of transaction, who it was with, and when it happened. Then it shows you a clean summary: total sent, total received, biggest recipient, and a list of every transaction.

No login. No database. No tracking. You paste, it parses, you see.

## Why It Exists

Every Kenyan with M-Pesa has hundreds of SMS messages. Nobody knows where their money goes each month. This tool answers the question everyone asks at the end of the month: where did it all go?

## How It Works

1. The user pastes their M-Pesa messages into the textarea on the page.
2. The frontend sends the whole block to the server with a single POST request.
3. The server splits the text into lines and runs each line through a parser.
4. The parser uses regex to extract the code, amount, type, recipient, and date from each message.
5. Each parsed transaction is stored in an array on the server.
6. The server sends the array back to the frontend.
7. The frontend renders the summary cards and the transaction list.

## Supported Message Types

- Send Money (sent to X)
- Money Received (received from X)
- Pay Bill (sent to X Paybill)
- Buy Goods (paid to X)
- Withdrawal (withdrawn from agent)
- Airtime purchase
- Fuliza notifications
- M-Shwari transfers
- Reversal confirmations
- Unknown messages are stored as-is so nothing is lost

## How to Run

    npm start

Then open http://localhost:3000 in the browser.

## Tech Stack

- Node.js for the server
- Plain HTML, CSS, and JavaScript for the frontend
- No frameworks. No database. No build step.

## Status

In development.
