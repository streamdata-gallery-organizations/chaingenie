---
swagger: "2.0"
x-collection-name: ChainGenie
x-complete: 0
info:
  title: ChainGenie Deposit into bank account
  description: Deposit crypto currency into the bank.  In sandbox mode, the account
    used is the demo account on the blockchain server.
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