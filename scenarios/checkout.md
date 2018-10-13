# Checkout

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

Our in-resort pricing team have created a set of promotions as an incentive for our customers:

* If you spend over £500 in a single transaction, you get 15% off of the total price.

* If you hire a car, plus purchase a wedding - the car hire is free.

* If you hire 2 or more sunbeds for 7 days - the price drops to £75.

The customer adds various products and services to the basket within the app.  On checkout - the total of all the items in the basket is calculated via an API and the final total returned to the app and the customer.  Note that the items can appear in any order.

Because our promotional rules will change frequently, they need to be flexible!

The interface to our checkout service (in Ruby) looks like this:

```ruby
co = Checkout.new(promotion_rules)
co.add(product)
co.add(product)
price = co.total
```

Implement a checkout service that fulfils these requirements.

## Test data

```bash
Basket: 0003,0001
Final price: £225.00

Basket: 0001,0002
Final price: £180.00

Basket: 0001,0005,0003
Final price: £500.00

Basket: 0001,0003,0004,0005,0004
Final price: £510.00

Basket: 0001,0007,0007,0007,0007
Final price: £400.00

Basket: 0004,0007,0002,0003,0001,0007,0005,0004
Final price: £705.50
```
