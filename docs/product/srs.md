  

GolDefi - Blockchain-based Digital Gold Tokenization Platform
ZEEVE INC.
Prepared for: GolDefi

           









Prepared by: 
Prateek Jha

Document Revision History

Date
Revision No.
Remarks
12th December 2023
1.0
Document Created
24th December 2023
1.1
Document Updated
11th March 2024
1.2
Document Updated
23rd April 2024
2.0
Document Revision with updated Requirements
18th June 2024
2.1
Tokenization and Redemption Process
23rd July
2.2
Final Draft





























TABLE OF CONTENTS 
Document Revision History	2
TABLE OF CONTENTS	3
Introduction	5
High Level Business Processes	5
User’s Registration	5
Distributor’s Registration	11
Gold Backed Tokens	15
Auditing Gold	16
Token Sales Platform	19
Tokenization Process	26
Authority/Reviewer onboarding	27
Token Redemption	27
Redemption process	29
Meta Transactions	33
Feature List	34
Frontend: User Portal	35
Frontend: Distributor Portal	35
Backend: Auditor Portal	36
Menus	36
Backend: Admin Portal	39
WorkFlows	47
User: Onboarding	47
User: Email Update Flow	48
User: Token Purchase (Credit/Debit Card, Crypto)	49
User: Token Purchase (Bank Payment Method)	50
User: Token Purchase (Cash Payment Method)	51
User: Update Wallet Address	53
Admin: Tokenization	53
Admin: Redemption	54
Admin: Update Threshold Limit	55
Admin: Update Platform Fee Account	55
Fees & Charges	56
Blockchain Details	56
Blockchain in use	56
Smart Contract	56
Write and Read operations in GDIToken smart contract:-	56
Events	58
Indexing Protocol	59
Technology Stack	59
User Type	60
Token Valuation	60
Notes	60

Introduction
The aim of this project is to implement a Blockchain-based Digital Gold Tokenization Platform that enables the creation, transaction, redemption, and burning of gold-backed crypto tokens. GolDefi, will be purchasing and storing the gold in the third-party vaults. Users can land on the website and Purchase GDI Tokens from the Platform using Fiat & Cryptocurrency (USDT). On placement of Orders, smart contract will mint the GDI Tokens which can be redeemed later.
High Level Business Processes
High Level business process includes
User Registration
Distributor Registration
Purchasing & Vaulting Gold
Auditing Gold
Token Sales Platform
Token Redemption

User’s Registration
The flow of the system starts with the users who are interested in the Digital Gold Investment. Users will be registering themselves on the website and submit KYC information. The third party KYC solution will share the status of KYC with the Goldefi Application.

The registration is divided into 3 different screens. Users can land on the Platform website and click on Signup Button. Users would need to fill in the following information.

Screen 1:
Date of Birth
Country
Please note that the platform will have provision of blacklisted and greylisted countries. Users signing up from blacklisted countries will not be allowed to register themselves on the platform.
Similarly, users registering from Grey listed countries will be asked for additional documentation during KYC.
There will be a provision at the admin panel to configure blacklisted and greylisted countries.


Screen 2:
Professional Activity - (A list of activities will be displayed and users can choose any one option from the list. This list will be configurable at the backend from admin’s panel)
Sector of Activity - (A list of activities will be displayed and users can choose any one option from the list. This list will be configurable at the backend from admin’s panel)
Annual Revenues
Declaration Statement



Screen 3:
Name
Email Address
Phone Number
Password
Confirm Password






Upon inputting the provided details, users will click the Create Account button. The system will then redirect them to the Email verification page, prompting the entry of the OTP sent to their email address.




Upon successful registration, users will be redirected to the Sign In page, where they must log in to access the platform. Following a successful login, Users will be directed to their “My Profile” page. 



After successful login, user can continue to complete their KYC. Without completing the KYC process, users won’t be able to buy GDI tokens. To complete KYC, users would be required to connect their Metamask wallet (using browser extension) with the platform and start the KYC process.

 Sumsub, a 3rd Party KYC Solution, is integrated for the KYC process. Users must click on the "Complete KYC" button and update the necessary information, including document attachments.

The KYC platform will share the status of applicants with the platform. Users will be notified of KYC status via email.

To make the account more secure, Users will set up 2 factor authentication on the platform which can be configured in My profile section. 2 Factor Authentication service will be provided for the User to add additional security to the login withAWS MFA Service.



Please note, User will be able to Update certain information provided at the time of the registration process listed below:
Address - To update the address, a request will be sent to the connected wallet to digitally approve the address. This address will be used for the delivery of physical gold at the time of redemption of GDI Tokens.
Email: Below steps required to update email address
User updates their email id in my profile and asks for OTP
OTP is entered by Customer confirming access to new email
Frontend then logs out the customer
Customer can login with new email id
Mobile number: Mobile verification will be done in Phase-2 (not included in this SRS).
Wallet address: It can be updated again but requires re-verification that the client is the BO (beneficial owner) of the new wallet.

Distributor’s Registration
Platform admin will create Distributors accounts from their portal and click a button to send the invitation email to the distributors via Goldefi Platform.
Distributors will access the email and click on the link to reset the password. Once the password is reset, the Distributor can login to the platform and complete its KYC. Please note that the KYC process of Users and Distributors are different in Sumsub.
Once KYC is completed, Distributors will be able to search orders and register cash payments on Cash orders.
Registering Payment for the Users
Users who would want to purchase GDI tokens using cash will create their orders in the platform and select the Payment method as Cash.
After creating the order, the User will search nearby distributors and visit them to provide the Order ID and email account.
Distributors will then be able to search the order by entering the order ID and Users email address. Please note, in order to maintain the security of the platform, Distributors will only be able to search for the orders by entering both the fields Order ID and email address.
To access the Sale order details an OTP will be sent to the User’s registered email address and User will share this OTP with the Distributor. By entering this OTP, distributors will be able to access the User’s order information.
After searching the order, the Distributor will then be able to register the payment in Cash. User will provide cash to the distributor and the distributor will mark the payment received on the order.
A digital signature will be required to register the payment. As soon as the payment is registered GDI Tokens will be minted and transferred to the buyers wallet address.
An email will be sent to the Users for the payment confirmation.
The settlement of the payment between Distributors and Goldefi will happen outside the platform.
The no. of GDI Tokens generated will be pegged to the weight of Gold. For example, 1 GDI Token will be generated for each 0.001 gram of Gold.











Gold Backed Tokens
At the launch of the Goldefi platform, Goldefi will have a collateral signed with the vault for 1KG of Gold. This gold will be available at the Vault location and ownership of this gold will be with Goldefi. (This will be managed outside the platform and not included in this SRS).
On receiving orders from Users, Vault will transfer the ownership of the Gold equivalent to the quantity of tokens purchased to the custodian’s ownership. Vault will be the Custodian of the platform. On redemption of tokens, this physical gold (under custodian’s custody) will be shipped to the Users. (This will be managed outside the platform and not included in this SRS).
In this phase of the project, there will be only one Vault linked to the platform. However in future phases there can be multiple vaults. The system will be designed in a way where it would be easier to implement multiple vault functionalities.

Auditing Gold
An Auditor will be creating Audit requests manually and visit the Vault locations to audit the Gold’s incoming and outgoing value. Auditor needs to follow the below steps for periodic audits.
The Auditor will visit the vault to audit.
The Auditor will create the Audit in the platform and upload the Audit report.
The Audit Inspector will physically verify all the information of Gold Batch in Vault premises like Quantity as per the document, Quality of the Gold, etc.
The Audit Inspector will upload the Factual Findings report on the platform, add his/her comments and post it on the Audit request.
The Audit Inspector will also fill in the following information of physical check
Vault Name
Auditor - will come up automatically
Comments
Metadata - Autofill
Status
Draft
Pending
Documents uploaded
Audited
Cancelled
Done
Exception
To submit the Audit report, the Audit Inspector will be required to digitally sign the audit.
All the uploaded documents will be stored in ZDFS (an IPFS service from Zeeve) and the hash of those documents will be stored in the blockchain.







Token Sales Platform
To access Token Sales Platform, Users should be registered on the platform with completed KYC and wallet connected to the platform. To purchase GDI Tokens, users will be navigating to the Buy GDI Token menu. Detailed steps are below

Navigate to Buy GDI Token
A screen will appear with two tabs
Buy using Cryptocurrencies (Default Tab)
Fields in this tab
Enter amount of GDI Token to Purchase
Select Cryptocurrency  as Payment method (USDT only in this phase, i.e, Phase-1)
Platform fee will be added (in GDI tokens) based on following calculation
Calculation
Case 1
Case 2
Token purchased
10000
100
percentage fee
5%
5%
GDI FEE VALUE (GDI tokens)
500
5
USD FEE VALUE
$3,750.00
$37.50
MINIMUM FEE (in $)
$50.00
$50.00
Minimum fee (in Tokens)
6.666666667
6.666666667
Payable amount (in GDI Tokens)
10500
0
PAYABLE AMOUNT ($)
$78,750.00
$0.00
Result
Purchase allowed
Purchase not allowed

Amount of Cryptocurrency to be transferred will appear automatically based on above calculation
Buy Button - By clicking on this button, a request will be sent to Metamask (Web wallet).
Buyer will have to approve the transaction in Metamask.
Once the cryptocurrency is received into the wallet. Tokens will be minted and transferred to the Buyer’s wallet.
Detailed Tokenization Process is explained here.




Buy using US Dollars.
Fields in this tab
Enter amount of GDI Token to Purchase
Select Fiat currency as Payment method (USD for phase-1)
Buy Button - By clicking on this button, the system will redirect users to the Stripe Payment Gateway and in return, payment gateway will share the status of the Payment.
The system will automatically generate an Order. Tokens will be minted and transferred to the Buyer’s account.
Detailed Tokenization Process is explained here.

Buy using Cash
In case of Cash orders, Users who would want to purchase GDI tokens using cash will create their orders on the platform and select the Payment method as Cash.
After creating the order, the User will search and visit any of Goldefi Distributors and provide them with the Order ID and email account.
Distributors will then be able to search the order by entering the order ID and Users email address.
To access the Sale Order details, an OTP will be sent to the User’s email address, User will share this OTP with the Distributor.
After searching the order, the Distributor will then be able to register the payment in Cash. User will provide cash to the distributor and the distributor will mark the payment received on the order.
A digital signature from the Distributor will be required to register the payment.
As soon as the order is placed, An email will be sent to the Users for the payment confirmation.
Payment record will be created and will be visible in the Distributor's portal.
Admin will verify the payment received in the backend.
Detailed Tokenization Process is explained here.
Note: The no. of GDI Tokens generated will be pegged to the weight of Gold. For example, 1 GDI Token will be generated for each 0.001 gram of Gold.



Buy using Bank Transfer
There will be a configuration menu from admin's panel where admin can configure banks information for each country. 
At the time of selecting the Bank transfer option, a list of already configured one or more banks (associated to the country) will pop up where the user can select any one of them to process and enter the transaction information. 
In case if there is no bank available for the country there will be a default bank configuration which will pop up automatically.

On selecting the bank, all the information of banks will be displayed on the screen with account details where users would be required to transfer the funds.
Along with the account details a unique code will be displayed on the screen which users would need to copy from the screen and use it in the Payment transaction to the bank account (which will happen on the bank application and not part of this platform).
The unique code will also be saved in the Sales Order so at the time of verifying the payment, platform admin can verify which payment is related to the order.
If User forgets to enter the code while making payment, the user will then have to reach out to the support team of Goldefi and share the transaction reference with them. The support process is not part of the platform.
To  verify the payment, Minting officer will be signing and confirming amount received as follows:-
Mark Payment as Done:
In the Backend: On click of accept payment button a popup is visible with message “Verify Payment amount is same as that of Order”
Admin can close this popup using close button  if they don’t want to proceed at the moment
On acceptance of the above popup, check the type of admin’s connected wallet in blockchain.
If the wallet is not authorised, show popup to get access from support
If the wallet is authorised, show the metamask popup for signature request
On successful signature, move the payment record to document/receipt upload stage
Admin then uploads the supporting document/receipts of payment
The payment is marked as success and Order is marked as paid
An email is sent to Tokenization Operator to process Order
Mark Payment as Rejected 
On click of the Reject Payment button, a pop up will appear with a message “Are you sure to reject the payment” and on confirmation the payment will be rejected and this will also cancel the Order.
User would require clicking on the confirm button in the pop up in order to reject the payment as well as orders.
On payment rejection, an email will be sent to the buyer.

Detailed Tokenization Process is explained here.







After order confirmation, Users can view their Order history by navigating to the My token menu. Following will be the information available for them:-
Order Reference
GDI Token Quantity
Gold Weightage (Equivalent to GDI Token Quantity)
Total Amount to be Paid
Order Status
Draft
Paid
Minted
Cancelled
Payment Method
Transaction reference number/Link



Tokenization Process 
Tokenization Process Start: The tokenization process includes the following steps (here "Tokenization Operator" is a GolDeFi employee):

The Tokenization Operator receives an email notification that a Tokenization Request has arrived in the system.
The Tokenization Operator logs into the system, opens the Tokenization Request, reviews and accepts it.
The Tokenization Operator assigns a (single) Vault to the Tokenization Request using a dropdown. If there is only one vault in the system then it will be automatically selected.
Note: There will be one vault in phase-1 for phase-2 there can be multiple vaults.
Ownership Transfer & Custodial Assignment: The ownership of the fractional gold, to be represented by the tokens, is transferred to the token holder (generically) and the Vault is appointed as the custodian. Once this is done, an optional document may be uploaded to the Tokenization Request and finalizes it.
An email notification is sent to the Vault itself with all the tokenization details, it may include the optional documentation and an attachment.
Minting Tokens: GDI tokens corresponding to the fractional gold purchase by the user are automatically minted.
Sale order status is updated to minting-in-progress.
Token Distribution: The minted tokens are issued and transferred (as part of the minting) as follows:
Fee Payment: Fees, denominated in GDI tokens, are transferred to a corporate wallet.
Client Transfer: Purchased GDI tokens are transferred to the purchaser's wallet.
The system marks the Tokenization Request as executed.


Authority/Reviewer onboarding
Admin can create a user which different Authorities can use to audit and examine the data like orders,  audit reports and other details present on the platform at any given instance. 
For this a read-only user will be created who will have access to all data and cannot update or remove any of it.

Token Redemption
Users can redeem their GDI Tokens for actual gold through a dedicated menu on the User portal
To Redeem GDI Token, User needs to raise a Redemption Request and fill in the following information.
Total Token you want to redeem. (Please note that a minimum 1 Troy ounce of Gold can be redeemed and in multiple of ounces).
Address: By default, User’s current address from profile page will be visible, However there will be an option to change the delivery address. Users can update the address and digitally sign the update.
Users can submit the request by clicking on Submit request Button and filling in all the above information.
To place a Redemption request, there will be a fixed non refundable fee (In GDI Tokens) charged to the User. On submitting the redemption request, a request will be sent to the user’s metamask wallet.
Users need to approve the non refundable fee request in their wallet and on confirmation, the request will be placed and a notification will be sent to the redemption operation in Goldefi.
Detailed Redemption process is explained here.
There will be an option to capture the Unique serial number of the gold bar in the redemption request. Redemption operator will update this serial number at the time of delivery.








Redemption process
Once Redemption request is submitted by user after paying non-refundable fee as per the blow calculation:-
For example: User Redeeming 400GDI / XYZ Troy oz + 5GDI (non-refundable fee) + 10% platform fee (40GDI)
-->TOTAL: 445 GDI
--> Pay : 5GDI and remaining they will pay on receiving the quote --> pay 5GDI from wallet

Redemption request processing starts right after that. The redemption process includes the following steps (here "Redemption Operator" is a GolDeFi employee):
The Redemption Operator receives an email notification that a Redemption Request has arrived in the system
The Redemption Operator logs into the system, opens the Redemption Request, reviews and accepts it. Following will be the fields in Redemption Order
Client
Order Date
Total Tokens to be Redeemed
Total Gold to be Delivered(weightage equivalent to tokens)
Delivery Charges (In GDI Tokens)
Platform Fee (In GDI Tokens)
Vault Allocated
Status
The Redemption Operator assigns a Vault to the RedemptionRequest using a dropdown. If there is only one vault in the system then it will be automatically selected. (There will be only one vault in phase I of the platform)
The Redemption Operator calls the Vault for a quote and adds the data to the Redemption Request, such as fees, shipping, insurance, etc. There will be 2 action buttons on Delivery Quotation generated for Redemption Request as follow:-
Mark as updated (done by Redemption Operator)
This button will be visible in draft state in Redemption Request object.
Once the fee is added to the record, the Redemption Operator clicks on this button, after that the quote moves to quotation-updated state.
Now the fields will not be editable in quotation-updated state.
Mark as Selected / Confirm (In Delivery Quotation object)
This button will be visible in the quotation-updated state in the Delivery Quotation object.
On click of this button, the rest of the delivery quotation related to Redemption order will be cancelled and selected quotation will be moved to Quotation-Selected state. This applies when there are multiple vaults. (Not part of phase I)
Delivery fee present on selected Quotation will be updated on the related Redemption request.
Send email to client to review request

The platform sends a notification (email, SMS) to the Client that they received the quote as follows:
	Continuing previous example,

Quote:- 440 GDI + shipping and insurance (10GDI) ==> 450GDI --> pay from wallet

Client can navigate to My Order menu in Users portal and selects the relevant Redemption Order, and choose between both the options explained below:
Agrees to the shipping cost shared and signs the transaction in MetaMask to transfer the GDI tokens using Approve Blockchain function (minus the already paid non-refundable redemption process fee)
Disagree on the shipping cost shared, then the RedemptionRequest is cancelled and the Redemption Operator will be notified by email.
If the client agrees:
The Redemption Request will gets confirmed.
An email notification will be sent to the Vault with all the Redemption Details.
Redemption Operator can click “Process Redemption request” button to call the blockchain function 
Check threshold limit and based on that send request to Gnosis or KMS (in Phase-2)
It deducts shipping fee (in GDI tokens)
Actual gold amount (in GDI tokens)
From the users wallet by moving these to a Intermediate Wallet (Redemption Handler Wallet)
Vault Process start (Outside the platform)
The Vault views the confirmed redemption request notification (email)
The Vault dispatches the corresponding gold to the client and sends the Tracking number to the Redemption Operator
Vault process end
The Redemption Operator adds the Tracking number to the RedemptionRequest, and clicks a button “Burn Tokens” which Automatically:
Burns the tokens linked to the RedemptionRequest
Sends the client an email with the Tracking number
The system marks the RedemptionRequest as executed




Following will be the fields in Redemption Order
User
Order Date
Total Gold to be Delivered(weightage equivalent to tokens)
Delivery Charges (In GDI Tokens)
Platform Fee (In GDI Tokens)
Vault Allocated
Status
Unique Serial number (Gold bar)

There will be an option to capture the Unique serial number of the gold bar in the redemption request. The Redemption Operator will update this serial number at the time of delivery.

Meta Transactions
Meta transaction feature will allow users to transfer Tokens on platform with their gas fees either paid by the platform (FULLY SUBSIDISED) or will be deducted from the GDI tokens (PARTIALLY SUBSIDISED) balance instead of needed to have native tokens into account. If the user does not belong to either of the categories, then they are required to pay gas fees in native currency that is MATIC.

The Process work as follows:-
User lands on Direct Transfer Portal on GolDefi Platform and frontend requests the wallet subsidiary type from backend along with rest of the details i.e, contract address gas fees etc (/api/v1/meta-txn-create)
Backend checks the user wallet address and finds the type of payment option (FULLY SUBSIDISED, PARTIALLY SUBSIDISED, Non-Subsidised or Native Tokens) available and returns the payload that needs to be signed by user
User submits To address and amount to be transferred (optional: allow option to choose transaction speed from ‘safeLow' | 'average' | 'fast' | 'fastest') which is sent to metamask wallet for User to sign the request
Once it is signed, it is then sent to backend (/api/v1/meta-txn-process) for Relayer Transaction Request (Node App)
Relayer (wallet) calls the Forwarder’s (smart contract)  execute function to do the transaction
Once the transaction is complete the status is return to user


Cases
Fully subsidised
Send to frontend [ {
    from: signer.address (user) ,
    to: goldefi.address (Main contract),
    data: registry.interface.encodeFunctionData(“transfer”, [to, 123]),
    value: 0, 
    gas: 1e6, 
    nonce
}]
Gas fees will be paid by Relayer/Forwarder having balance already.


Partially subsidised (pay via GDI tokens)
Send to frontend [ {
    from: signer.address (user) ,
    to: goldefi.address (Main contract),
   data: registry.interface.encodeFunctionData(“batchTransfer”, [[to, platformRecipient],[123,  0.3]]),
    value: 0, 
    gas: 1e6, 
    nonce
} 
]
Gas fees will be paid by User based on the above response to FeeHandler.

Native tokens (Send Request to GDI Contract)
Create transaction and pay via Metamask
Gas fees will be directly paid by user









Feature List
Below are the detailed feature List of the Platform Based on Users Type

Frontend: User Portal
As soon as User Logs in to the portal, System will redirect them to the Profile page.

My Profile Section - User will be able to Update certain information provided at the time of the registration process.  
KYC - Users will be able to check their KYC status under this section and be able to complete the KYC process if status is pending. Platform will be integrated with Sumsub, a third  party KYC platform.
Physical Address: Update Physical Address of user.
Update Password: User can change their password
Google/AWS Authenticator: To set up 2FA authentication
Dashboard: List details about current tokens holding, recent orders.
Token Purchasing Section (Buy Tokens) - There will be a section where Users can navigate to purchase the GDI Tokens. There will be different options to Purchase GDI. Detailed Token Buying platform is explained under section “ Token Sales Platform” in this document.
Token Redemption (Redeem Tokens) -  There will be a menu on the User portal using which Users can redeem their GDI Tokens with actual Gold.
Order History (My Tokens) - Users will be able to check their GDI Tokens purchase history under this section

Frontend: Distributor Portal
As soon as distributor logs into the portal, System will redirect them to the Profile page or Order search page based on the KYC status.

My Profile Section - Distributor will be able to Update the information provided at the time of the registration process. 
KYC - Distributors will be able to check their KYC status under this section and will be able to complete the KYC process if status is pending.
Physical Address: Update Physical Address of Distributor.
Update Password: Distributor can change their password
Google/AWS Authenticator: To set up 2FA authentication
Order Search Page - Distributor will search for Sales order based on Email id and Order ID of the User, if the KYC status of the User is verified and sale order exists then only the order will be visible. Refer Registering Payment for the Users for detailed flow.
Payment Receipts: All the received Payments can be viewed here.


Backend: Auditor Portal
Auditors will be able to manage Audits on the platform. The Audit Inspector will verify all the information of Gold and will upload the Factual Findings report. For the workflow Refer: Auditing Gold.

Menus
Gold Audit
ID: Id for the Audit
Vault: Related Vault for Audit
Auditor: Auditor user who is performing the Audit
Comments: To add comments on Gold status and other details found during audit
Document Hash: A unique hash created when audit report is uploaded in IPFS
Digital Signature: A signature when an auditor uploads and signs the audit report to confirm the authenticity.
Meta Data: The data that is signed (including comments and document hash) by auditor for performing the Audit
Stage
Draft
Pending
Documents Uploaded
Audited
Cancelled
Done
Exception





























Partners
Vault Locations
Vault Name: Name of the vault
Vault user: User to be contacted for Vault related questions.
Vault Address: Address of Physical location of Vault
User’s Email: Email of Vault user
User’s Mobile no.: Mobile number  of Vault user
Vault ID: Unique ID of Vault generated to store in blockchain
URI: A URL of the vault where related documents are stored.
Tokens, Gold Available at Custodian: ?
Gold Available at Vault: ?




Backend: Admin Portal
Following will be the detailed features of Admin’s Portal
GolDefi Platform
Orders: Admin can see all the Order created on platform
Orders: This sub-menu will List All the  Orders
Customers: This will show all the Users signed on Token Sale platform
Gold Audit: Admin can see all the audits submitted on the platform.
All Audits: This sub-menu will List All the  Audits in different stages
It has Audit ID, Vault, Auditor user and other fields that can be referred here: Audit Fields
Redemption: Here the Redemption Order related information will be present
Redemption Requests
Order Ref: Order reference of the Redemption order
Client: User who has created the redemption request
Quantity
Redemption ID: Id created to store in blockchain
Date: Date of Order created
Platform fee: Charged by Platform
Address: Address of the Client when gold delivery is requested. 
Vault allocation: All the Vaults to whom Redemption Operator will reach out to ask for quotation will be listed here. 
Delivery Quotations: In this button, all related quotation created based on the Redemption Flow will be visible
Gold Serial Number: To refer gold that will be delivered
Tracking number: To refer for tracking gold delivery by vault
Shipping insurance fee: Added after the quote is confirmed from the vault
Stage
Draft
Quotation requested
Quotation selected
Ready to deliver
Completed
cancel
Delivery Quotations: All the delivery quotation requested from vaults will be listed here
Reference: Redemption order reference
Vault: Related vault to which the quotation is requested
Quantity
Delivery fee
Date
Stage
Draft
Quotation updated: quotation is updated by vault user
Selected: Quotation is selected by Redemption operator
Rejected: Quotation is Rejected by Redemption operator

Partners
Distributor
All Distributor user will be created here
Name
Address
Email
Phone
Mobile
Is KYC done
Clients
All Users / Investors user will be created here
Name
Address
Wallet address: Wallet address of user
Email
Phone
Mobile
Professional Activity
Sector of Activity
Range of Annual Revenues
Annual Threshold Limit
Is KYC done
Auditor
All auditor user will be created here
Name
Address
Public Key: Wallet address of auditor, used to verify the auditor while performing audit
Email
Phone
Mobile
Vault Locations: List of Vaults to deliver the gold, Refer Vault Locations for detailed information
Configuration
Admin Configuration
Fee Configuration
Current Gold Rate: The Gold rate is used to show the value corresponding to GDI tokens purchased by Users on platform. This is configured manually by Platform Admin. The unit will be USD/mg.
Fee Account Address: The address where the platform fee will be transferred after blockchain transaction for purchase, redeem and transfer of GDI tokens
Buy Calculation Type: It is configured to apply different types of platform fee during Token Purchase. Admin can configure platform fee as Fixed, by Percentage and By Range options to charge the fees. A minimum fee can also be configured in each type of calculation.
Fixed: In this case a fixed amount is charged. Admin will configure value in USD and GDI tokens corresponding to this value will be charged.

Percentage: 
When configured a percentage value, user will be charged a percentage of total tokens the user is going to purchase. 
In this case, the total tokens purchased should be greater than minimum tokens value. Admin will configure value in USD and GDI tokens corresponding to this value will be charged.

By Range
Admin can configure different range values to charge the fee. For example: for 1 to 100 GDI tokens charge 5%, 101 to 200 GDI tokens charge 4% etc
In this case also, the total tokens purchased should be greater than minimum tokens value. Admin will configure value in USD and GDI tokens corresponding to this value will be charged.
				
Redemption Calculation Type: 
This configuration is required for platform fees calculation during the GDI Token redemption process. There are following calculations for Redemption.
Non refundable fee: Everytime when a user will place a Redemption request, there will be a one time non refundable fee charged to the user. This will be a fixed amount that can be configured from the admin's account. 
Redemption Process Fee: This fee will have similar configuration as we have for Token Purchasing platform fee configuration explained above. It can be a fixed amount, can be configured as a percentage or by range. Here the the detailed configuration Buy Calculation Type
Main Configuration
Gold Product Configuration: This is used for internally managing the Sale Order Line Product and is required by backend application. It’s a one time configuration.
Purchase threshold limit: 
This limit is used to limit the number of tokens purchased per transaction. If a user purchases above this limit, the request (when being processed by Tokenization Operator) will be sent to Gnosis in Phase-2. 
This Limit can be updated by clicking on the button “Update Purchase Limit”. A blockchain transaction will be required from platform Admin.

Redemption threshold Limit
It’s similar to Purchase threshold limit, This is referred to during the redemption process when the Redemption Operator finalises the processing of order.
Email Ids for Error Message: If there is any error in the system, an email will be sent to all the emails configured in this section with the error details to take necessary action
Meta transaction: In this section, configuration related to meta transaction  features are stored
Allow meta transaction: This is to enable/disable meta transaction feature on the platform
Transaction Speed: To do the meta transaction, the speed can be configured here. The values could be SAFE LOW, AVERAGE, FAST, FASTEST
Relayer contract address: The address of relayer contract where the meta transactions will be posted in case if the user is Fully or Partially subsidised. Refer Meta Transactions for more details.
Fee Handler Address: Address of wallet where the Meta Transaction fees will be transferred when the user has payment type of Partially Subsidised.
Banks: Here all the banks are configured to which payment can be made while purchasing GDI token using Bank Transfers. One bank can be set as default, countries with no bank account will see the default bank in the option to transfer the funds. 
Name
Swift Code
Email
Phone
Bank Address
Account Number
Countries Served: If the user’s country is listed here, the current bank details will be visible to transfer funds during bank transfer payment method while buying GDI Tokens
Default Bank: If this is checked then the current bank will be  visible to user if there is no matching bank based on user’s country
Countries: List of all countries stored in platform
Name
Currency
Country code
Type: This field stores whether a country is Grey, White or Blacklisted. 
The platform doesn’t allow customers from blacklisted countries. 
For grey listed country, user requires to provide certain additional documents during their KYC
Annual Threshold Limit: This limit is used to restrict GDI token purchase of user based on a country
Minimum Yearly Income: This is the minimum yearly income an individual should have
State Name: All the states the country has
Currency: All the currencies supported by platform will  be listed here
Name
Active: Whether it is active in system or not
Is CryptoCurrency:  whether the currency is cryptocurrency and if it is we show this option during GDI token purchase
Symbol Position: 
Symbol
Currency Unit
Decimal Places
Signup Options: Options available on sign up page 2 for user

Type: Professional Activity, Sector of activity, Range of Annual Revenues
Is Active: Set to True or false to keep the option active or inactive
Value: Value that will be visible under the Type of section i.e, under Professional Activity, Sector of activity, Range of Annual Revenues
Error Logs: Stores all the error details occurred in system
Traceback: The entire traceback of the error. It includes file name, line number and function calls
Error Message: Actual error message
Timestamp: Time when the error occurred
Document Master: It has all the documents configured for the platform e.g, Audit docs.
Business Documents: Master view for configuring docs
Name
Is Public Document
Requires Approval
Document Model where the document is visible
Mandatory
Documents: All the uploaded documents will be visible here
Document model to which this document was uploaded
Uploaded document file
Related object ID for the record
Web3 Base: All the Blockchain configuration is stored here
Transaction Verification: Stores details of different payment transaction occur on platform during purchase of GDI tokens
Transaction#
Payment Type
Timestamp
Model
Object ID
Signed
Amount
Network
State: 
Draft 
Pending
Failed
Manual Process
Admin approval
Success
Users: System Users are present here
Vault Users: Vaults users assigned to vault in Vault Locations are listed here
All Users: All System Users are present here
Transaction Logs: All the blockchain Transaction logs are stored here
Transaction Type: Detail of blockchain txn type
Transaction hash: Hash of transaction
ID: Database record ID 
Created on: Date when transaction is performed
KYC Records: Store KYC records for user present in platform
KYC Transaction: Main Menu to see the KYC data of user
Sumsub Applicant ID: Unique applicant id provided by sumsub for each user
Wallet Address
User: User whose KYC record this is.
Sumsub KYC Status: Status of KYC of the user
Settings: All the settings for the backend application is listed here
General settings
Users and Companies
Sumsub configuration: Configuration parameters for Sumsub including API Key
Technical
Email
Outgoing Mail server: Configure the outgoing mail details here
Automa	tion
Scheduled Actions: To activate/deactivate schedulers running to process different tasks like confirming Fiat/Crypto Payment, Sending emails etc. 

WorkFlows
This section lists the WorkFlows that will be implemented in the platform. Refer this Link for updated workflows.

User: Onboarding

 








User: Email Update Flow















User: Token Purchase (Credit/Debit Card, Crypto)

User: Token Purchase (Bank Payment Method)


User: Token Purchase (Cash Payment Method)























User: Update Wallet Address


Admin: Tokenization


Admin: Redemption


Admin: Update Threshold Limit


Admin: Update Platform Fee Account





Fees & Charges
Platform will be charging its commission . There will be a Menu to configure Platform fee. To Configure Fees, Admin user will navigate to:- 

Configuration menu → User Configuration → Fees Configuration

After Navigating the menu, there will be an option to configure following Fees.
Mint Fee - At the time of GDI Token Purchase this fee will be applicable on the Token Sales Orders. Users would be required to pay the fee if they would like to purchase GDI Tokens.
Redemption Fee - At the time of redemption, this fee will be charged to the User.  It could be configured as a percentage of the transaction amount or a fixed fee.
Detailed fee configuration is explained under Admin’s portal in this document.

Blockchain Details
Blockchain in use
Polygon - PoS will be used

Smart Contract
GDIToken Smart Contract: This smart contract will manage our GDI Token, offering features such as minting tokens backed by physical gold, transferring GDI Tokens, and redeeming GDI Tokens for physical gold.
Users Smart Contract: This contract will manage the KYC status of users' wallets. The KYC status will be utilized during the purchase (minting) process in the GDI Token smart contract.
Forwarder Smart Contract:  This smart contract manages the meta transactions (transactions that are sent using the relayer) requests and executes the operation in GDIToken smart contract.



Write and Read operations in GDIToken smart contract:-
Write Operations
grantRole: Admin of the role will grant the role to an account (as of now we have two type roles 1. Admin 2. Auditor). Admin role will be provided by the contract owner (DEFAULT_ADMIN_ROLE) and auditor role will be provided by the admin.
revokeRole: Admin of the role will revoke the role of an account. Roles are explained in the above section.
updatePlatformFeeRecipient: Allows the admin to update the platform fee account in which we are transferring the platformFee during the mint and redemption process.
updateRedemptionHandler: Allows the admin to update the redemption handler account by which we are burning the redeemed tokens.
updateCheckThresholdLimit: Allow the admin to change the use threshold config. For phase 1, we are not using the threshold limit config (Safe wallet).
updateMintThresholdConfig: Only authorizer (Safe wallet) can change the limit and authorizer address.
addVault: Allows the admin to add a new GOLDEFI vault.
uploadDocument: Allow the auditor of the contract to upload the documents for the vault audits.
mint: Facilitates the minting of tokens based on approval  of admin regarding the payment and also deducts the platform fees.
Parameters:-
vaultIDs (bytes32[])
uniqueOrderID (uint256)
user (address)
quantity (uint256)
platformFee (uint256)

Approve: Standard ERC20 function.
transfer: Standard ERC20 function.
transferFrom: Standard ERC20.
batchTransfer: A custom transfer function for handling the meta transactions for partially subsidised users. 
updateNonRefundableFee: Allows the admin to update the non refundable fees for redemption flow.
createRedemptionRequest: User will create the redemption request for redemption of their holdings into gold. We are deducting nonRefendableFees from the user.
reviewRedemptionRequest: Allows admin to update the vaults and shipping information against a raised redemption request.
processRedemptionRequest: User will process the redemption request and transfers the shipping fees as well as redeemable amount in the platform redemption handler wallet.
burnForRedemption: Platform wallet (redemption handler) will initiate this transaction for the burn tokens that are delivered to the user in the physical gold format.

Queries
allowance: Standard ERC20 read function.
balanceOf: Standard ERC20 read function.
decimals: Standard ERC20 read function.
getRoleAdmin: get the admin of any role.
hasRole: check if the account has the admin role.
name: Standard ERC20 read function.
symbol: Standard ERC20 read function.
totalSupply: Standard ERC20 read function.
For more queries visit -> https://www.oklink.com/amoy/address/0xc71a3fda6c888366daa008be45facd0e9184952a/contract#category=read  

Events
GDIToken Smart Contract Events

Transfer(address from, address to, uint256 value) -> Emitted when value tokens are moved from one account (from) to another (to).
Approval(address owner, address spender, uint256 value) -> Emitted when the allowance of a spender for an owner is set by a call to approve. value is the new allowance.
PlatformFeeRecipientUpdated(address indexed newPlatformFeeRecipient) -> Emitted when the platform account address is updated to a new value.
PlatformRedemptionHandlerUpdated(address indexed newPlatformRedemptionHandler) -> Emitted when the platform redemption handler is updated to a new value.
VaultRegistered(bytes32 indexed vaultID, string uri, string countryCode) -> Emitted when a new vault is added, identified by a unique vaultID with URI and country code of the vault.
MintThresholdConfigChanged(uint256 limit, address newAuthorizer) -> Emitted when the mint threshold config (limit or authorizer account) is updated.
MintOrderGenerated(uint256 indexed orderID, bytes32[] VaultID, address indexed user, uint256 quantity, uint256 platformFee, address platformFeeRecipient) -> Emitted when mint function executed and buy order generated.
RedemptionRequestGenerated(bytes32 id, uint256 amount, uint256 nonRefendableFee, address owner) -> Emitted when a redemption request created by the user.
RedemptionRequestProcessed(bytes32 id, uint256 shippingFee) -> Emitted when the redemption request is processed for a redemption id.
RedemptionRequestCompleted(bytes32 id) ->  Emitted when the redemption request is completed by the platform.
RoleGranted(role, account, sender) -> Emitted when a specific role is granted to a designated account. This event provides transparency into the assignment of roles within the access control system. The sender is the address initiating the role grant.
RoleRevoked(role, account, sender) -> Emitted when a specific role is revoked from a previously assigned account. This event indicates the removal of certain privileges or responsibilities associated with the specified role. The sender is the address initiating the role revocation.
RoleAdminChanged(role, previousAdminRole, newAdminRole) -> Emitted when the administrator role for a specific role is changed to a new administrator with the newAdminRole address. This event signifies a change in the authority responsible for managing permissions related to the specified role. It includes the address of the previous and new administrators.
AuditReportUploaded(uint256 docID, bytes32 vaultID, string uri, address auditor) -> Emitted when the auditor uploads  the audit report of a vault.


Users Contract Events

UserKycStatusUpdated(address indexed walletAddress, string kycID, bool kycStatus)-> Emitted when a new user is added to the system, identified by their walletAddress.
RoleGranted(role, account, sender) -> Emitted when a specific role is granted to a designated account. This event provides transparency into the assignment of roles within the access control system. The sender is the address initiating the role grant.
RoleRevoked(role, account, sender) -> Emitted when a specific role is revoked from a previously assigned account. This event indicates the removal of certain privileges or responsibilities associated with the specified role. The sender is the address initiating the role revocation.
RoleAdminChanged(role, previousAdminRole, newAdminRole) -> Emitted when the administrator role for a specific role is changed to a new administrator with the newAdminRole address. This event signifies a change in the authority responsible for managing permissions related to the specified role. It includes the address of the previous and new administrators.
Indexing Protocol
Subgraphs (Data will be indexed by Subgraph)
Webhooks with Subgraph

Technology Stack
Application
ReactJS,
Javascript
Python
PostgreSQL
Blockchain
Solidity

User Type
Below are the types of users involved in the system
Backend
GolDefi Admin
Auditors
Vaults

Frontend
Users
Distributors

Token Valuation
GDI Token valuation will be based on the Gold Price. 
One GDI Token will be equal to 0.001 Grams of Gold. If the rate of 999.99 fineness of Gold is 44.88 GBP per Gram the price of 1 GDI Token will be 0.04488 GBP.
Similarly, as the Gold price keeps changing the value of GDI Token will also keep changing.

Notes
One GDI token is stored as 100 value in blockchain.

