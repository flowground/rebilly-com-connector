# ![LOGO](logo.png) Rebilly **flow**ground Connector

## Description

A generated **flow**ground connector for the Rebilly API (version 2.1).

Generated from: https://api.apis.guru/v2/specs/rebilly.com/2.1/swagger.json<br/>
Generated at: 2019-05-07T17:43:48+03:00

## API Description

# Introduction
The Rebilly API is built on HTTP.  Our API is RESTful.  It has predictable
resource URLs.  It returns HTTP response codes to indicate errors.  It also
accepts and returns JSON in the HTTP body.  You can use your favorite
HTTP/REST library for your programming language to use Rebilly's API, or
you can use one of our SDKs (currently available in [PHP](https://github.com/Rebilly/rebilly-php)
and [Javascript](https://github.com/Rebilly/rebilly-js-sdk)).

We have other APIs that are also available.  Every action from our [app](https://app.rebilly.com)
is supported by an API which is documented and available for use so that you
may automate any workflows necessary.  This document contains the most commonly
integrated resources.

# Authentication
When you sign up for an account, you are given your first API key.
You can generate additional API keys, and delete API keys (as you may
need to rotate your keys in the future). You authenticate to the
Rebilly API by providing your secret key in the request header.

Rebilly offers three forms of authentication:  secret key, publishable key, JSON Web Tokens, and public signature key.
- [Secret API key](#section/Authentication/SecretApiKey): used for requests made from the server side. Never share these keys. Keep them guarded and secure
- [Publishable API key](#section/Authentication/PublishableApiKey): used for requests from the client side. For now can only be used on the [Tokens resource](#tag/Payment-Tokens%2Fpaths%2F~1tokens%2Fpost)
- [JWT](#section/Authentication/JWT): short lifetime tokens that can be assigned a specific expiration time

Never share your secret keys. Keep them guarded and secure.

<!-- ReDoc-Inject: <security-definitions> -->

# PHP SDK
For all PHP SDK examples provided in this spec you will need to configure `$client`.
You may do it like this:

```php
$client = new Rebilly\Client([
    'apiKey' => 'YourApiKeyHere',
    'baseUrl' => 'https://api.rebilly.com',
]);
```

# Using filter
Rebilly provides collections filtering. You can use `?filter` param on collection to define which records should be shown in the response.

Here is filter format description:

- Fields and values in filter are separated with `:`: `?filter=firstName:John`.

- Fields in filter are separated with `;`: `?filter=firstName:John;lastName:Doe`.

- You can use multiple values using `,` as values separator: `?filter=firstName:John,Bob`.

- To negate the filter use `!`: `?filter=firstName:!John`. Note that you can negate multiple values like this: `?filter=firstName:!John,Bob`. This filter rule will exclude all Johns and Bobs from the response.

- You can use range filters like this: `?filter=amount:1..10`.

- You can use gte (greater than or equals) filter like this: `?filter=amount:1..`, or lte (less than or equals) than filter like this: `?filter=amount:..10`.

- You can create some [predefined values lists](https://rebilly.github.io/RebillyUserAPI/#tag/Lists) and use them in filter: `?filter=firstName:@yourListName`. You can also exclude list values: `?filter=firstName:!@yourListName`


## Authorization

Supported authorization schemes:
- API Key- API Key- API Key
## Actions

### Retrieve a list of ThreeDSecure entries

*Tags:* `3D Secure`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a ThreeDSecure entry

> Create a ThreeDSecure entry

*Tags:* `3D Secure`

### Retrieve a ThreeDSecure entry

> Retrieve a ThreeDSecure entry with specified identifier string

*Tags:* `3D Secure`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of Attachments

> Retrieve a list of Attachments

*Tags:* `Files`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `expand` - _optional_ - Expand response to get full related object intead of ID.  See the expand guide for more info.
* `fields` - _optional_ - Limit the returned fields to the list specified, separated by comma.  Note that id is always returned.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).

### Create an Attachment

> Create an Attachment

*Tags:* `Files`

### Delete an Attachment

> Delete the Attachment with predefined identifier string

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve an Attachment

> Retrieve a Attachment with specified identifier string

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Update the Attachment with predefined ID

> Update the Attachment with predefined ID

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Read current authentication options

> Read current authentication options

*Tags:* `Customer Authentication`

### Change authentication options

> Change options

*Tags:* `Customer Authentication`

### Retrieve a list of auth tokens

> Retrieve a list of auth tokens

*Tags:* `Customer Authentication`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Login

> Login a user (customer)

*Tags:* `Customer Authentication`

### Logout a user

> Logout a user

*Tags:* `Customer Authentication`

#### Input Parameters
* `token` - _required_ - The token identifier string

### Verify

> Verify an authentication token

*Tags:* `Customer Authentication`

#### Input Parameters
* `token` - _required_ - The token identifier string

### Retrieve a list of bank accounts

> Retrieve a list of Bank Accounts

*Tags:* `Bank Accounts`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a Bank Account

> Create a Bank Account

*Tags:* `Bank Accounts`

### Retrieve a Bank Account

> Retrieve a Bank Account with specified identifier string

*Tags:* `Bank Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a BankAccount with predefined ID

> Create or update a BankAccount with predefined identifier string

*Tags:* `Bank Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Deactivate a Bank Account

> Deactivate a Bank Account

*Tags:* `Bank Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of blacklists

> Retrieve a list of blacklists

*Tags:* `Blacklists`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a blacklist

> Create a blacklist

*Tags:* `Blacklists`

### Delete a blacklist

> Delete a blacklist with predefined identifier string

*Tags:* `Blacklists`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a blacklist

> Retrieve a blacklist with specified identifier string

*Tags:* `Blacklists`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a blacklist with predefined ID

> Create a blacklist with predefined identifier string

*Tags:* `Blacklists`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of contacts

> Retrieve a list of contacts

*Tags:* `Contacts`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a contact

> Create a contact

*Tags:* `Contacts`

### Delete a contact

> Delete a contact with predefined identifier string

*Tags:* `Contacts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a contact

> Retrieve a contact with specified identifier string

*Tags:* `Contacts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create or update a contact with predefined ID

> Create or update a contact with predefined identifier string

*Tags:* `Contacts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of coupons

> Retrieve a list of coupons

*Tags:* `Coupons`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).

### Create a coupon

> Create a coupon

*Tags:* `Coupons`

### Retrieve a list of coupon redemptions

*Tags:* `Coupons`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).

### Redeem a coupon

> Redeem a coupon

*Tags:* `Coupons`

### Retrieve a coupon redemption with specified identifier string

*Tags:* `Coupons`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Cancel a coupon redemption

*Tags:* `Coupons`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a coupon

> Retrieve a coupon with specified redemption code string

*Tags:* `Coupons`

#### Input Parameters
* `redemptionCode` - _required_ - The Coupon's redemption code

### Create or update a coupon with predefined redemption code

> Create or update a coupon with predefined redemption code

*Tags:* `Coupons`

#### Input Parameters
* `redemptionCode` - _required_ - The Coupon's redemption code

### Set a coupon's expiration time.

> Set a coupon's expiry time with the specified redemption code.<br/>
> The expiredTime of a coupon must be greater than its issuedTime.<br/>
> This cannot be performed on expired coupons.

*Tags:* `Coupons`

#### Input Parameters
* `redemptionCode` - _required_ - The Coupon's redemption code

### Retrieve a list of credentials

> Retrieve a list of credentials

*Tags:* `Customer Authentication`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a credential

> Create a credential

*Tags:* `Customer Authentication`

### Delete a credential

> Delete a credential with predefined identifier string

*Tags:* `Customer Authentication`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a credential

> Retrieve a credential with specified identifier string

*Tags:* `Customer Authentication`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create or update a credential with predefined ID

> Create or update a credential with predefined identifier string

*Tags:* `Customer Authentication`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve Custom Fields

> Retrieve a schema of Custom Fields for the given resource type

*Tags:* `Custom Fields`

#### Input Parameters
* `resource` - _required_ - The resource type string
    Possible values: customers, payment-cards, subscriptions, transactions, websites, contacts, products.

### Retrieve a Custom Field

> Retrieve a schema of the given Custom Field for the given resource type

*Tags:* `Custom Fields`

#### Input Parameters
* `resource` - _required_ - The resource type string
    Possible values: customers, payment-cards, subscriptions, transactions, websites, contacts, products.
* `name` - _required_ - The custom field's identifier string

### Create or alter a Custom Field

> Create or alter a schema of the given Custom Field for the given resource type.

*Tags:* `Custom Fields`

#### Input Parameters
* `resource` - _required_ - The resource type string
    Possible values: customers, payment-cards, subscriptions, transactions, websites, contacts, products.
* `name` - _required_ - The custom field's identifier string

### Retrieve a list of customers

> Retrieve a list of customers

*Tags:* `Customers`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `expand` - _optional_ - Expand response to get full related object intead of ID.  See the expand guide for more info.
* `fields` - _optional_ - Limit the returned fields to the list specified, separated by comma.  Note that id is always returned.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).
* `Accept` - _optional_ - The response media type
    Possible values: application/json, text/csv.

### Create a customer

> Create a customer

*Tags:* `Customers`

### Retrieve a customer

> Retrieve a customer with specified identifier string

*Tags:* `Customers`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a customer with predefined ID

> Create a customer with predefined identifier string

*Tags:* `Customers`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Delete a Lead Source for a customer

> Delete a Lead Source that belongs to a certain customer

*Tags:* `Customers`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a customer's Lead Source

> Retrieve a Lead Source of given customer

*Tags:* `Customers`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a Lead Source for a customer

> Create a Lead Source for a customer

*Tags:* `Customers`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of disputes

> Retrieve a list of disputes

*Tags:* `Disputes`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a dispute

> Create a dispute

*Tags:* `Disputes`

### Retrieve a dispute

> Retrieve a dispute with specified identifier string

*Tags:* `Disputes`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create or update a Dispute with predefined ID

> Create or update a Dispute with predefined identifier string

*Tags:* `Disputes`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Get matched rules for the dispute

*Tags:* `Disputes`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of files

> Retrieve a list of files

*Tags:* `Files`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `expand` - _optional_ - Expand response to get full related object intead of ID.  See the expand guide for more info.
* `fields` - _optional_ - Limit the returned fields to the list specified, separated by comma.  Note that id is always returned.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).

### Create a file

> Additionally, a file can be sent with:<br/>
>  - multipart/form-data POST request: in this case all property names are the same as the JSON ones (`file` is an uploaded file)<br/>
>  - file body request: the file body is sent as the request body, with the appropriate `Content-Type`. No aditional<br/>
>  properties can be set along the request data<br/>
> <br/>
> The following file types only are allowed:<br/>
>  - jpg<br/>
>  - png<br/>
>  - gif<br/>
>  - pdf<br/>
>  - mp3<br/>
> <br/>
> <br/>
> If using a Publishable Api Key, only private files can be created. The files can later on be modified or used using<br/>
>  a secret API key.

*Tags:* `Files`

### Delete a File

> Delete the File with predefined identifier string

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a File Record

> Retrieve a File with specified identifier string

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Update the File with predefined ID. Note that file can be uploaded with POST only.

> Update the File with predefined ID

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Download a file

> Download a file

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Download image in specific format

> Download image in specific format. Images are converted server-side

*Tags:* `Files`

#### Input Parameters
* `id` - _required_ - The resource identifier string
* `extension` - _required_ - File extension which also indicates the desired file format
    Possible values: .png, .jpg, .gif.

### Retrieve a list of invoices

> Retrieve a list of invoices

*Tags:* `Invoices`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `Accept` - _optional_ - The response media type
    Possible values: application/json, text/csv.

### Create an invoice

> Create an invoice

*Tags:* `Invoices`

### Retrieve an invoice

> Retrieve an invoice with specified identifier string

*Tags:* `Invoices`

#### Input Parameters
* `Accept` - _optional_ - The response media type
    Possible values: application/json, application/pdf.

### Create or update an invoice with predefined ID

> Create or update an invoice with predefined identifier string

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Abandon an invoice

> Abandon an invoice with specified identifier string

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Issue an invoice

> Issue an invoice with specified identifier string

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve invoice items

> Retrieve an invoice items with specified invoice identifier string

*Tags:* `Invoices`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create an invoice item

> Create an invoice item

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Get matched rules for the invoice

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Void an invoice

> Void an invoice with specified identifier string

*Tags:* `Invoices`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of KYC documents

> Retrieve a list of KYC documents

*Tags:* `KYC Documents`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).
* `Accept` - _optional_ - The response media type
    Possible values: application/json.

### Create a KYC Document

> Create a KYC Document

*Tags:* `KYC Documents`

### Retrieve a KYC Document

> Retrieve a KYC document with specified identifier string

*Tags:* `KYC Documents`

#### Input Parameters
* `Accept` - _optional_ - The response media type
    Possible values: application/json.

### Create or update a KYC document with predefined ID

> Create or update a KYC document with predefined identifier string

*Tags:* `KYC Documents`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Accept a KYC document

> Manually override automated status and accept the document

*Tags:* `KYC Documents`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Reject a KYC document

> Manually override automated status and reject the document

*Tags:* `KYC Documents`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of tokens

> Retrieve a list of tokens

*Tags:* `Customer Authentication`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a Reset Password Token

> Create a Reset Password Token

*Tags:* `Customer Authentication`

### Delete a Reset Password Token

> Delete a Reset Password Token with predefined identifier string

*Tags:* `Customer Authentication`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a Reset Password Token

> Retrieve a Reset Password Token with specified identifier string

*Tags:* `Customer Authentication`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of Payment Cards

> Retrieve a list of Payments Cards

*Tags:* `Payment Cards`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a Payment Card

> Create a Payment Card

*Tags:* `Payment Cards`

### Retrieve a Payment Card

> Retrieve a Payment Card with specified identifier string

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Update a payment card's values

> Update any of the payment card's values except for the pan

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a payment card with predefined ID

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Authorize a Payment Card

> Authorize a Payment Card

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Deactivate a Payment Card

> Deactivate a Payment Card

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Get matched rules for the payment card

*Tags:* `Payment Cards`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a Payment Instrument validation

> Retrieve a Payment Instrument validation with specified identifier string

*Tags:* `Payment Instrument Validation`

### Validate a payment instrument

> Validate a payment instrument

*Tags:* `Payment Instrument Validation`

### Retrieve a list of validated payment instruments

> Retrieve a list of validated payment instruments

*Tags:* `Payment Instrument Validation`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Retrieve a payment list

> Retrieve a payment list

*Tags:* `Payments`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `Accept` - _optional_ - The response media type
    Possible values: application/json, text/csv.

### Create a payment

> Create a payment

*Tags:* `Payments`

### Retrieve a payment

> Retrieve a payment with specified identifier string

*Tags:* `Payments`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a payment with predefined ID

> Make a payment with predefined identifier string

*Tags:* `Payments`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of PayPal accounts

> Retrieve a list of PayPal Accounts

*Tags:* `PayPal Accounts`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a PayPal Account

> Create a PayPal Account

*Tags:* `PayPal Accounts`

### Retrieve a PayPal Account

> Retrieve a PayPal Account with specified identifier string

*Tags:* `PayPal Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a PayPal account with predefined ID

*Tags:* `PayPal Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Activate a PayPal Account

> Activate a PayPal Account

*Tags:* `PayPal Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Deactivate a PayPal Account

> Deactivate a PayPal Account

*Tags:* `PayPal Accounts`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of plans

> Retrieve a list of plans

*Tags:* `Plans`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a plan

> Create a plan

*Tags:* `Plans`

### Delete a Plan

> Delete a Plan with predefined identifier string

*Tags:* `Plans`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a plan

> Retrieve a plan with specified identifier string

*Tags:* `Plans`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create or update a Plan with predefined ID

> Create or update a Plan with predefined identifier string

*Tags:* `Plans`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of products

> Retrieve a list of products

*Tags:* `Products`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a Product

> Create a Product

*Tags:* `Products`

### Delete a product

> Delete a product with predefined identifier string

*Tags:* `Products`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a product

> Retrieve a product with specified identifier string

*Tags:* `Products`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a product with predefined ID

> Create a product with predefined identifier string

*Tags:* `Products`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a scheduled payment list

> Retrieve a scheduled payment list

*Tags:* `Payments`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Retrieve a scheduled payment

> Retrieve a payment with specified identifier string

*Tags:* `Payments`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Update pending payment

*Tags:* `Payments`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of shipping zones

> Retrieve a list of shipping zones

*Tags:* `Shipping Zones`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a Shipping Zone

> Create a Shipping Zone

*Tags:* `Shipping Zones`

### Delete a shipping zone

> Delete a shipping zone with predefined identifier string

*Tags:* `Shipping Zones`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a shipping zone

> Retrieve a shipping zone with specified identifier string

*Tags:* `Shipping Zones`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create a shipping zone with predefined ID

> Create a shipping zone with predefined identifier string

*Tags:* `Shipping Zones`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of cancellations

> Retrieve a list of cancellations for all subscriptions

*Tags:* `Subscriptions`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Cancel a subscription

> Cancel a subscription or preview the cancellation parameters before that

*Tags:* `Subscriptions`

### Delete a cancellation

> Delete a subscription's cancellation. Only draft can be deleted.

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a subscription cancellatopn

> Retrieve a subscription cancellatopn with specified identifier string

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Cancel a subscription

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of reactivations

> Retrieve a list of reactivations for all subscriptions

*Tags:* `Subscriptions`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Reactivate a subscription

*Tags:* `Subscriptions`

### Retrieve a subscription reactivation

> Retrieve a subscription reactivation with specified identifier string

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of subscriptions

> Retrieve a list of subscriptions

*Tags:* `Subscriptions`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `Accept` - _optional_ - The response media type
    Possible values: application/json, text/csv.

### Create a subscription

> Create a subscription

*Tags:* `Subscriptions`

### Retrieve a subscription

> Retrieve a subscription with specified identifier string

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Create or update a subscription with predefined ID

> Create or update a subscription with predefined identifier string

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Change a subscription's plan

> Change a subscription's plan and designate when and if there should be pro rata credits given.

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Issue an interim invoice for a subscription

> Issue an interim invoice for a subscription, typically used in conjunction with plan changes and pro rata adjustments.<br/>
> This process creates an invoice, adds the subscription's line items to the invoice, and issues the invoice, and applies<br/>
> payment to it if a transaction id is supplied.

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Get matched rules for the subscription

*Tags:* `Subscriptions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a list of tokens

> Retrieve a list of tokens

*Tags:* `Payment Tokens`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset

### Create a payment token

> Create a token

*Tags:* `Payment Tokens`

### Retrieve a token

> Retrieve a token with specified identifier string

*Tags:* `Payment Tokens`

#### Input Parameters
* `token` - _required_ - The token identifier string

### Expire a token

> Expire a token

*Tags:* `Payment Tokens`

#### Input Parameters
* `token` - _required_ - The token identifier string

### Retrieve a list of transactions

> Retrieve a list of transactions

*Tags:* `Transactions`

#### Input Parameters
* `limit` - _optional_ - The collection items limit
* `offset` - _optional_ - The collection items offset
* `filter` - _optional_ - The collection items filter requires a special format.
Use "," for multiple allowed values.  Use ";" for multiple fields.
See the [filter guide](https://rebilly.github.io/RebillyAPI/#section/Using-filter) for more options and examples about this format.

* `q` - _optional_ - The partial search of the text fields.
* `sort` - _optional_ - The collection items sort field and order (prefix with "-" for descending sort).
* `Accept` - _optional_ - The response media type
    Possible values: application/json, text/csv.

### Retrieve a Transaction

> Retrieve a Transaction with specified identifier string

*Tags:* `Transactions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Cancel a pending or suspended transaction

> Cancel a scheduled transaction. Once handled a transaction cannot be canceled

*Tags:* `Transactions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Retrieve a Transaction Gateway Logs

> Retrieve Gateway communication Logs for Transaction with specified identifier string

*Tags:* `Transactions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Get matched rules for the transaction

*Tags:* `Transactions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

### Refund a Transaction

> Refund a Transaction with specified identifier string.<br/>
> Note that the refund will be in the same currency as the original transaction.

*Tags:* `Transactions`

#### Input Parameters
* `id` - _required_ - The resource identifier string

## License

**flow**ground :- Telekom iPaaS / rebilly-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
