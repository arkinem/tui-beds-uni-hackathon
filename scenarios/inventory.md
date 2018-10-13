# Inventory

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

As you can see - not all products and services are unlimited - availability is restricted.

As a customer uses the in-resort app - the availability of the various products and services needs to be updated in real time.  So that if a product or service is no longer available this is indicated to the customer and they can no longer add that product/service to the in-app basket.  This can happen at any time.

When a customer successfully checks out within the app - availability is reduced accordingly.  Also, in real time.  However, you need to check the availability of each product/service in the customers basket at checkout.  If any of the products/services the customer has chosen is no longer available, you need to alert the customer and cancel the checkout process.

As customers return home, or their hire duration/wedding has ended - the product/service is returned to the supplier.  At this point the availability of each product/service needs updating (in real time).  This can also happen at any time.

You have been asked to implement the inventory service above.  It needs to include the app and the inventory as services and should use either: RabbitMQ, Redis or AWS SQS event messaging to communicate between the two.
