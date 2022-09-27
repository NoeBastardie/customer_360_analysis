Data Analysis description and reasons 

Questions : What is important to analyze in your customer database (DB) ? How did I proceed to analyze
yours ?


To understand what is important to analyze in a customer database, you first need to answer
this question : What is the purpose of customer analytics ?


The purpose of customer analytics is to better understand customer behavior and drive
better business outcomes. Customer analytics helps you understand who your
customers are and how they behave. This information can be used to improve customer
experience, increase sales, and retain customers.


Now that we know the purpose of customer analytics, we can focus on what is important to
analyze. The goal of the analysis will be to answer the two questions mentioned above :
- Who are your customers ?
- How do they behave ?


1. Who are your customers ?


To answer the first question, we can split it in several minor questions about the customer
that will help the analysis :
- How old are your customers ?
- Where do they come from ?
- What gender are they ?
- Have they been customers for a long time ?


Thanks to this list of questions we now know which information we need to obtain in order to
analyze who our customers are. We will need :
- The age of the customer : that is easy to obtain here as we have the birth date of
customers. To better view the age repartition of our customer we will create
categories (buckets) with young, middle age and old adults.
- The location of our customer : we will use their zip code.
- The gender of our customers : we will see here that the civility data that we have is
not clean enough to be useful and we will use the first name to deduce the gender of
customers.
- We have the created date of most of the offline and online contact (if we don’t have
this info we’ll use the first order as the created date) that we can use to calculate the
longevity of each customer. We will create categories of longevity to make the
analysis more understandable.


For all this datas, we also need to analyze which customers gave the information and which
did not to target communication on specific segments of customer.


2. How do they behave ?


To answer this second question we will use the same process as above and firstly split it into
subquestions, that will guide the analysis. To know how your customer behave you need to
know :
- What channel do your customers use ?
- How much do they spend ?
- How many products do they buy ?
- How do they respond to discounts ?
- When do they order ?


Regarding this list of question, these are the datas that’ll need and how to get them :
- First, we will need the number of customers per channel and the number of orders
(in count and in total sales, quantity etc…) per channel. We can have these datas by
making some calculations using order and contacts tables. We will also look at
customers that use both channels.
- We will look at the total sales and the average basket price of each customer
- We will also analyze the size in terms of quantity of products for each order and the
average.
- Regarding discount, we will look at the influence of discount over the customer
behavior looking at their basket when there is a discount.
- Finally, we will also look at their spending during the week : are they more spending
on a special day ? And during the year : are they more spending during a particular
month or period ? For this we’ll use the date of orders.


To create the 360 database used to answer those multiple questions, I’ve used email to join
online tables and contact_id to join offline tables. Then, to create a 360 contact table I’ve
unioned the two contact tables by adding some fields to the offline table and removing
duplicate contact. And, to create the 360 order table I’ve also used an union function. All this
process is better described in the notebook that I’ve add to this repo.
