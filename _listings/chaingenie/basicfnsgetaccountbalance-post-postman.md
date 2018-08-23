{
  "info": {
    "name": "ChainGenie Get user's account balance (*)",
    "_postman_id": "30d63c6b-db46-4a26-8598-65f7cef580d6",
    "description": "Get information about an user's account balance.  The call is restricted to the unlocked user's account / query only. <br/>* In this sandbox, you can query any user's account balance for testing purposes.  All accounts are test accounts and no actual value or account is exposed in the sandbox.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "1d10915e-a0da-4cf5-bd79-9caaa2afe90a",
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
              "id": "754acdb8-3c83-4da6-ae1f-a5a27213515c"
            }
          ]
        },
        {
          "id": "08cbd35a-3947-41ac-a04c-93528693f649",
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
              "id": "44f55436-de68-4020-991b-1966d34ed406"
            }
          ]
        },
        {
          "id": "2179b029-dae1-4662-be64-b6976293be05",
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
              "id": "4a36ca68-9cab-4a6a-8537-4beaf2b6269d"
            }
          ]
        },
        {
          "id": "b2a2a659-ab76-48f2-b029-b4994a27ab3d",
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
              "id": "375ab2d3-9e31-4032-aa97-1c5ff7bf154d"
            }
          ]
        },
        {
          "id": "2609496c-0bc8-4a1f-9ef5-8185aa650cba",
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
              "id": "89cb57e1-8144-4fe7-99fe-19a564af9f1b"
            }
          ]
        },
        {
          "id": "8b452569-d9c4-41ef-9c29-cfe0b141e7bb",
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
              "id": "76552914-ef9e-46f7-942d-74b002806a25"
            }
          ]
        },
        {
          "id": "92334bcb-b4c0-43e8-b61d-1a5dded49847",
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
              "id": "8888011b-8286-4f80-ad86-f2aeb0009de6"
            }
          ]
        },
        {
          "id": "03f91fa5-6323-423e-8605-a1a10e5ae00a",
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
              "id": "842daaba-983a-439c-a41b-f032ead983f6"
            }
          ]
        },
        {
          "id": "31bc69ff-c2a1-4d90-99e4-34eeee0b1dab",
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
              "id": "4497e3da-7a38-4ea5-ba41-1ebd403a74f5"
            }
          ]
        },
        {
          "id": "9b1052ed-d5c3-4898-bf58-1e9764dd79b7",
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
              "id": "602e6a53-c437-40cc-bb63-87da284686dc"
            }
          ]
        },
        {
          "id": "62974de1-cd48-4755-b421-d3bf1d266b90",
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
              "id": "3eb57956-ba3f-4aa2-b39f-65f2929e1632"
            }
          ]
        },
        {
          "id": "90743b0c-07f5-4f81-be70-9cbd2ca5df30",
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
              "id": "a2120d16-d823-4830-b9c6-3e84d801a57f"
            }
          ]
        },
        {
          "id": "25925eae-7126-419c-8c1d-5db51cf71774",
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
              "id": "c46bef1e-1287-48c6-943d-dd1b08b86581"
            }
          ]
        },
        {
          "id": "8000d981-0935-4863-a2ea-9bfe867ee4cd",
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
              "id": "c1be6b33-ef1d-4ea3-9a8e-76ac1ad2b4d2"
            }
          ]
        },
        {
          "id": "789984cf-7cd6-4e2b-b080-247b3b8c005c",
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
              "id": "a67b7a8b-f4c9-4d13-972d-4a8b566ea1b5"
            }
          ]
        },
        {
          "id": "ef1a12dd-7c0a-45f4-b28d-b4400695403f",
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
              "id": "f9433560-7720-4b94-a6c6-2451b39df7eb"
            }
          ]
        },
        {
          "id": "e1f9f6b4-f4b9-4d11-8b3d-417b92d5fc95",
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
              "id": "2b143bf5-9b7a-40f4-80a4-e33ddb2f4cf6"
            }
          ]
        },
        {
          "id": "07997821-b3e4-436e-ba99-2b19b0614733",
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
              "id": "1262f5b7-1bf2-440b-9710-2bbe4a5033b9"
            }
          ]
        },
        {
          "id": "e55c54e9-43b0-4adf-b60e-5bc42d6df4ec",
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
              "id": "88be272a-9b14-4513-b683-7b1569d00cdd"
            }
          ]
        },
        {
          "id": "31f4ae94-4fe7-41e1-9517-983c16893868",
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
              "id": "3cb9369a-c589-425c-a4fa-95ba161052a9"
            }
          ]
        },
        {
          "id": "5581533a-6054-44ac-ad10-8536f21691ab",
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
              "id": "51cf1f3e-26df-41cb-9ea4-17688683eaee"
            }
          ]
        },
        {
          "id": "216d93dc-57ce-4c7a-b990-51fcc6829e9f",
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
              "id": "9a8f9997-0035-483b-a50c-fc6685bd3250"
            }
          ]
        },
        {
          "id": "412834cc-cce2-45af-b199-d22d348125e0",
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
              "id": "891eb9e2-73df-40e8-a40a-2813cda856cd"
            }
          ]
        },
        {
          "id": "a55147ff-51e0-436f-9bb6-a548704400b7",
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
              "id": "d08fb129-62fe-42a2-a401-0c3f0df1a9a1"
            }
          ]
        },
        {
          "id": "37628543-947e-43c9-a28b-91d33e326f21",
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
              "id": "4f2ad5ed-bdf2-4335-be8c-70a2a7f0ed93"
            }
          ]
        },
        {
          "id": "a292445b-e41d-4e7f-b298-a969c80724f0",
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
              "id": "3dc68462-18b5-470d-97c2-7bc0e7d732b0"
            }
          ]
        },
        {
          "id": "0577a24c-97f3-4e07-88eb-77a1449412a7",
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
              "id": "13546319-b777-415e-8521-e7d821902ab9"
            }
          ]
        },
        {
          "id": "06e0ba9a-7a3a-4555-8450-3d38758aa1ce",
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
              "id": "54e257b5-90d2-4a26-a2c2-e639383d3b66"
            }
          ]
        },
        {
          "id": "6c6fe4a2-c60e-4d97-afff-5b067658fb17",
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
              "id": "d4393ca7-9748-4962-99ea-a8c809bc9396"
            }
          ]
        },
        {
          "id": "11818ce5-4aec-4601-bae4-cbb8dc91f2ad",
          "name": "BasicfnsGetAccountBalancePost",
          "request": {
            "url": "http://api.chaingenie.com/api/v1/basicfns/GetAccountBalance",
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
                  "key": "accountId",
                  "value": "{}",
                  "disabled": false,
                  "description": ""
                }
              ]
            },
            "description": "Get information about an user's account balance.  The call is restricted to the unlocked user's account / query only. <br/>* In this sandbox, you can query any user's account balance for testing purposes.  All accounts are test accounts and no actual value or account is exposed in the sandbox."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f8bdd257-6659-4195-8dd3-ad565f314655"
            }
          ]
        }
      ]
    }
  ]
}