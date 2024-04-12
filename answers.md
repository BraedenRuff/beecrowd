# beecrowd problems (postgreSQL)

1)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/3cb1e066-32fb-49ae-874a-7d9a1ce48738)

```
SELECT name FROM customers WHERE state = 'RS';    
```

2)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/12f2921d-86b4-441a-a966-f5ec3faa7ea6)

```
SELECT name, street from customers where city = 'Porto Alegre';    
```

3)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/9dc171f4-d81a-42c0-9368-04432e4ce70c)

```
SELECT id, name from products where price < 10 OR price > 100;    
```

4)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/1333ff47-8de7-4a49-96b1-456de7edd56e)

```
SELECT products.name, providers.name    
FROM products    
JOIN providers on providers.id = products.id_providers    
WHERE id_categories = 6    
```

5)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/c117cc9f-7942-4dbe-8b03-8403238f7519)

```
SELECT products.id, products.name    
FROM products    
JOIN categories ON categories.id = products.id_categories    
WHERE categories.name LIKE 'super%'    
```

6)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/727c71e1-13ef-432d-b56a-e2a273cd8bea)

```
SELECT DISTINCT City     
FROM providers    
ORDER BY City DESC;    
```

7)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/1e8a90c9-daa4-4dd9-bd8b-60b1f3ff264c)

```
SELECT MAX(price), MIN(price)    
FROM products;    
```

8)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/4f4205fa-2f52-4db3-b2e3-ba79948c2e1a)

```
SELECT categories.name, SUM(products.amount)        
FROM products    
JOIN categories ON categories.id = products.id_categories    
GROUP BY categories.name    
ORDER BY categories.name DESC;    
```

9)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/c3025447-6f51-4c35-ba5b-ab13b2da319c)

```
SELECT CAST(AVG(price) as numeric(10,2)) as number from products;    
```

10)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/d57ed179-504e-4064-b1bc-506abb88d36e)

```
SELECT movies.id, movies.name from movies join genres on movies.id_genres = genres.id where genres.description = 'Action';    
```

11)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/5e728d05-f61c-4eee-a51d-a79cfb93d6b4)

```
select movies.id, movies.name from movies join prices on movies.id_prices = prices.id where prices.value < 2.00; 
```

12)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/2ac41f02-358c-4bd1-ba09-813a90531c7d)

```
select customers.name, rentals.rentals_date     
from customers     
join rentals on rentals.id_customers = customers.id     
where rentals.rentals_date < '2016-10-01' AND rentals.rentals_date >= '2016-09-01';     
```

13)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/2853f5eb-3892-4cdc-95bd-9f3ecd266f61)

```
SELECT DISTINCT city FROM customers
```

14)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/9b6394a9-56e8-454a-a682-c975aeb76e25)

```
select id, name from customers where id not in (select id_customers from locations) 
```

15)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/61b5efde-33e2-44c5-90f5-7c36419ce7f0)

```
select products.name, providers.name     
from providers     
join products on providers.id = products.id_providers     
where providers.name = 'Ajax SA';    
```

16)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/e5314c07-dd7e-4b3d-9802-59581e34424e)

```
select products.name, providers.name, categories.name    
from products    
join providers on providers.id = products.id_providers    
join categories on categories.id = products.id_categories    
where categories.name = 'Imported' AND providers.name = 'Sansul SA';    
```

17)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/f6d95ac7-6bc4-4211-9b4f-cef16efdf1b6)

```
select products.name, providers.name, products.price     
from products    
join providers on providers.id = products.id_providers    
join categories on categories.id = products.id_categories    
where products.price > 1000 and categories.name = 'Super Luxury';    
```

18)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/84a67534-517b-4b6f-856a-a0a282ba078f)

```
SELECT customers.name, orders.id    
FROM customers    
JOIN orders ON orders.id_customers = customers.id    
WHERE orders.orders_date >= '2016-01-01' AND orders.orders_date < '2016-07-01';    
```

19)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/76ffb05e-78b7-4620-9f59-98e452b83692)

```
select products.name     
from products    
join providers on products.id_providers = providers.id    
where (products.amount between 10 and 20) and providers.name like 'P%'    
```

20)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/a1b93c8f-ebe5-4434-b5b1-ec848c17e3a5)

```
select name    
from customers    
where customers.id in (select id_customers from legal_person)    
```

21)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/2fdf7a71-7115-4ebe-a25a-0a958e35c18a)

```
select products.name, categories.name    
from products    
join categories on id_categories = categories.id    
where amount > 100 and categories.id in (1,2,3,6, 9)    
order by categories.id asc    
```

22)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/449f9f9e-fc52-4f97-9eba-0de5a9a9a27f)

```
select count(distinct city) from customers
```

23)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/5bf23de2-18fb-4197-80dc-0dd6dbe51f94)

```
select SUBSTRING(cpf FROM 1 FOR 3) || '.' ||     
       SUBSTRING(cpf FROM 4 FOR 3) || '.' ||    
       SUBSTRING(cpf FROM 7 FOR 3) || '-' ||    
       SUBSTRING(cpf FROM 10 FOR 2)    
from natural_person     
```

24)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/3419b200-d65c-4eaa-9a0a-9596a450ffc9)

```
SELECT name, customers_number from (SELECT name, customers_number, 1 AS order_col FROM lawyers WHERE customers_number = (SELECT MAX(customers_number) FROM lawyers)    
UNION    
SELECT name, customers_number, 2 AS order_col FROM lawyers WHERE customers_number = (SELECT MIN(customers_number) FROM lawyers)    
UNION    
SELECT 'Average' AS name, ROUND(AVG(customers_number))::INTEGER AS customers_number, 3 AS order_col FROM lawyers    
ORDER BY order_col asc) as x    
```

25)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/c1e23ded-795c-4840-8119-08bf19473814)

```
select name, ROUND(((score.math*2+score.specific*3 + score.project_plan*5)/10)::numeric, 2) as avg     
from candidate    
join score on candidate_id = id        
order by avg desc    
```

26)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/cd5dcef8-65e6-4412-ae26-fe1416b7c0da)

```
select name, EXTRACT(DAY FROM payday)::INTEGER as day from loan
```

27)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/262c2f4e-fd3b-4913-8fa8-8157eb9293d4)

```
WITH RankedTeams AS (    
  SELECT team, position,    
         ROW_NUMBER() OVER (ORDER BY position ASC) AS row_num,    
         COUNT(*) OVER () AS total_count    
  FROM league    
)    
SELECT 'Podium: ' || team AS name    
FROM RankedTeams    
WHERE row_num <= 3    
UNION ALL    
SELECT 'Demoted: ' || team    
FROM RankedTeams    
WHERE row_num IN (total_count - 1, total_count)    
```

28)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/f3efa730-b7b7-4297-923f-8962b68ce7db)

```
select 'Approved: ' || name, grade from students    
where grade >= 7    
order by grade desc;    
```

29)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/ad9f154f-1789-49e5-bf22-2bb79d675727)

```
select life_registry.name, ROUND(life_registry.omega * 1.618, 3) as "The N Factor"    
from dimensions    
join life_registry on life_registry.dimensions_id  = dimensions.id    
where life_registry.name like 'Richard%' AND (dimensions.name = 'C774' OR dimensions.name = 'C875');    
```

30)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/93bb83b1-69cf-4e1d-aad6-55a8d380ce3c)

```
select name, length(name) as length from people    
order by length desc    
```

31)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/66959a1a-4454-4fba-8bcd-f37a3e855d83)

```
select id, password, MD5(password) as MD5 from account
```

32)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/7d70bf44-366d-4b5e-9709-ec5720e7d66e)

```
select name, Round(salary / 10, 2) as tax from people    
where salary > 3000    
```

33)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/609e74c3-539b-4a92-9470-f6f66aa5c054)

```
select replace(name, 'H1', 'X') from virus
```

34)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/38f16737-15b9-4f8e-a1a1-dbab3e10bcfa)

```
WITH TeamResults AS (    
  SELECT     
    teams.name,     
    COUNT(teams.name) AS matches,     
    SUM(    
      CASE         
        WHEN (matches.team_1 = teams.id AND matches.team_1_goals > matches.team_2_goals)     
             OR (matches.team_2 = teams.id AND matches.team_2_goals > matches.team_1_goals)     
        THEN 1     
        ELSE 0     
      END    
    ) AS victories,    
    SUM(    
      CASE     
        WHEN (matches.team_1 = teams.id AND matches.team_1_goals < matches.team_2_goals)     
             OR (matches.team_2 = teams.id AND matches.team_2_goals < matches.team_1_goals)     
        THEN 1     
        ELSE 0     
      END    
    ) AS defeats,    
    SUM(    
      CASE     
        WHEN (matches.team_1 = teams.id AND matches.team_1_goals = matches.team_2_goals)     
             OR (matches.team_2 = teams.id AND matches.team_2_goals = matches.team_1_goals)     
        THEN 1     
        ELSE 0     
      END    
    ) AS draws    
  FROM     
    teams    
  JOIN     
    matches ON matches.team_1 = teams.id OR matches.team_2 = teams.id    
  GROUP BY     
    teams.name    
)    
select name, matches, victories, defeats, draws, (victories * 3 + draws) as score    
from TeamResults    
order by score desc
```

39)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/bddf43dc-27d5-49c0-b109-13546751b51f)

```
select amount from (select amount, count(amount) as most_frequent_value from value_table    
group by amount    
order by most_frequent_value desc limit 1) as x    
```

40)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/530a4211-af4c-479f-82b4-46a5eb2d7d8c)

```
select doctors.name,  ROUND( SUM(attendances.hours * 150 * (1 + work_shifts.bonus/100)), 1 ) as salary from doctors    
join attendances on attendances.id_doctor = doctors.id    
join work_shifts on attendances.id_work_shift = work_shifts.id    
group by doctors.name    
```

41)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/d3e5b4c8-238c-4747-92b1-a55cabcdf5e2)

```
WITH matching_temperatures AS (    
	SELECT    
		temperature,    
		COUNT(temperature) AS matching_count    
	FROM records    
	GROUP BY temperature, mark    
	ORDER BY mark    
)    
SELECT     
    temperature,    
    matching_count AS number_of_records    
FROM matching_temperatures    
;
```

42)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/28b4764a-e397-4743-845c-61ee5b4e6d88)

```
SELECT    
	packages.year,     
	senders.name as sender,     
	receivers.name as receiver    
FROM packages     
INNER JOIN users AS senders    
     ON packages.id_user_sender = senders.id     
INNER JOIN users AS receivers    
     ON packages.id_user_receiver = receivers.id    
WHERE (packages.color='blue' or packages.year=2015) AND     
(senders.address <> 'Taiwan' AND receivers.address <> 'Taiwan')    
ORDER BY packages.year DESC;    
```

44)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/382f69d2-2be2-475f-b324-5e5289299a36)

```
WITH running_operations_returns AS (    
	SELECT     
		clients.id,    
		clients.name,    
		clients.investment,    
		operations.month,    
		SUM(profit) OVER (PARTITION BY client_id ORDER BY operations.id) AS running_sum_of_profit,    
		SUM(profit) OVER (PARTITION BY client_id ORDER BY operations.id) - clients.investment AS return    
	FROM operations    
	INNER JOIN clients    
		ON operations.client_id = clients.id    
	ORDER BY operations.client_id, operations.month    
)    
SELECT     
	payback_month_return.name,    
	running_operations_returns.investment,    
	running_operations_returns.month AS month_of_payback,    
	payback_month_return.return    
FROM (    
	SELECT DISTINCT ON (id)    
		name,    
		investment,    
		return    
	FROM running_operations_returns    
	WHERE return >= 0    
) AS payback_month_return    
INNER JOIN running_operations_returns    
	USING (return )    
ORDER BY return DESC    
;    

46)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/73f6087b-6bd9-417e-98ab-5cca0026558a)

select name, (CASE     
              WHEN (type = 'A')     
              THEN 20.0     
              WHEN (type = 'B')     
              THEN 70.0     
              WHEN (type = 'C')     
              THEN 530.5     
              END) as price from products     
order by type, id desc    
```

47)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/5468c20a-5e09-44a1-a38c-824f092e6648)

```
SELECT     
    c1.queue AS row,     
    c1.id AS left_chair,     
    c2.id AS right_chair    
FROM chairs c1    
JOIN chairs c2 ON c1.queue = c2.queue AND c1.id = c2.id - 1    
WHERE c1.available = TRUE AND c2.available = TRUE    
ORDER BY c1.id;    
```

48)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/75a4cf32-64f2-4dda-95a1-85634b9c2dbf)

```
WITH NodeDetails AS (    
    SELECT    
        node_id,    
        pointer IS NOT NULL AS has_pointer    
    FROM    
        nodes    
),    
Pointers AS (    
    SELECT    
        DISTINCT pointer AS node_id    
    FROM    
        nodes    
    WHERE    
        pointer IS NOT NULL    
),    
Classification AS (    
    SELECT    
        node_id,    
        CASE    
            WHEN node_id NOT IN (SELECT node_id FROM Pointers) THEN 'ROOT'    
            WHEN NOT EXISTS (SELECT 1 FROM NodeDetails WHERE NodeDetails.node_id = nodes.node_id AND has_pointer) THEN 'LEAF'    
            ELSE 'INNER'    
        END AS type    
    FROM    
        nodes    
    GROUP BY    
        node_id    
)    
SELECT    
    node_id,    
    type    
FROM    
    Classification    
ORDER BY    
    node_id;    
```

49)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/bb7f5d15-3fb6-4fe3-9c55-33e72247b7bd)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/19b41601-d4e4-4198-96a8-1190a58a7569)

```
SELECT     
    CASE     
        WHEN u1.posts < u2.posts THEN u1.user_name    
        ELSE u2.user_name    
    END AS u1_name,    
    CASE     
        WHEN u1.posts < u2.posts THEN u2.user_name    
        ELSE u1.user_name    
    END AS u2_name    
FROM followers f1    
JOIN followers f2 ON f1.following_user_id_fk = f2.user_id_fk AND f1.user_id_fk = f2.following_user_id_fk    
JOIN users u1 ON u1.user_id = f1.user_id_fk    
JOIN users u2 ON u2.user_id = f1.following_user_id_fk    
WHERE u1.user_id < u2.user_id    
ORDER BY     
    CASE     
        WHEN u1.posts < u2.posts THEN u1.user_id    
        ELSE u2.user_id    
    END;    
```

50)
![image](https://github.com/BraedenRuff/beecrowd/assets/45854390/a724dcc2-3832-420c-9533-fbe10eb82ed3)

```
SELECT city_name, population    
FROM (    
  SELECT city_name, population,    
         DENSE_RANK() OVER (ORDER BY population DESC) AS pop_rank    
  FROM cities        
) ranked_cities    
WHERE pop_rank = 2    
union        
SELECT city_name, population    
FROM (   
  SELECT city_name, population,    
         DENSE_RANK() OVER (ORDER BY population ASC) AS pop_rank    
  FROM cities    
) ranked_cities    
WHERE pop_rank = 2    

order by population desc;    
```

35, 36, 37, 38, 43, 45 not completed due to different language
