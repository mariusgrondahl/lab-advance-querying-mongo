![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies that it's name match 'Babelgum'. Retrieve only their `name` field.

Filter: {name: "Babelgum"} 
Project: {name: 1}

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.


Filter: {number_of_employees: { $gte: 5000}} 
Sort: {number_of_employees: 1}

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fileds.

Filter: {founded_year: { $gte: 2000, $lte: 2005}} 
Project: {founded_year: 1, name: 1} 



### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

Filter: {founded_year:{$lte: 2010 }},  {valuation_amount: {$gte: 100000000 }}
Project: {name: 1, ipo: 1}

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

Filter: {founded_year:{$lte: 20005 }},  {number_of_employees: {$lte: 1000 }}
Sort: {number_of_employees: 1}
Limit: 10

### 6. All the companies that don't include the `partners` field.

{partners: { $exists: false } }

### 7. All the companies that have a null type of value on the `category_code` field.

{category_code: { $eq: null} }

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

Filter: {number_of_employees: {$gte: 100, $lte: 1000} }
Project: {number_of_employees: 1, name: 1}

### 9. Order all the companies by their IPO price descendently.

Sort: {valuation_amount: -1 }

### 10. Retrieve the 10 companies with more employees, order by the `number of employees`

sort: {number_of_employees: -1 }
limit: 10

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

Filter: {founded_month: {$gte: 6} }
Limit: 1000

### 12. All the companies that have been 'deadpooled' after the third year.



### 13. All the companies founded before 2000 that have and acquisition amount of more than 10.000.000

{founded_year: {$lte: 2000}, acquisition: {$gte: 10000000}  }

### 14. All the companies that have been acquired after 2015, order by the acquisition amount, and retrieve only their `name` and `acquisiton` field.

Filter: {founded_year: {$gte: 2015}, acquisition: {$gte: 10000000}  }
Project: {name: 1, acquisition: 1}
Sort: { acquisition: 1}

### 15. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

Project: {name: 1, founded_year: 1}

### 16. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `aquisition price` descendently. Limit the search to 10 documents.

Project: {name: 1, founded_year: 1}
Sort: {founded_year: 1}

### 17. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascendant order.

Filter: {category_code: {$eq: "web"}, number_of_employees: {$gte: 4000 }}
Sort: {number_of_employees: 1}

### 18. All the companies which their acquisition amount is more than 10.000.000, and currency are 'EUR'.

Filter: {"acquisitions.price_amount": {$gt: 10000000}, "acquisition.price_currency_code": {$eq: "EUR"}}

### 19. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

Filter: {"acquisitions.acquired_month": {$lte: 4}}
Project: {name: 1, acquisition: 1}
Limit: 10

### 20. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

Filter: {founded_year: {$gte: 2000, $lte: 2010}, "acquisition.acquired_year": {$lt: 2011}}