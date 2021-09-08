# Exercise Walkthrough

1. Return from the `character` table, records with `speed` greater than 4.
```sql
select *
from character
where speed > 4
```

2. Return from the `character` table, records with `speed` greater than 4 and `durability` less than or equal to 3
```sql
select *
from character
where speed > 4 and durability <= 3
```

3. Return from the `character` table, records with `hair` equal to 'Brown' or `eyes` equal to 'Brown'
```sql
select *
from character
where hair = 'Brown' or eyes = 'Brown'
```

4. Return from the `character` table, records with `secret_identity` equal to false
```sql
select *
from character
where secret_identity = false
```

5. Return from the `team` table, records with `headquarters` equal to 'New York'
```sql
select *
from team
where headquarters = 'New York'
```

6. Return from the `team` table, records with `founded_on` greater than July 4, 1984
```sql
select *
from team
where founded_on > '1984-07-04'
```

7. Return from the `team` table, records with `founded_on` greater than July 4, 1984 and `headquarters` = 'New York'
```sql
select *
from team
where founded_on > '1984-07-04' and headquarters = 'New York'
```

8. Return from the `team` table, records with `headquarters` not equal to 'New York'
```sql
select *
from team
where headquarters <> 'New York'
```

9. Return from the `team` table, records with `name` equal to 'Kree' or 'Skrulls'
```sql
select *
from team
where name = 'Kree' or name = 'Skrulls'
```

10. Return from the `team` table, records with `headquarters` having a null value
```sql
select *
from team
where headquarters is null
```

11. Return from the `team` table, records with `headquarters` having a non-null value
```sql
select *
from team
where headquarters is not null
```

12. Return from the `team` table, records with `name` less than or equal to 'Defenders'
```sql
select *
from team
where name <= 'Defenders'
```

13. What characters have a power_level above 9000? (power_level = all stats multiplied)
```sql
select name
from character
where (durability * energy * fighting * intelligence * speed * strength) > 9000
```

14. What characters with names starting with 'X', 'Y', or 'Z' have a secret identity?
```sql
select name
from character
where name > 'X' and secret_identity = true
```

15. What teams were founded in the 80s and 90s?
```sql
select name
from team
where founded_on >= '1980-01-01' and founded_on < '2000-01-01'
```

16. What teams without a headquarters were founded either in the 70s or the 2010s?
```sql
select name
from team
where headquarters is null
    and ((founded_on >= '1970-01-01' and founded_on < '1980-01-01')
      or (founded_on >= '2010-01-01' and founded_on < '2020-01-01'))
```