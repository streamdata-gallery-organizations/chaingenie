{
  "info": {
    "name": "ChainGenie Refund buyer and stop trade (by Seller)",
    "_postman_id": "333e446c-18ad-410a-b6d4-8f917cb013b7",
    "description": "Seller can cancel the market trade after bid/buy by refunding the seller<br/>\r\nEscrow from buyer is returned back to the buyer<br/>\r\nEscrow from seller is returned back to the seller (optional: penalties can be imposed)<br/>\r\nEnd transaction state = Escrow returned, smart contract cancelled and become inactive<br/>",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "f3ea3d1a-e28b-4c58-8d96-85a0ccb19163",
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
              "id": "2d3003c2-84ab-488e-adbc-06f582afd6e0"
            }
          ]
        },
        {
          "id": "ca2771da-b932-4982-8475-765660fb85f8",
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
              "id": "43bf7708-0d22-4d74-95a8-f5f2bd63517b"
            }
          ]
        },
        {
          "id": "a68be467-8dfb-459f-8ca9-223fa94f98c4",
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
              "id": "fa1f59dc-da78-4994-948b-180d5fffc266"
            }
          ]
        },
        {
          "id": "f44b3aa5-c93c-4143-8299-38ecf7126cc6",
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
              "id": "6d1b112c-e005-40fc-a035-3f967d3b5cc0"
            }
          ]
        },
        {
          "id": "59e23da4-0a16-4c93-89ab-85b5bfaaf49b",
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
              "id": "710d47cf-3dd2-4586-b7a4-514e95dd9c2f"
            }
          ]
        },
        {
          "id": "85a9db31-3bb6-4de8-8d8c-f324aadd16b3",
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
              "id": "5480ae19-7bdb-4ca4-a74f-a767a0aa0e28"
            }
          ]
        },
        {
          "id": "15c5603b-c463-46fe-b24a-cdbd3fe185b9",
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
              "id": "997a88b4-809e-4756-9883-bae7221d1f38"
            }
          ]
        },
        {
          "id": "fe4c0dbb-a741-45be-92d3-5086dd1efa34",
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
              "id": "02506d87-490a-443f-85f9-ea0fcc0db30e"
            }
          ]
        },
        {
          "id": "f2133d8e-c500-4cfd-bb54-33c63b318620",
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
              "id": "21ffd2b9-574a-42e7-869d-a3daa9254483"
            }
          ]
        },
        {
          "id": "9c93e67f-4e10-4c1e-a7eb-298da6dcd141",
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
              "id": "f810ac57-d6ca-411d-8b15-b6ecc5f77114"
            }
          ]
        },
        {
          "id": "3a16c46d-0840-4c57-9359-74215f326d76",
          "name": "EthledgerPostdocPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/postdoc",
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
                  "key": "filetypes",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Post document hash into eth chain for POE (proof of existence) and post the document into ipfs for safekeep!"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b3afda2a-d4d8-4a2a-b0ea-3cfbc824bf3a"
            }
          ]
        },
        {
          "id": "2b12bc07-75fc-4897-9b84-7c51ca3ed814",
          "name": "EthledgerSendcertPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/sendcert",
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
                  "key": "recipient",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "strHash",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Route the document to a recipient.  The document history and status is updated for querying.  The API call does not return any document properties.  This is a <b>minimalistic function</b> for stringing with other functions"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4b760296-6f15-4bf8-a40c-a7ec87c5d30a"
            }
          ]
        },
        {
          "id": "b443c556-16ca-4982-b4b2-d481b3196792",
          "name": "EthledgerSigncertPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/signcert",
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
                  "key": "strHash",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Cryptographically sign the document and add the record to blockchain.  The document history and status is updated for querying.  The API call does not return any document properties.  This is a <b>minimalistic function</b> for stringing with other functions"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2d49915f-dc94-4f92-a6c7-88209e9faa43"
            }
          ]
        },
        {
          "id": "6d10a2d4-a8bf-4603-862d-6dbf699e2e8f",
          "name": "EthledgerGetdocstatePost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/getdocstate",
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
                  "key": "strHash",
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
              "id": "86674672-3f0d-4eb1-88b0-c8b51ffc2605"
            }
          ]
        },
        {
          "id": "6bb88bcf-1d59-4d54-9f65-df0a242cd238",
          "name": "EthledgerPosthashPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/posthash",
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
                  "key": "hash",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Post string hash into eth chain for POE (proof of existence)"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "bc889898-75d3-46f5-9013-4f218c9ada59"
            }
          ]
        },
        {
          "id": "ede97ad8-f39e-4e3a-8578-cf4baaf04f1d",
          "name": "EthledgerExistshashPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/existshash",
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
                  "key": "hash",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Check if your hash exists in the eth blockchain"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a420fb37-4632-4b5e-9d86-110ca5b2a3af"
            }
          ]
        },
        {
          "id": "34ecbc6b-43f2-412e-958e-15ab88bd9997",
          "name": "EthledgerPoststrPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/poststr",
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
                  "key": "str",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Post string hash into eth chain for POE (proof of existence)"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "814e7215-171d-4942-83c0-306f5059c9b7"
            }
          ]
        },
        {
          "id": "1f4fedf7-54eb-4c26-bf9e-405a30a5240f",
          "name": "EthledgerExistsstrPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/existsstr",
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
                  "key": "str",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Check if your string exists in the eth blockchain"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "49cdbeb3-fc6b-4476-aa02-926bfeb065ef"
            }
          ]
        },
        {
          "id": "1850fa07-92f1-437e-a886-19fc98819bde",
          "name": "EthledgerGettransGet",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/ethledger/gettrans",
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
            "description": "Displays all transactions connected to this project / smart contract"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "23114cab-dc2e-4b5d-98a1-f79086d1a463"
            }
          ]
        },
        {
          "id": "68265261-6efe-4d3a-b883-4f679dc049d4",
          "name": "TradechainCreateTradeContractPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/CreateTradeContract",
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
                  "key": "itemName",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemPartNum",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemSellerName",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemValidUntil",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemValue",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "List product on marketplace: <br/>\r\n- Seller initiates sale - CreateTradeContract<br/>\r\n- Escrow from seller added for value of contract<br/>\r\n- End transaction state = Smart Contract Created<br/>"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "fcaf61bc-417f-4c86-9838-86068295dd7d"
            }
          ]
        },
        {
          "id": "65aba5eb-919f-43b0-8898-5203744805d8",
          "name": "TradechainConfirmAbortPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/ConfirmAbort",
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
                  "key": "itemContractId",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemSellerName",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Remove Listing (by Seller)<br/>\r\n- Seller cancels the market trade after listing but before bid/buy<br/>\r\n- Escrow from seller is returned back to the seller<br/>\r\n- End transaction state = Smart contract is rendered inactive<br/>"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1daa3782-00c2-4063-aa38-32365440f22b"
            }
          ]
        },
        {
          "id": "00851a3f-ac20-4e41-bb62-2f8b031c5288",
          "name": "TradechainConfirmPurchasePost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/ConfirmPurchase",
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
                  "key": "itemBuyerName",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemContractId",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Bid / buy the item listed on the marketplace: <br/>\r\n- Buyer confirms interest in buying<br/>\r\n- Escrow from buyer added to value of contract<br/>\r\n- Invoice document is created with all details using invoice template<br/>\r\n- Invoice is added IPFS and invoice hash into blockchain<br/>\r\n- End transaction state = Trade is actively locked between the seller and buyer<br/>"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "cf509bbe-d19f-4f26-832c-33a66edcd6b1"
            }
          ]
        },
        {
          "id": "0c28db68-bcb1-4fed-94f8-823994563a2e",
          "name": "TradechainConfirmRefundPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/ConfirmRefund",
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
                  "key": "itemContractId",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "itemSellerName",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Seller can cancel the market trade after bid/buy by refunding the seller<br/>\r\nEscrow from buyer is returned back to the buyer<br/>\r\nEscrow from seller is returned back to the seller (optional: penalties can be imposed)<br/>\r\nEnd transaction state = Escrow returned, smart contract cancelled and become inactive<br/>"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3fedaed3-6c53-405b-b44d-3cc78ef32922"
            }
          ]
        }
      ]
    }
  ]
}