# Payment
> A payment service for the in-resort app

TUI have an in-resort app that can be downloaded by its customers.  This app allows our customers to book and pay for any of the additional services and products we offer at our hotels.

Here is a sample of some products:

```bash
Code | Name                                    | Price   | Availability
-----|-----------------------------------------|---------|-------------
0001 | Taxi Transfer - Airport to Hotel Return | £100.00 | Unlimited
0002 | Baby Cot Hire - 7 Days                  | £80.00  | 10
0003 | Car Hire - 7 Days                       | £125.00 | 10
0004 | Attraction Ticket - Per Person          | £50.00  | Unlimited
0005 | Wedding                                 | £400.00 | 7
0006 | Excursion - Per Person                  | £40.00  | Unlimited
0007 | Sunbed Hire - 7 Days                    | £100.00 | 100
```

You have been asked to implement a payment service for the app.  This service is API-driven.

Your service needs to request the credit card details of the customer within the app.  Send those (securely) over to the payment service.

The payment service will then contact the credit card issuer for authorisation.  All credit card issuers respond with one of 2 responses:

* Authorised, i.e. the payment has been made on the customers credit card and the total deposited into the service providers account

* Failure, i.e. there is insufficient funds in the customers account, or the addition of the funds into the service providers account has failed.  You can assume there are no other causes of failure (e.g. communications, device failure).

Design and build the payment service - responses from credit card issuers can be faked or randomised.

Design and build the API used between the app and the payment service.  As you will be taking credit card details this API needs to be secure, as does the transport of data.  The choice of API security technique is left to you.  However, transport must be secured to AES-256 standard - in both directions.

As an additional complication - the payment API itself needs to be versioned, so that systems using the API are not affected by breaking changes made in other versions.
