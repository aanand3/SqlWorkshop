# Exercise Walkthrough

### INNER JOIN
1. Return the character`name` and alias `name` of all characters with aliases
```sql
select c.name, a.name
from character c
join alias a on c.id = a.character_id
```

2. Return the character `name` and alias `name` of all characters with aliases, whose character name has at least 8 letters, but alias name has exactly 4 
```sql
select c.name, a.name
from character c
join alias a on c.id = a.character_id
where c.name like '________%' and a.name like '____'
```

3. Return the character `name` and power `power_id` of all characters with powers
```sql
select c.name, cp.power_id
from character c
join character_power cp on c.id = cp.character_id
```

4. Return the character `name` and power `name` of all characters with powers
```sql
select c.name, p.name
from character c
join character_power cp on c.id = cp.character_id
join power p on cp.power_id = p.id
```

5. Return the character `name` and power `name` of all characters with powers, but only powers that do not contain the word 'Super'
```sql
select c.name, p.name
from character c
join character_power cp on c.id = cp.character_id
join power p on cp.power_id = p.id
where p.name not like '%Super%'
```

6. Return the character `name` and power `name` of all characters with powers, but only powers that do not contain the word 'Super', and characters with a `strength` greater than 5 
```sql
select c.name, p.name
from character c
join character_power cp on c.id = cp.character_id
join power p on cp.power_id = p.id
where p.name not like '%Super%' and c.strength > 5
```

### LEFT JOIN
7. Return all character `name` and any alias `name` (if any)
```sql
select c.name, a.name
from character c
left join alias a on c.id = a.character_id
```

8. Return the character `name` of all characters without aliases
```sql
select c.name
from character c
left join alias a on c.id = a.character_id
where a.id is null
```

9. Return the character `name` of all characters without aliases, who also have a `secret_identity`
```sql
select c.name
from character c
left join alias a on c.id = a.character_id
where a.id is null and c.secret_identity = true
```

10. Return the character `name` of all characters who are not on a team
```sql
select c.name
from character c
left join team_character tc on c.id = tc.character_id
where tc.team_id is null
```

11. What teams headquartered in 'New York' have members with the power of `Flight`
```sql
select t.name
from team t
join team_character tc on t.id = tc.team_id
join character_power cp on tc.character_id = cp.character_id
join power p on cp.power_id = p.id
where t.headquarters = 'New York' and p.name = 'Flight'
```

12. Who are all the active members of the X-Men with a secret identity, but no aliases?
```sql
select c.name
from character c
left join alias a on c.id = a.character_id
join team_character tc on c.id = tc.character_id
join team t on tc.team_id = t.id
where t.name = 'X-Men'
  and tc.is_active = true
  and c.secret_identity = true
  and a.id is null
```