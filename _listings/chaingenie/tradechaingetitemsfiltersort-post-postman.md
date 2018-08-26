{
  "info": {
    "name": "ChainGenie Report / list of marketplace transactions",
    "_postman_id": "110ecd1b-68a5-4872-87dc-c556dcd4d80c",
    "description": "Use a combination of fields to get any type of report.  Ex. send specific seller name or id to get active for sale items by seller; send specific filehash to get status of a particular item/invoice; send itemPartNum to get a list of all products of that partnumber and send sort order as itemValue ascending to cheapest top list) . . . \r\n-\tfilterField (accepted items below, default – none)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemPartNum\r\no\tfileHash\r\no\tFileHash\r\n-\tsortField (accepted items below, default – itemValidUntil)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemValue\r\no\titemPartNum\r\no\titemValidUntil\r\n-\tsortOrder (default – desc)\r\no\tasc\r\no\tdesc\r\n-\tonSaleOnly (default – true, only if not “Inactive”)\r\no\ttrue\r\no\tfalse\r\n-\tmaxPrice (double; default - 0)",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "cb40ef84-9540-4c25-a6ef-748290e049d9",
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
              "id": "d48fcc3d-081b-4a67-b357-2173c74dcf65"
            }
          ]
        },
        {
          "id": "061198e4-c8ba-485e-adc7-59695613186f",
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
              "id": "7810cdb8-dac6-4662-86dc-5a081be733c5"
            }
          ]
        },
        {
          "id": "eef9cf78-4a96-4004-9d46-292077421497",
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
              "id": "887e8eec-e5ea-48d0-9850-8a6521f26498"
            }
          ]
        },
        {
          "id": "be0fe0c5-357a-41b2-aa7a-3e777a286a5d",
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
              "id": "d2105531-1600-4d11-8ae2-f05fb3763e70"
            }
          ]
        },
        {
          "id": "4d540896-0cbc-4125-b44c-d2dc3c997bea",
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
              "id": "17d6f814-c1dd-4f46-a304-5be80e8b9c96"
            }
          ]
        },
        {
          "id": "dcd7db14-5d6e-4714-b4e5-b65422923ce1",
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
              "id": "7e197215-780e-447f-bc6f-26ef96b9a8e2"
            }
          ]
        },
        {
          "id": "71cec1d4-8051-48f0-9469-660ac97c6c7a",
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
              "id": "3074853f-9449-4cfa-b7f7-0d13070ee960"
            }
          ]
        },
        {
          "id": "97fb027d-d737-41d3-9c57-a155c40689e4",
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
              "id": "137764f7-9700-400a-8069-7352ffface76"
            }
          ]
        },
        {
          "id": "654ee020-8395-4ba8-971a-0eefab9ec7d8",
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
              "id": "b9ab6192-57da-4951-a1ad-d48470b83888"
            }
          ]
        },
        {
          "id": "d2f7805f-cb23-412c-83f9-8b876a07c010",
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
              "id": "48874933-267b-42cf-ba14-6c9fe0687529"
            }
          ]
        },
        {
          "id": "1589f2c3-5957-4203-ba8d-00f4d281a917",
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
              "id": "018393a7-1892-4c86-b191-3a42be0ccf66"
            }
          ]
        },
        {
          "id": "d4311c3f-f452-4706-b905-e335160afd6e",
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
              "id": "6fc94055-e6c3-4fd7-9d5f-7989f62cde64"
            }
          ]
        },
        {
          "id": "4a850185-89fa-400d-ae4b-2728b22e5ec3",
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
              "id": "84d42577-c1a2-4206-aeff-b1450d057c28"
            }
          ]
        },
        {
          "id": "b01df9da-f119-4cdf-b191-eaca131c7424",
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
              "id": "e95237f7-5ef0-4258-bf2e-8f6f6f65825d"
            }
          ]
        },
        {
          "id": "ce2b39b3-3a77-4697-99a8-48b4b20df3b8",
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
              "id": "69a13927-435c-49e9-bf7d-e7b9d645ddcd"
            }
          ]
        },
        {
          "id": "95e5502f-faf7-46cb-970e-051d77b2a548",
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
              "id": "bb1509fb-18c3-423d-89d7-f970f0bea58c"
            }
          ]
        },
        {
          "id": "b9314652-fe56-48ec-963b-ca8a8cbd202f",
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
              "id": "eea8494f-704a-456b-a6de-06c083880d53"
            }
          ]
        },
        {
          "id": "c154d73a-c2ca-4e24-91b4-cd0c7b7dc408",
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
              "id": "4fa7c929-119e-4be9-bc80-b1ddbf7b28bc"
            }
          ]
        },
        {
          "id": "2a0773a8-c5ef-4520-b992-510eb31314a3",
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
              "id": "db1599ca-a84a-4fb8-ba1f-ac21264cf5cf"
            }
          ]
        },
        {
          "id": "2e37b783-ed00-4575-8af7-9992430c9b62",
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
              "id": "b97070b8-3348-4a8c-8630-5381e4461ce2"
            }
          ]
        },
        {
          "id": "78d2f0ba-7f04-4075-a2d5-4b2de52e8527",
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
              "id": "718b112f-ffe5-4de8-ada2-ed9489a3adcf"
            }
          ]
        },
        {
          "id": "3351fdc1-f79a-4256-83a1-0f540702110d",
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
              "id": "5cffcba0-e0af-4df0-ae27-1353488c985c"
            }
          ]
        },
        {
          "id": "c6d8d098-e340-485c-8240-1df5a748023c",
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
              "id": "eccb8eec-e2e1-4f52-9e5f-ac05385f1012"
            }
          ]
        },
        {
          "id": "871a8ce5-104c-4aea-b09f-33dcc5eb325b",
          "name": "TradechainConfirmReceivedPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/ConfirmReceived",
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
            "description": "Delivery of item confirmed by the buyer \r\n-Escrow is fully sent to seller\r\n- End transaction state = TRANSACTION COMPLETE"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9b031521-b10b-45ef-a7b5-c21694b5c881"
            }
          ]
        },
        {
          "id": "9b7bc9bc-ae4a-4ec6-9f3f-2afa380c3219",
          "name": "TradechainGetStateOfContractPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/GetStateOfContract",
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
                }
              ]
            },
            "description": "Get contract details & state\n- Provide full information including\n - Escrow amount in contract\n - Contract state \n - Buyer & Seller information\n - Links to contract / invoice documents\n - and other contract / sale specific information"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "0a2bc972-b11b-470a-b598-81603a7315fa"
            }
          ]
        },
        {
          "id": "86535d66-2c6a-4e7f-8e55-db72297e1e53",
          "name": "TradechainGetFundsLockedInContractPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/GetFundsLockedInContract",
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
                }
              ]
            },
            "description": "Get contract escrow details -\n- Retrieves full information including but not limited to\n - Escrow amount in contract\n - Contract state \n - Buyer & Seller information\n - Links to contract / invoice documents\n - and other contract / sale specific information"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b45625f0-5437-4d4c-87f9-37a5f50a5e56"
            }
          ]
        },
        {
          "id": "2484e1e6-f1dd-42b1-a7da-cbbe83934fc4",
          "name": "TradechainWhoIsSellerPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/WhoIsSeller",
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
                }
              ]
            },
            "description": "Get full information about the seller by providing the contract id.  Response will also include some contract details."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "99cdeb5b-fc33-435f-ab97-16f08f1d9f16"
            }
          ]
        },
        {
          "id": "783b1fd9-d788-4295-8dd2-2794b6d21e09",
          "name": "TradechainWhoIsBuyerPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/WhoIsBuyer",
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
                }
              ]
            },
            "description": "Get full information about the seller by providing the contract id.  Response will also include some contract details."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3ef6c45e-8dac-4fdd-8b2d-541972f22c56"
            }
          ]
        },
        {
          "id": "595324f4-99f0-4289-aac5-103f09a97562",
          "name": "TradechainGetItemsFilterSortPost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/tradechain/GetItemsFilterSort",
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
                  "key": "filterField",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "filterValue",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "maxPrice",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "onSaleOnly",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "sortField",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                },
                {
                  "key": "sortOrder",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Use a combination of fields to get any type of report.  Ex. send specific seller name or id to get active for sale items by seller; send specific filehash to get status of a particular item/invoice; send itemPartNum to get a list of all products of that partnumber and send sort order as itemValue ascending to cheapest top list) . . . \r\n-\tfilterField (accepted items below, default – none)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemPartNum\r\no\tfileHash\r\no\tFileHash\r\n-\tsortField (accepted items below, default – itemValidUntil)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemValue\r\no\titemPartNum\r\no\titemValidUntil\r\n-\tsortOrder (default – desc)\r\no\tasc\r\no\tdesc\r\n-\tonSaleOnly (default – true, only if not “Inactive”)\r\no\ttrue\r\no\tfalse\r\n-\tmaxPrice (double; default - 0)"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "595f1479-b75c-4ae0-8c11-34ab31982761"
            }
          ]
        }
      ]
    }
  ]
}