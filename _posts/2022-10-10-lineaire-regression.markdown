# Lineaire regression

An example usually used for learning lineaire regression for machine learning, 
is predicting house prices based on different criteria, like number of bedrooms and square footage. 

| Cost ($1000) | Bedrooms | sqt  |
|--------------|----------|------|
| 10           | 2        | 1200 |


Say price = P and number of rooms is R, and square footage is F.
It is sensible to assume that there is some sort of relationship:

P = a1 * R + a2 * F + b

The goal of lineair regression is to start with the data (house prices and their square footage and number of bedrooms) 
and find out an approximate value for a1, a2, b that minimize the error.

