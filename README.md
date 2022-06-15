# Trunk-based development for data teams - an example
A couple cool and simple example of comparing a "normal" data workflow to a 
trunk-based one. Our setup is a data stack with...

- Three source systems, the Customers, Orders and a CRM System. (data comes inside CSVs)
- We ingest via plain Python (written inside a Jupyter Notebook)
- We use SQL to transform our data 
- And we use superset to build a dashboard on top of our data.

## What we got here?
We got pipeline that is already "preexisting", it goes like this:
- Source the customer.csv & the orders.csv (Python)
- put both into raw tables customers & orders (Python)
- join the two together to form a orders_p_customer model via the customer_id (SQL)
- aggregate to form a orders_per_customer model (SQL)
- build an "Orders per Customer" dashboard on top of this (superset)

If you want to try this yourself, you can take this and do the following task:

**Our task**: Ingest the new source "CRM" (a CSV file), which contains 
the customers, some additional information and the "source". It tells us whether a
customer discovered our product via organic traffic, via an ad or via our newsletter.
Then make the dashboard filterable on this attribute. 

If you don't want to try this yourself, I provide two implementations of this:

1. Shows you the workflow step by step I would've done 4 years ago
2. Shows you the trunk-based workflow I now follow.

Both workflows end up at the same result, but (2) is much quicker in fixing
upcoming problems and gets stuff done waaay faster (in my experience).


## How to run in my own machine
If you want to run this on your own machine, you can use *batect*.

Simply run ```./batect dev``` and it will start the notebook server 
for you, mounting everything into it.

## References 
This repository is based on my article [trunk based development for analytics teams](https://towardsdatascience.com/trunk-based-development-for-data-analytics-engineers-cc8602115b55)! And of course Paul Hammant's great book/website 
[trunk based development](https://trunkbaseddevelopment.com/).
