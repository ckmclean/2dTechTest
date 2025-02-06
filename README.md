### Quick Overview

The purpose of this test is to measure your ability to understand
a request, build a solution, and interpret data into a front end
solution.

We are looking at several measures

* Initiative shown in implementing the request
* Comprehensiveness and accuracy of the response
* Presentation to the end user (i.e. the customer)
* Approach and usefulness of the code

You are very much allowed to reference our existing address searches
for 2degrees or Slingshot, however we aren't looking for you copy
them.You are encouraged to use whatever flare you wish to enhance
the solution - we are looking at how **you** develop, not ourselves.

Saying that, don't feel like you need to create something drastically
unique either. Build what is comfortable to you and assume that this
will be something either a customer or internal agent will be using.

---

# READ ALL INSTRUCTIONS BEFORE PROCEEDING WITH ANY WORK

---

# Address Qualification Test

One of the fundamental concepts when connecting or making changes to
a customers broadband connection is the address qualification, also
known as a prequalification. This is when we take a customer's address
from a text input, search for matching address objects in our database,
then from their selected correct address find all the products that they
can purchase for any address.

# The Task

**Your task is to build an address search app that allows the user to
search a free text input, choose their correct address, and then display
the availability of any Fibre 1000 product is available at their
location.**

You are allowed to make this in any language, framework, or deployment
that you wish, however the code must be relatively simple to build and
run locally, with full instructions included in your solution to allow
us to run it. Runnable code is a requirement.

# Order of operations

## Address search

The first task is to allow the customer to search for their address.
We do this with a free text search API.

---

***API***

`GET https://api.2degrees.nz/sales/v3/qualification/addresses/search`

***PARAMETERS***

* address - a text parameter of a partial address, typically gathered 
  from a form field
---
This will return a list of addresses including their individual
components and elements.


## Address qualification

Once a search is done and a customer presented with the matches,
they will select their correct address and you can use the qualification
endpoint to check what products are available.

****API****
`GET https://api.2degrees.nz/sales/v3/qualification/qualify`

****PARAMETERS****

* businessGroup - indicates which segment of the greater business you 
  wish to get products for (e.g. brand)
* salesChannel - a way of filtering to a subset of products, used to 
  differentiate between uses such as for new customer sales, existing 
  customer address moves, etc.
* locationId - a unique identifier for every broadband physical connection

## Qualification results

Once you have the qualification results, you need to determine if
they have a Fibre 1000 `coreProduct` available at this address. The
qualification results detail a great many items and information including
hardware items, additional products such as mobile plans, and information 
on the Local Fibre Company (LFC) connections that might exist.

**You only need to ensure that a Fibre 1000 product is available - 
it does not matter what specific product**

This is the trickiest part of the process, as you will need to intuit what 
the best method will be to determine this availability. Ensure you look 
over the API response or mocks carefully, and consult other resources
(see below)

Once you have shown this availability, your task is complete.

---

# Providing your Solution

Please place your solution into your own Github account and send us a 
public link to the code. 


---

### Do not upload any branches or code to this repository 

---

## Resources

We have provided several resources for your use. You may use as few or 
as many of these as you wish, however we strongly encourage you to 
review all of them, especially the `constants.json` file which contains
both critical and non-critical values that you can use. The `/mocks` 
directory also contains dummy responses for both the address search and 
qualification that you can build against, however your submitted 
solution must use our proper APIs.

## Things to consider

* We expect this test to take an evening at most and would appreciate
  the solution provided to us within 48 hours of delivery of these  
  instructions.
* Our focus is primarily on functionality, usability, and comprehension.
* Make it look good, but don't feel like it has to be stunning - use a
  framework like Bootstrap or any Material UI base if you wish, or you
  can reference our own sites
* Pay attention to the business groups provided. You may use any that 
  you wish, however your presentation should match.
* If you wish to go above and beyond, think about what other data you
  could present to the customer that is genuinely relevant - look at 
  what adds value, perhaps there's another layer you could expand upon?
* Whatever you do, don't get lost in providing the most complete solution
  beyond the requirements. Initiative is a great thing to show, but focus
  on the goal of the test.
  



