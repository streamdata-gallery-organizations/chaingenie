{
  "info": {
    "name": "ChainGenie Deposit into bank account",
    "_postman_id": "0cda9296-f9d8-4bbe-9ac5-24167910801b",
    "description": "Deposit crypto currency into the bank.  In sandbox mode, the account used is the demo account on the blockchain server.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "36ca9842-7725-4c8a-ae17-c4eb3d8d3699",
          "name": "EthbankDepositPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethbank/deposit",
            "method": "POST",
            "header": [
              {
                "key": "ApiKey",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "urlencoded",
              "urlencoded": [
                {
                  "key": "value",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Deposit crypto currency into the bank.  In sandbox mode, the account used is the demo account on the blockchain server."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "8fbb881f-2f40-4289-9483-98252635a338"
            }
          ]
        }
      ]
    }
  ]
}