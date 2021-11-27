---
description: Start working with our eSIM API.
---

# Using the API

## Getting Started

To get started using the API:

1. [Create an account](https://esims.dataplans.io/signup)
2. View [API docs](https://app.dataplans.io/docs/v1#/) and / or [Postman example](https://www.getpostman.com/collections/5f4159854d5cf32ae41b)
3. Agree to the [User Agreement](https://dataplans.io/user-agreement/)
4. Fund your account and purchase an eSIM

### **Sandbox Environment**

After login, you will be in the sandbox testing  area, with test credit and eSIMs.  With in the sandbox account you can:

1. Make a deposit of funds
   1. Navigate to Billing > Make External Deposit
2. Make a eSIM purchase
   1. Go to Products and choose one of the available choices
   2. Go to Purchases and review purchase history
3. Generate your API Key
4. Make API calls&#x20;

Calling the sandbox API is done with the follwing endpoint:

```
https://sandbox.dataplans.io/api/v1
```

Additionally,  you can interact with the [Swagger API docs in sandbox](https://sandbox.dataplans.io/docs/v1#/) with your API Key. Click the Authorize button and enter your API key to work with the API within the Swagger doc.

![](<.gitbook/assets/Screen Shot 2021-01-14 at 5.41.02 PM.png>)

### **Live Environment**

Once satisfied with your process, you can switch to the live environment.  You can use the same API or roll a new one.  The API key is the same for both Sandbox and Live enviroments.&#x20;

In the live environment use the following endpoint:

```
https://app.dataplans.io/api/v1
```

You can interact with the [Swagger API docs in live mode](https://app.dataplans.io/docs/v1#/) with your API Key.

### Run In Postman

Postman is a great way to work with our API and you can [import our collection](https://www.getpostman.com/collections/5f4159854d5cf32ae41b) into your project.&#x20;



## eSIM Payload

Purchasing an eSIM is possible once you have a positive account balance.  When requesting the eSIM, your balance is deducted according to your current monthy tier.&#x20;

### API Delivery

When purchasing via API, you will receive a JSON eSIM payload.  This provides both the manual entry data as well as the QR code for adding an eSIM.

```
{
  "purchase": {
    "purchaseId": "07045e84-a075-49f9-8eeb-f2f537d1f8eb",
    "planSlug": "tourist-sim-dtac",
    "retail": "299.00",
    "paid": "284.65",
    "currency": "THB",
    "purchasedAt": "2020-02-06T08:54:06.047Z",
    "esim": {
      "manual1": "ais.prod.ondemandconnectivity.com",
      "manual2": "hidden",
      "optionalCode": "",
      "phone": "0800773477",
      "serial": "8782979238792973",
      "expiryDate": "2020-02-06T08:18:20.022Z",
      "qrCodeString": "LPA:1$ais.prod.ondemandconnectivity.com$SEW7JEBMFGPRVSPD",
      "qrCodeDataUrl": "data:image/png;base64,iVBORw0KGgoAAAA..."
    }
  },
  "availableBalance": "15000"
}
```

| **Parameters** | Description                                                           |
| -------------- | --------------------------------------------------------------------- |
| manual1        | String for manual entry of SM-DP+ Address                             |
| manual2        | Sring for Activation Code                                             |
| optionalCode   | Confirmation Code. Used with some eSIM providers                      |
| phone          | eSIM phone number                                                     |
| serial         | eSIM Serial number                                                    |
| expiryDate     | eSIM expiry date                                                      |
| qrCodeString   | QR code payload string. Populate your custome QR code with this data. |
| qrCodeDataUrl  | QR code PNG imag                                                      |

###

{% swagger baseUrl="https://app.dataplans.io/api/v1" path="/plan/{slug}" method="get" summary="Plan by Slug" %}
{% swagger-description %}
Fetch plan details with slug
{% endswagger-description %}

{% swagger-parameter in="path" name="slug" type="string" %}
Sample value:

_sim2fly-asia _

 
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "id": 0,
  "slug": "sim2fly-asia",
  "name": "SIM2Fly Asia",
  "period": 8,
  "capacity": 6000,
  "capacityUnit": "MB",
  "retailPrice": "399.00",
  "priceCurrency": "THB",
  "prepaidCredit": 0,
  "prepaidCurrency": "THB",
  "reloadable": true,
  "phoneNumber": true,
  "active": true,
  "operator": {
    "slug": "ais",
    "name": "AIS"
  },
  "region": {
    "slug": "asia",
    "name": "Asia"
  },
  "countries": [
    {
      "countryCode": "AU",
      "countryName": "Australia"
    }
  ]
Get}
```
{% endswagger-response %}
{% endswagger %}



