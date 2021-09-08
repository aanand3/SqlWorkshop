# Exercise
1. Return all records and all columns from the `character` table
```sql
select *
from character
```

2. Return all records and all columns from the `power` table
```sql
select *
from power
```

3. Return only the `name` column from the `power` table
```sql
select name
from power
```

4. Return only the `name` column from the `power` table, but change the column name to 'superpower'
```sql
select name as superpower
from power
```

5. Return `name` and `headquarters` from the `team` table
```sql
select name, headquarters
from team
```

6. Return `name` and `headquarters` from the `team` table, but change the column names to 'super_friends' and 'super_location' respectively
```sql
select name as super_friends, headquarters as super_location
from team
```

7. Return `name`, `energy`, and `intelligence` from the `character` table using a table alias called 'superhero'
```sql
select superhero.name, superhero.energy, superhero.intelligence
from character as superhero
```

8. Return `name` from the `character` table and the product of (durability, energy, fighting, intelligence, speed, strength) as the 'power_level' column
```sql
select name, (durability * energy * fighting * intelligence * speed * strength) as power_level
from character
```