[[_TOC_]]

# Question d'un client :
As we need (“keywords” + password) OR (pattern + password, can we have a “OR” operator in the SIT or should I create 2 SIT ?
The difficulty is to catch the “password”…

# Réponse à fournir
a Sensitive Information Type (SIT) is made of these characteristics : 
- A name and description
- One to several pattern
Each pattern is made of : 
- a primary element : the core rule of the pattern. Most of the time it is a regex formula, but it can be keywords
- supporting element : these are rule that reduces the risk of having false positives with the primary element
- additional checks : these are other rule that reduces the risk of having false positives with the primary element
>![SIT-1.png](/.attachments/SIT-1-823535fe-4ce7-4e2e-aa76-dad2ad805f87.png) 

- Each pattern works as an "OR" operator in the SIT
- "supporting elements" and "additional elements" work as an "AND" operator within the pattern. 
It can be useful but also can bring to false negative if these are too strict for identifying the pattern.

An example with ONE (simple) SIT with two patterns :
- pattern 1 : looks for "login" keyword as a primary element, with no supporting elements
- pattern 2 : looks for "password" keyword as a primary element, with no supporting elements,
>![SIT-2.png](/.attachments/SIT-2-4f253d6c-fc2c-47e6-a9b7-0160dae76a1f.png)

Then : 
- a document with only the word "login" will match
- a document that contains the word "login" AND "password" will match
- a document with only the word "password" will match