{
  "info": {
    "name": "ChainGenie Check document exists on blockchain",
    "_postman_id": "eb07e33f-e381-4608-bf38-d4e8882915c7",
    "description": "Check if your documents exists in the eth blockchain",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "c4281dc4-b240-48c4-8122-21e6d1baf2ff",
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
              "id": "9c48e48f-e552-4128-9e1b-f6a9d867e661"
            }
          ]
        },
        {
          "id": "53fa952e-8a31-4f87-a38a-17e8161fbd7b",
          "name": "EthbankWithdrawPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethbank/withdraw",
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
            "description": "Withdraw crypto currency into the bank.  In sandbox mode, the account used is the demo account on the blockchain server. Of course, you can only withdraw if there is money in the account!"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3e619995-cfb5-465c-a0a4-bd79b7cf338b"
            }
          ]
        },
        {
          "id": "9d888e3c-b937-4d7f-9c6b-7d893738dd22",
          "name": "EthbankPassbookGet",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethbank/passbook",
            "method": "GET",
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
              "mode": "raw"
            },
            "description": "Displays all transactions made by the user"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "db35e5ae-583b-4ae3-aa98-fa2e33397d50"
            }
          ]
        },
        {
          "id": "ff1a6c55-ebdd-4168-a633-e785a2314857",
          "name": "EthbankBalanceGet",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethbank/balance",
            "method": "GET",
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
              "mode": "raw"
            },
            "description": "Displays user bank balance information"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e2bad2ed-43c0-46e8-9eb4-2f0329f38eee"
            }
          ]
        },
        {
          "id": "d09450ba-b485-4ad0-8168-392bf0ff9860",
          "name": "EthledgerInvokecontractPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/invokecontract",
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
                  "key": "attribs",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "file",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "This API is the generic version of the \"Generate document from template\" API. Any template file can be uploaded (sample available as link for testing).  If you just want to see how this would work - use the other call and just run it without any uploaded certificate. \nUpload a templated pdf with editable / filable fields and generate a document with automated sign and routing to a recipient.  Every attribute that needs to be filled will need to be passed in the format - ex. course field to be substituted - field = attrib; value = [\"course\",\"course value\"] or date field to be substituted - field = attrib; value = [\"date\",\"12/12/2016\"].  If your fillable form has the field named \"today\", current time will be used for filling the value of that field.\nYou will need to upload for the file attribute a real template file with fillable fields. For the sample values as configured, you can use the demo template available at http://chaingenie.com/cert.pdf.  Download this certificate and add it as your input file\nTo route the document to recipient (optional) add field recipient with \"key\" of the recipient - available recipient in the system - 0xb3A214341df9560a3e09E256BfacefD6648f5Ca9 for your testing\nUse case - Upload an invoice template with fillable fields, add attrib values for all the fields that needs to be filled, add the recipient field - your invoice will be created, signed with your key (in production / in test it will be signed with the local admin key) and will be routed to the recipient (in production you can add your recipient / in sandbox - use recipient 0xb3A214341df9560a3e09E256BfacefD6648f5Ca9)\nResponse will contain the document name, signatories, timestamps, recipient, IPFS hash (handle to retrieve the actual document)\nThe document hash will be posted on blockchain and the actual document will be added to IPFS.  Want to retrieve your document? Check out the API - Write & Retrieve - Docs (IPFS)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "783aa17d-e21d-4ed2-8fb7-c7744d4c4f81"
            }
          ]
        },
        {
          "id": "54b8d305-3fe8-4a44-b14e-22b3c5ebf848",
          "name": "EthledgerDocertPost2",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/docert",
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
                  "key": "course",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "date",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "students",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "This is an over simplified version for testing this API for its powers a template - uses an inbuilt into ChainGenie template and values are preconfigured - just running this will work and provide you an IPFS handle to retrieve the document you generated with your variables / values from the template.\nUse an existing document on our server and generate a document with automated sign and routing to a recipient.  Ex. this configured api will generate a certificate for a student name (name) with the completed certificate course (course) and dated (date). \nThe document hash will be posted on blockchain and the actual document will be added to IPFS.  Want to retrieve your document? Check out the API - Write & Retrieve - Docs (IPFS)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "d3ffa3de-8a3b-494b-8266-c3fc499e508f"
            }
          ]
        },
        {
          "id": "114c8d75-fc54-4a20-83b9-ee690d63f067",
          "name": "EthledgerSendforsignPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/sendforsign",
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
                  "key": "files",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "recipient",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Route the document for signature.  The document history and status is updated for querying."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "72bf664d-7dc3-47af-9144-65f624e3f179"
            }
          ]
        },
        {
          "id": "b3fce38f-ecb6-4e83-9d3c-fa51be14f93a",
          "name": "EthledgerSignPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/sign",
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
                  "key": "files",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Cryptographically sign the document and add the record to blockchain.  The document history and status is updated for querying."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4dfbca6b-19ad-44f0-a94d-eebcb5197b21"
            }
          ]
        },
        {
          "id": "f31726d6-e9b0-4a80-bd09-125ae086b5d2",
          "name": "EthledgerDocstatusPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/docstatus",
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
                  "key": "files",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Review the document status - existence, hash, block info, signatories, routing to users and details"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "576d0b19-1da8-4e18-afef-a176f66859ad"
            }
          ]
        },
        {
          "id": "e23dc8ed-855e-42b5-81bb-6dd20d815faa",
          "name": "EthledgerExistsdocPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/existsdoc",
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
                  "key": "files",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Check if your documents exists in the eth blockchain"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2b7c3008-3154-4740-ba25-a5986ac33cf3"
            }
          ]
        }
      ]
    }
  ]
}