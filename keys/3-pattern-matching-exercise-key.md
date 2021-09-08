# Exercise
1. Which characters have names that start with 'Captain'
```sql
select name
from character
where name like 'Captain%'
```

2. Which characters have names that end with 'Man'
```sql
select name
from character
where name like '%Man'
```

3. Which characters have hair and eyes that starts with 'Bl' 
```sql
select name, eyes, hair
from character
where hair like 'Bl%' and eyes like 'Bl%'
```

4. What powers contain the word 'ion'
```sql
select name
from power
where name like '%ion%'
```

5. What powers start with a 5-letter word
```sql
select name
from power
where name like '_____ %'
```

6. What powers end with a 5-letter word
```sql
select name
from power
where name like '% _____'
```

7. What powers contain both an opening and closing parenthesis?
```sql
select name
from power
where name like '%(%' and name like '%)%'
```

8. What characters start with a 3-letter word or end with a 3-letter word?
```sql
select name
from character
where name like '___ %' or name like '% ___'
```

9. What characters start with a 3-letter word or end with a 3-letter word, and also has `Black` hair?
```sql
select name
from character
where (name like '___ %' or name like '% ___')
    and hair = 'Black'
```

10. What characters start with a 3-letter word or end with a 3-letter word, and either has `Black` hair or `Black` eyes?
```sql
select name
from character
where (name like '___ %' or name like '% ___')
    and (hair = 'Black' or eyes = 'Black')
```

11. What characters start with a 3-letter word or end with a 3-letter word, and either has `Black` hair or `Black` eyes, or has a both `Blond` hair and `Blue` eyes.
```sql
select name, *
from character
where (name like '___ %' or name like '% ___')
    and ((hair = 'Black' or eyes = 'Black')
        or (hair = 'Blonde' and eyes = 'Blue'))
```