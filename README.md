# Bolt Fraud Analysis

# Introduction
Bolt is an Estonian mobility company that offers vehicle for hire, micromobility, car-sharing, and food delivery services headquartered in Tallinn and operating in over 400 cities in over 45 countries[2][3] in Europe, Africa, Western Asia and Latin America. The company has 100 million customers globally [3] and more than 2.5 million drivers use the Bolt Driver platform to offer rides. Source - [**_wikipedia_** ](https://en.wikipedia.org/wiki/Bolt_(company))

# **Problem Statement**
About 40% of our transactions are cashless - meaning we are charging clients and paying majority of the charge to the driver every week (withholding our 15-25% commissions).

We always pay the driver and take the risk for collecting the funds from the client. Luckily, we have basic filters to block users from making multiple fraudulent transactions and find groups of fraudulent users using the same devices or cards. 

# **Goal**
Stop first timer from doing fraudulent transaction and develop a top 2-5 solotions will help reduce the percent of failed payments.

# Goals & Business Questions

* Findout the pattern in the fraudulent transaction
  * what are the type of fraud transaction?
  * What day and weekday do fraud transaction usually happened?
  * When does fraud transaction usually happened?
  * Device identification?
  * Country
  
* Findout What model of machine learning that's the best recall score to   predict a fraud transaction
  * What is the best machine learning model to predict fraud transaction
  
  # Data Dictionaries and MetaData
* created – time when the 1st time order request was created.
* device_name – name of the device used to make order
* device_os_version – version of the device OS
* country – 2 char country code
* city_id – internal system city ID (not relevant which one is which)
* lat – latitude of the pickup spot for the order
* lng – longitude of the pickup spot for the order
* real_destination_lat – latitude of the destination for the order
*  real_destination_lng – longitude of the destination for the order
*  user_id – internal user ID
*  order_id – internal order ID
* order_try_id – internal order try ID (order tries happen before client and driver are matched to an order)
*  distance – driver distance to the client pickup location, in meters
*  ride_distance – trip distance in meters
*  price – price charged to client, can be lower than “ride_price” if client had a discount, currencies vary and are undefined
*  ride_price – calculated price of the final trip, currencies vary and are undefined
*  price_review_status – “Price review” is when we send “ride_price” to be audited by human to check for system errors. 99% of orders are final and should have “ok” already set. There might be some that are still in pending states, most likely you can discard those.
*  price_review_reason – automatic or manual reason for the price review to be requested.
*  is_successful_payment – 1 means order was charged successfully, 0 mean it has failed (including after all attempts to re-charge)
*  name – card details, irrelevant.
*  card_bin – details on card BIN.
*  failed_attempts – number of failed order attempts before this 1st finished order.

# Conclusion

* Discounts should be given to every first-time rider as cases of failed payments are assumed to be caused by the ride price being higher than the anticipated price by the rider.​

* Overall, the majority of the failed payments happened in the following countries such as NG, RS, UA, MX, GH, and SA and they are due mainly to high ride prices and ride distance. Further looking at the price review reason, it is observed that most of these failed payments are a result of prices being too high and there are also cases where the ride prices are zero.


* Also, the highest volumes of the failed transactions account for about 7.6% of the 79,033 failed payments that occurred between hours 1 pm and 11 pm. The findings did show that our analysis before shows that the fraud transactions are usually constant during any time of the day which is very frequent on Thursdays and Fridays, a majority in the month of July and December.


# Recommendation
* Discounts should be given to every first-time rider as cases of failed payments are assumed to be caused by the ride price being higher than the anticipated price by the rider.​

* Providing ride-sharing options in cities/countries where failed transactions are frequent because the longer the distance the higher the ride price. This will lessen the cost effect by sharing ride fares among riders.​

* Introduction of an internal wallet to be funded with an allow minimum amount for all first-time riders before requesting a ride which will reduce the problem of fraudulent transactions. ​

* Relying on data, monitor time and places where surge tends to be high and direct drivers from low demand areas to high demand areas.​

* Partner with Integrated Mobility As Service companies to help deploy more rides and drivers in cities where ride prices are usually high as a result of the surge and ride distance in order to provide cheaper rides.​


