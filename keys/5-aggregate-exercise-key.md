# Exercise
1. How many teams operate out of each of the `headquarters`?
```sql
select headquarters, count(id)
from team
group by headquarters
```

2. How many teams operate out of each of the `headquarters`, ignoring records that do not have a headquarters specified?
```sql
select headquarters, count(id)
from team
where headquarters is not null
group by headquarters
```

3. How many teams operate out of each of the `headquarters`, ignoring records that do not have a headquarters specified, and only headquarters with more than 1 team operating?
```sql
select headquarters, count(id)
from team
where headquarters is not null
group by headquarters
having count(id) > 1
```

4. How many teams operate out of each of the `headquarters`, ignoring records that do not have a headquarters specified, and only headquarters with more than 1 team operating, sorted by headquarters with the most teams at the top?
```sql
select headquarters, count(id)
from team
where headquarters is not null
group by headquarters
having count(id) > 1
order by count(id) desc
```