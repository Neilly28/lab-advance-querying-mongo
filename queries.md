![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

<!-- Your Code Goes Here -->

query: {name: 'Babelgum'}
projection: {name:1, \_id:0}

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

<!-- Your Code Goes Here -->

query: {number_of_employees: {$gt: 47}}
projection:
sort: {number_of_employees:1}
skip:
limit: 20

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

<!-- Your Code Goes Here -->

query: {founded_year: {$gte: 2000, $lte:2005}}
projection: {name: 1, founded_year: 1, \_id:0}
sort:
skip:
limit:

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

<!-- Your Code Goes Here -->

query: {$and: [{"ipo.valuation_amount": {$gt: 100000000}},{founded_year: {$lt: 2010}}]}
projection: {name:1, ipo:1, \_id:0}
sort:
skip:
limit:

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

<!-- Your Code Goes Here -->

query: {$and: [{number_of_employees: {$lt: 1000}},{founded_year: {$lt: 2005}}]}
projection:
sort: {number_of_employees: 1}
skip:
limit: 10

### 6. All the companies that don't include the `partners` field.

<!-- Your Code Goes Here -->

query: {'partners': {$exists: false}}
projection:
sort:
skip:
limit:

### 7. All the companies that have a null type of value on the `category_code` field.

<!-- Your Code Goes Here -->

query: {category_code: {$type: 'null'}}
projection:
sort:
skip:
limit:

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

<!-- Your Code Goes Here -->

query: {number_of_employees: {$gte:100, $lt:1000}}
projection: {name: 1, number_of_employees: 1, \_id:0}
sort:
skip:
limit:

### 9. Order all the companies by their IPO price in a descending order.

<!-- Your Code Goes Here -->

query:
projection:
sort: {"ipo.valuation_amount": -1}
skip:
limit:

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

<!-- Your Code Goes Here -->

query:
projection:
sort: {number_of_employees: -1}
skip:
limit: 10

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

<!-- Your Code Goes Here -->

query: {founded_month: {$gte:4, $lte:6}}
projection:
sort:
skip:
limit: 1000

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

<!-- Your Code Goes Here -->

query: {$and: [{'founded_year': {$lt: 2000}, 'acquisition.price_amount': {$gt: 10000000}}]}
projection:
sort:
skip:
limit:

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

<!-- Your Code Goes Here -->

query: {'acquisition.acquired_year': {$gt: 2010}}
projection: {name:1, acquisition:1, \_id:0}
sort: {'acquisition.price_amount': 1}
skip:
limit:

### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

<!-- Your Code Goes Here -->

query:
projection: {name: 1, founded_year: 1, \_id:0}
sort: {founded_year: 1}
skip:
limit:

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

<!-- Your Code Goes Here -->

query: {founded_day: {$gte: 1, $lte:7}}
projection:
sort: {'acquisition.price_amount': -1}
skip:
limit: 10

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

<!-- Your Code Goes Here -->

query: {category_code: "web", number_of_employees: {$gt: 4000}}
projection:
sort: {number_of_employees: 1}
skip:
limit:

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

<!-- Your Code Goes Here -->

query: {$and: [{'acquisition.price_amount': {$gt: 10000000}},{'acquisition.price_currency_code': 'EUR'}]}
projection:
sort:
skip:
limit:

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

<!-- Your Code Goes Here -->

query: {'acquisition.acquired_month': {$gte: 1, $lte:3}}
projection: {name: 1, acquisition: 1}
sort:
skip:
limit: 10

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

<!-- Your Code Goes Here -->

query: {$and: [{founded_year: {$gte: 2000, $lte: 2010}},{'acquisition.acquired_year': {$gte: 2011}}]}
projection:
sort:
skip:
limit:
