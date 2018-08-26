{
  "info": {
    "name": "ChainGenie Get contract details & state",
    "_postman_id": "2446a140-bb2b-41b3-9e34-38cd32fec5e8",
    "description": "Get contract details & state\n- Provide full information including\n - Escrow amount in contract\n - Contract state \n - Buyer & Seller information\n - Links to contract / invoice documents\n - and other contract / sale specific information",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Blockchain",
      "item": [
        {
          "id": "18f3d1fa-0cad-45cf-8341-eb70a4d0be2f",
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
              "id": "8af74552-f722-42da-b3fe-fb19fa010687"
            }
          ]
        },
        {
          "id": "c7d3dadc-dbb2-43a0-8e6f-bba78ab18414",
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
              "id": "452135f2-5209-4d7e-a380-d174fe686304"
            }
          ]
        },
        {
          "id": "f53f154c-d12d-4b01-bc54-09f23692aaa0",
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
              "id": "2bc64b56-d41b-4d6f-9af1-88e041b3baa3"
            }
          ]
        },
        {
          "id": "ed5709c2-8ae1-49bd-abb7-556040fac5dd",
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
              "id": "81897b9c-a760-47ef-83be-803b31ebd242"
            }
          ]
        },
        {
          "id": "e588b725-5d07-490d-8743-64d5856d4884",
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
              "id": "9fd075f2-1f0f-49eb-9eac-7033b67e52ba"
            }
          ]
        },
        {
          "id": "bed9b539-23dd-4c01-93e9-ce3251758e5f",
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
              "id": "c019f1a5-b59e-45c9-9239-abdb3c767f92"
            }
          ]
        },
        {
          "id": "a38b5253-bf8b-431a-8bbf-8f6de0489a6c",
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
              "id": "97274bf6-498a-46bc-941c-17be8a009403"
            }
          ]
        },
        {
          "id": "f3391568-1a94-47c0-993a-908a8dd9940f",
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
              "id": "d2386601-eac3-4ce6-8214-9fc923afb3ed"
            }
          ]
        },
        {
          "id": "56a33f43-7b51-4885-ae49-cfbe7e4837ef",
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
              "id": "5a5345d0-e2c8-4fbd-a762-c87dc54abec6"
            }
          ]
        },
        {
          "id": "efa0f146-ecc8-483f-9b1e-8095720a7429",
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
              "id": "ac389940-6e9d-4d4b-9063-45e74a4515d8"
            }
          ]
        },
        {
          "id": "c79f188d-b881-4512-8085-d7dfcbb6d9b6",
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
              "id": "2854f1be-2f19-4fab-8d2d-13902ee57492"
            }
          ]
        },
        {
          "id": "dbb1a67e-ff9b-48bb-b391-7649c12b17fa",
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
              "id": "0449257e-8180-419d-a782-a74fdee0d941"
            }
          ]
        },
        {
          "id": "bd7397dc-9fde-408d-82e1-915ca28e1f23",
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
              "id": "8a9cd746-e928-42d4-97ff-da07e9648563"
            }
          ]
        },
        {
          "id": "dc66e59b-9c7d-4dbb-9ff9-c9d8b205365c",
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
              "id": "421eb6d9-ce9b-41a3-b1eb-4d37f6862c7e"
            }
          ]
        },
        {
          "id": "082f9acc-6bff-4c40-9850-05c81959a8b7",
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
              "id": "48aed325-38a1-4cb2-97ff-94925aacad9c"
            }
          ]
        },
        {
          "id": "3e4a8790-7a0d-47d6-822d-1d40a245ffb8",
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
              "id": "2961f1bc-e87f-4f61-b30b-d0252ffe855b"
            }
          ]
        },
        {
          "id": "7d24fbe6-3391-4425-95b4-dcd452e43d9e",
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
              "id": "0440b7cd-496d-4a0e-bb24-91a5bd9ab7c8"
            }
          ]
        },
        {
          "id": "d454b40b-4fff-4467-86b4-9cffa2868854",
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
              "id": "8121d432-53d3-4725-85e1-be687e8bd16c"
            }
          ]
        },
        {
          "id": "f32c631d-87ae-464e-8e8a-15c840797fee",
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
              "id": "b48f68b8-7ad9-40f9-abfa-41ff7c3ba9cf"
            }
          ]
        },
        {
          "id": "1c26b8af-4fe4-40c5-bb3b-98131f68d12f",
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
              "id": "28c60601-1aea-4164-9b51-f2eaa3c0bfe6"
            }
          ]
        },
        {
          "id": "b2fa81d5-61e9-4c84-9c11-2b14e04155c5",
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
              "id": "b3743157-34f5-42c8-a798-55ef4bbe9fa9"
            }
          ]
        },
        {
          "id": "b6b1c9e3-0758-412a-a717-24612405bce0",
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
              "id": "4c73b288-38d6-48d3-960a-e19e1304c92f"
            }
          ]
        },
        {
          "id": "bc52cf05-b187-4a5d-9001-12dfbc031a4b",
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
              "id": "866d4a0d-84d2-451a-9c64-06b10ecc91a7"
            }
          ]
        },
        {
          "id": "41271889-85fb-4602-8043-a70f05bac865",
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
              "id": "74191151-4ab3-40c4-b7e5-893bdde5ec3c"
            }
          ]
        },
        {
          "id": "a63bd0cf-5454-4e92-9a2c-1b9efd0bdc47",
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
              "id": "ef5255ea-6cd6-41ad-b893-5e922d6aae2b"
            }
          ]
        }
      ]
    }
  ]
}