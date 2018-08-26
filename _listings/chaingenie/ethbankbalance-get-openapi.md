---
swagger: "2.0"
x-collection-name: ChainGenie
x-complete: 0
info:
  title: ChainGenie Bank balance (user)
  description: Displays user bank balance information
  version: "1.0"
host: api.chaingenie.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /ethbank/deposit:
    post:
      summary: Deposit into bank account
      description: Deposit crypto currency into the bank.  In sandbox mode, the account
        used is the demo account on the blockchain server.
      operationId: EthbankDepositPost
      x-api-path-slug: ethbankdeposit-post
      parameters:
      - in: header
        name: ApiKey
      - in: formData
        name: value
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Deposit
      - Into
      - Bank
      - Account
  /ethbank/withdraw:
    post:
      summary: Withdraw from bank account
      description: Withdraw crypto currency into the bank.  In sandbox mode, the account
        used is the demo account on the blockchain server. Of course, you can only
        withdraw if there is money in the account!
      operationId: EthbankWithdrawPost
      x-api-path-slug: ethbankwithdraw-post
      parameters:
      - in: header
        name: ApiKey
      - in: formData
        name: value
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Withdraw
      - From
      - Bank
      - Account
  /ethbank/passbook:
    get:
      summary: Bank passbook (user)
      description: Displays all transactions made by the user
      operationId: EthbankPassbookGet
      x-api-path-slug: ethbankpassbook-get
      parameters:
      - in: header
        name: ApiKey
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Bank
      - Passbook
      - (user)
  /ethbank/balance:
    get:
      summary: Bank balance (user)
      description: Displays user bank balance information
      operationId: EthbankBalanceGet
      x-api-path-slug: ethbankbalance-get
      parameters:
      - in: header
        name: ApiKey
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Bank
      - Balance
      - (user)
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---