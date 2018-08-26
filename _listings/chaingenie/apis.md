---
name: ChainGenie
x-slug: chaingenie
description: ChainGenie provides a plug and play platform that helps you connect your
  existing (or create new) applications to DLTs for lodging and workflow management
  using a simple easy to use user interface. ChainGenie is a platform to create blockchain
  apps that provide speed-to-market for companies looking to launch faster, rather
  than reinvent the wheel. Write your applications to run on popular Blockchain networks
  like Ethereum, Bitcoin Blockchain etc with great ease when you require to validate
  credentials or make your existing traditional applications use the power of DLT
  and blockchain overnight!
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
x-kinRank: "7"
x-alexaRank: ""
tags: ChainGenie
created: "2018-08-26"
modified: "2018-08-26"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/apis.md
specificationVersion: "0.14"
apis:
- name: ChainGenie = DLT + Blockchain + Magic - Deposit into bank account
  x-api-slug: ethbankdeposit-post
  description: Deposit crypto currency into the bank.  In sandbox mode, the account
    used is the demo account on the blockchain server.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankdeposit-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankdeposit-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Withdraw from bank account
  x-api-slug: ethbankwithdraw-post
  description: Withdraw crypto currency into the bank.  In sandbox mode, the account
    used is the demo account on the blockchain server. Of course, you can only withdraw
    if there is money in the account!
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankwithdraw-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankwithdraw-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Bank passbook (user)
  x-api-slug: ethbankpassbook-get
  description: Displays all transactions made by the user
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankpassbook-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankpassbook-get-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Bank balance (user)
  x-api-slug: ethbankbalance-get
  description: Displays user bank balance information
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankbalance-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethbankbalance-get-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Generate, Sign & Route Document (Advanced)
  x-api-slug: ethledgerinvokecontract-post
  description: "This API is the generic version of the \"Generate document from template\"
    API. Any template file can be uploaded (sample available as link for testing).
    \ If you just want to see how this would work - use the other call and just run
    it without any uploaded certificate. \nUpload a templated pdf with editable /
    filable fields and generate a document with automated sign and routing to a recipient.
    \ Every attribute that needs to be filled will need to be passed in the format
    - ex. course field to be substituted - field = attrib; value = [\"course\",\"course
    value\"] or date field to be substituted - field = attrib; value = [\"date\",\"12/12/2016\"].
    \ If your fillable form has the field named \"today\", current time will be used
    for filling the value of that field.\nYou will need to upload for the file attribute
    a real template file with fillable fields. For the sample values as configured,
    you can use the demo template available at http://chaingenie.com/cert.pdf.  Download
    this certificate and add it as your input file\nTo route the document to recipient
    (optional) add field recipient with \"key\" of the recipient - available recipient
    in the system - 0xb3A214341df9560a3e09E256BfacefD6648f5Ca9 for your testing\nUse
    case - Upload an invoice template with fillable fields, add attrib values for
    all the fields that needs to be filled, add the recipient field - your invoice
    will be created, signed with your key (in production / in test it will be signed
    with the local admin key) and will be routed to the recipient (in production you
    can add your recipient / in sandbox - use recipient 0xb3A214341df9560a3e09E256BfacefD6648f5Ca9)\nResponse
    will contain the document name, signatories, timestamps, recipient, IPFS hash
    (handle to retrieve the actual document)\nThe document hash will be posted on
    blockchain and the actual document will be added to IPFS.  Want to retrieve your
    document? Check out the API - Write & Retrieve - Docs (IPFS)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerinvokecontract-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerinvokecontract-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Generate and Manage Document (Basic)
  x-api-slug: ethledgerdocert-post
  description: "This is an over simplified version for testing this API for its powers
    a template - uses an inbuilt into ChainGenie template and values are preconfigured
    - just running this will work and provide you an IPFS handle to retrieve the document
    you generated with your variables / values from the template.\nUse an existing
    document on our server and generate a document with automated sign and routing
    to a recipient.  Ex. this configured api will generate a certificate for a student
    name (name) with the completed certificate course (course) and dated (date). \nThe
    document hash will be posted on blockchain and the actual document will be added
    to IPFS.  Want to retrieve your document? Check out the API - Write & Retrieve
    - Docs (IPFS)."
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerdocert-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerdocert-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Send document
  x-api-slug: ethledgersendforsign-post
  description: Route the document for signature.  The document history and status
    is updated for querying.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersendforsign-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersendforsign-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Sign document
  x-api-slug: ethledgersign-post
  description: Cryptographically sign the document and add the record to blockchain.  The
    document history and status is updated for querying.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersign-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersign-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Check document exists on blockchain
  x-api-slug: ethledgerexistsdoc-post
  description: Check if your documents exists in the eth blockchain
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerexistsdoc-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerexistsdoc-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Post document to IPFS + blockchain
  x-api-slug: ethledgerpostdoc-post
  description: Post document hash into eth chain for POE (proof of existence) and
    post the document into ipfs for safekeep!
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerpostdoc-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerpostdoc-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Send document using hash (min fn;
    no return)
  x-api-slug: ethledgersendcert-post
  description: Route the document to a recipient.  The document history and status
    is updated for querying.  The API call does not return any document properties.  This
    is a <b>minimalistic function</b> for stringing with other functions
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersendcert-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersendcert-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Sign document using hash (min fn;
    no return)
  x-api-slug: ethledgersigncert-post
  description: Cryptographically sign the document and add the record to blockchain.  The
    document history and status is updated for querying.  The API call does not return
    any document properties.  This is a <b>minimalistic function</b> for stringing
    with other functions
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersigncert-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgersigncert-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Get document status using hash
  x-api-slug: ethledgergetdocstate-post
  description: Review the document status - existence, hash, block info, signatories,
    routing to users and details
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgergetdocstate-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgergetdocstate-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Write hash to blockchain
  x-api-slug: ethledgerposthash-post
  description: Post string hash into eth chain for POE (proof of existence)
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerposthash-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerposthash-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Write message to blockchain
  x-api-slug: ethledgerpoststr-post
  description: Post string hash into eth chain for POE (proof of existence)
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerpoststr-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgerpoststr-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Document transactions
  x-api-slug: ethledgergettrans-get
  description: Displays all transactions connected to this project / smart contract
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgergettrans-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgergettrans-get-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - List product for sale
  x-api-slug: tradechaincreatetradecontract-post
  description: "List product on marketplace: <br/>\r\n- Seller initiates sale - CreateTradeContract<br/>\r\n-
    Escrow from seller added for value of contract<br/>\r\n- End transaction state
    = Smart Contract Created<br/>"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaincreatetradecontract-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaincreatetradecontract-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Refund buyer and stop trade (by Seller)
  x-api-slug: tradechainconfirmrefund-post
  description: "Seller can cancel the market trade after bid/buy by refunding the
    seller<br/>\r\nEscrow from buyer is returned back to the buyer<br/>\r\nEscrow
    from seller is returned back to the seller (optional: penalties can be imposed)<br/>\r\nEnd
    transaction state = Escrow returned, smart contract cancelled and become inactive<br/>"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechainconfirmrefund-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechainconfirmrefund-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Get contract details & state
  x-api-slug: tradechaingetstateofcontract-post
  description: "Get contract details & state\n- Provide full information including\n
    - Escrow amount in contract\n - Contract state \n - Buyer & Seller information\n
    - Links to contract / invoice documents\n - and other contract / sale specific
    information"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaingetstateofcontract-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaingetstateofcontract-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Get buyer information
  x-api-slug: tradechainwhoisbuyer-post
  description: Get full information about the seller by providing the contract id.  Response
    will also include some contract details.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechainwhoisbuyer-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechainwhoisbuyer-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Report / list of marketplace transactions
  x-api-slug: tradechaingetitemsfiltersort-post
  description: "Use a combination of fields to get any type of report.  Ex. send specific
    seller name or id to get active for sale items by seller; send specific filehash
    to get status of a particular item/invoice; send itemPartNum to get a list of
    all products of that partnumber and send sort order as itemValue ascending to
    cheapest top list) . . . \r\n-\tfilterField (accepted items below, default \u2013
    none)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemPartNum\r\no\tfileHash\r\no\tFileHash\r\n-\tsortField
    (accepted items below, default \u2013 itemValidUntil)\r\no\titemSellerId\r\no\titemSellerName\r\no\titemBuyerId\r\no\titemBuyerName\r\no\titemId\r\no\titemName\r\no\titemValue\r\no\titemPartNum\r\no\titemValidUntil\r\n-\tsortOrder
    (default \u2013 desc)\r\no\tasc\r\no\tdesc\r\n-\tonSaleOnly (default \u2013 true,
    only if not \u201CInactive\u201D)\r\no\ttrue\r\no\tfalse\r\n-\tmaxPrice (double;
    default - 0)"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaingetitemsfiltersort-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/tradechaingetitemsfiltersort-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Get user's account balance (*)
  x-api-slug: basicfnsgetaccountbalance-post
  description: Get information about an user's account balance.  The call is restricted
    to the unlocked user's account / query only. <br/>* In this sandbox, you can query
    any user's account balance for testing purposes.  All accounts are test accounts
    and no actual value or account is exposed in the sandbox.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/basicfnsgetaccountbalance-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/basicfnsgetaccountbalance-post-openapi.md
- name: ChainGenie = DLT + Blockchain + Magic - Retrieve document from IPFS
  x-api-slug: ethledgeripfsget-post
  description: Retrieve the document stream from IPFS node
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28902-api-chaingenie-com.jpg
  humanURL: http://chaingenie.com
  baseURL: https://api.chaingenie.com//api/v1
  tags: Blockchain
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgeripfsget-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/chaingenie/master/_listings/chaingenie/ethledgeripfsget-post-openapi.md
x-common:
- type: x-github
  url: https://github.com/ChainGenie
- type: x-website
  url: http://chaingenie.com
- type: x-api-gallery
  url: http://broadleaf.commerce.api.gallery.streamdata.io
- type: x-twitter
  url: https://twitter.com/ChainGenie
- type: x-website
  url: http://api.chaingenie.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---