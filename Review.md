

**Data Mining: Association Rule Mining**


**Data Mining**

Source: Forbes

The process of analysing large amounts of data sets in order to discover patterns and extract useful information.

![image](https://github.com/user-attachments/assets/ca9dddbb-47bf-4e44-b4a7-c557688e455d)


**Why “mine” data?**

- Massive data is being generated and warehoused (e.g., web-data, e-commerce, bank/credit card transactions, retail, etc.)
- Computers are cheap and fast
- The information and knowledge gained via “mining” can be valuable and useful for many applications

![image](https://github.com/user-attachments/assets/2555b2f2-49bf-4f0f-8ef0-346fd00be56d)


**Beer and diapers: the impossible correlation**

https://www.linkedin.com/pulse/tale-beer-diapers-ibeukp

- In 1992, an industry consultant analysed 1.2m market baskets from 25 Osco Drug stores and discovered that customers bought beer and diapers between 5-7 pm
- Put beer and diapers on the same shelf; run a sales promotion on diapers while raise the price of beer
- Not an example of data mining or any type of advanced analysis — just using SQL queries to find correlations!

![image](https://github.com/user-attachments/assets/ee772d56-c407-437c-af69-4b83571a695e)


**Market Basket Analysis**

![image](https://github.com/user-attachments/assets/caf2ad01-28e4-41f4-8a2d-f6115764961f)


Bread Jam Laptop Headphone

To uncover purchase patterns (associations between items)

Source: Wall Street Journal

- Chocolate packages are reaching the expiry date
- Chocolate <=> Barbie dolls
- Run a promotion campaign: buy 1 barbie doll, 50% discount on chocolate bars

![image](https://github.com/user-attachments/assets/a235988c-9f8e-4e35-99d6-11560d0cf221)


**Frequent Itemset**

- Itemset
  - a collection of item(s), e.g., {milk, diaper, beer}
- Support count
  - frequency of occurrence of an itemset
  - e.g., Freq({milk, diaper, beer}) = 2
- Support
  - fraction of transactions containing an itemset
  - e.g., Support({milk, diaper, beer}) = 2/5
- Frequent itemset
  - an itemset whose support value is greater than a threshold

![image](https://github.com/user-attachments/assets/7f2fc6d6-f10a-4ee0-82e4-8fcc9dc053cf)

![image](https://github.com/user-attachments/assets/438cfbf8-1a0f-478d-92a8-094a9165506b)


TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

**Association Rule**

- Association rule
  - if-then rule, X → Y where X and Y are itemsets
  - if: antecedent; then: consequent (An antecedent is an item found within the data. A consequent is an item found in combination with the antecedent.)
  - e.g., {milk, diaper} → {beer}
- Rule evaluation metrics
  - Support (s): fraction of transactions containing both X and Y, i.e., s(X → Y) = Freq(X ∪ Y) / |T|
  - Confidence (c): how often items in Y appear in transactions containing X, i.e., c(X → Y) = Freq(X ∪ Y) / Freq(X), a.k.a. the probability of Y given X



TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

**Association Rule**

- Example: {milk, diaper} → {beer}
- Support = Freq({milk, diaper, beer}) / |T| = 2/5 = 0.40
- Confidence = Freq({milk, diaper, beer}) / Freq({milk, diaper}) = 2/3 = 0.67

TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

**Association Rule Mining**

- Problem: Given a transaction dataset T = {T1, T2, …, Tn}, identify all rules X → Y with support and confidence values greater than the minimum thresholds

TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

**Association Rule Mining**

- Challenge: How to generate association rules?
- Brute-force approach: 1) list all possible rules, 2) compute support and confidence, 3) remove rules based on thresholds. BUT too computationally expensive!
- a more efficient way is to mine frequent itemsets, based on which rules with certain confidence are generated
- key question: how to mine frequent itemsets?

TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

**Frequent itemset mining**

TID | Items
---|---
1 | bread, milk
2 | bread, diaper, beer, eggs
3 | milk, diaper, beer, coke
4 | bread, milk, diaper, beer
5 | bread, milk, diaper, coke

- Apriori
  - identify frequent items and extend them iteratively to larger and larger itemsets
  - drawbacks: 1) number of candidates; 2) multiple scans of the database
- more advanced: FP-Growth

Itemset | Support
---|---
bread | 4
milk | 4
diaper | 4
beer | 3
coke | 2
eggs | 1

Itemset | Support
---|---
bread, milk | 3
bread, diaper | 3
milk, diaper | 3
diaper, beer | 3
…

**Further reading**

- Han, J., Kamber, M., and Pei, J., *Data Mining: Concepts and Techniques*, 3rd ed. San Francisco, CA, USA: Morgan Kaufmann Publishers Inc., 2011. ISBN: 978-0-12-381479-1.

**Happy Coding**

---
