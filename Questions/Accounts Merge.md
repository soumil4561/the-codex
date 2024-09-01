---
Date: 2024-08-26
Link: https://leetcode.com/problems/accounts-merge/description/
tags:
  - graph
  - union-find
---
Here is the first time that the basic template of union find is changed. 

`Parent`: HashMap<String,String> where each email is an element
`Rank`: (optional) HashMap<String,Integer>

`If u do not want to go by rank system, u can opt for the lexicographic approach as well.`

Now, for each account, if the email exists does not exist in parent, first make that entry. Also store the name for this email in some hashmap or smth. Once email is registered, connect(union) it with previous email(only one) of the same account. 

For each element of parent, find ultimate parent, add this email in list of that ultimate parent. Now finally for each ultimate parent list in the resulting list, sort all the list. Now add names for each list using the earlier stored names, return.

