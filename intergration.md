---
description: Purchasing eSIMs with Dataplans.io
---

# Using the Web App

Dataplans.io is an eSIM API platform and management backend.  Currently proving eSIMs from 2 carriers: AIS and DTAC.

![eSIM Dashboard](.gitbook/assets/Screen\_Shot\_2021-01-18\_at\_11\_52\_36.png)

## Getting Started

To get started:

1. [Create an account at esims.dataplans.io](https://esims.dataplans.io/signup) &#x20;
2. Make a test deposit - under Billing > [Make External Deposit](https://esims.dataplans.io/dashboard/billing/wires)
3. Make a test purchase in the Sandbox area - under [Products](https://esims.dataplans.io/dashboard/products)
4. Switch to **live mode**
5. Agree to the [User Agreement](https://dataplans.io/user-agreement/) and complete Identity Verification
6. Fund your account and purchase an eSIM

### **Sandbox Environment**

![Sandbox dashboard for making test purchases](<.gitbook/assets/Screen Shot 2021-01-27 at 09.28.30.png>)

After login, you will be in the sandbox testing  area, with test credit and eSIMs.  With in the sandbox account you can:

1. Make a deposit of test funds
   1. Navigate to Billing > Make External Deposit
2. Make a test  eSIM purchase
   1. Go to Products and choose one of the available choices
   2. Go to Purchases and review purchase history



### **Live Environment**

Once satisfied with your process, you can switch to the live environment.  You can use the same API key or roll a new one.  The API key is the same for both Sandbox and Live environments, but the base URL has a different sandbox and live subdomain.



## eSIM Delivery

Purchasing an eSIM is possible once you have a positive account balance.  When requesting the eSIM, your balance is deducted according to your current monthly tier.&#x20;

###

### Web app delivery&#x20;

When purchasing via the dashboard, you will receive the QR code and additional metadata. QR code can be delivered to a customer as is, or recreated as a new QR code.

![QR code payload purchased in the dashboard](<.gitbook/assets/Screen Shot 2021-01-15 at 17.50.30.png>)

Provided is the connection string data, serial number and any additional data like phone or connection code.  Manual entry codes also provided.&#x20;



| **Parameters** | Description                                                            |
| -------------- | ---------------------------------------------------------------------- |
| manual1        | String for manual entry of SM-DP+ Address                              |
| manual2        | String for Activation Code                                             |
| optionalCode   | Confirmation Code. Used with some eSIM providers                       |
| phone          | eSIM phone number                                                      |
| serial         | eSIM Serial number                                                     |
| expiryDate     | eSIM expiry date                                                       |
| qrCodeString   | QR code payload string. Populate your customer QR code with this data. |
| qrCodeDataUrl  | QR code PNG imag                                                       |

###
