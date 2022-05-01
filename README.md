## Solution of the 1 task:

# Table with results

| query | total cost | elapsed time | index type |
| --- | ------- | ------- | ------- |
| select * from customers where to_tsvector('english', review) @@ to_tsquery('english', 'great \| product') | 23.75 | 0.002 | gist |
| select * from customers where to_tsvector('english', address) @@ to_tsquery('english', 'Washingtone') | 91.22 | 0.001 | gin |
| select * from customers where name = 'David Gomez' | 48.07 | 0.001 | btree |
| select * from customers where birthday between '2002-01-25' and '2002-01-27' | 1092.16 | 0.009 | brin |
| query = "select * from customers where email = 'kayla90@yahoo.com'" | 12.04 | 0.001 | hash |