Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.


1. test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```SQL
        CREATE TABLE employee (
	        id integer Primary Key,
	        name varchar(50),
	        birthday date,
	        email varchar(100)
        ); 
```

2. Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```SQL
        insert into employee (id, name, birthday, email) values (1, 'DemoName', '1999-01-01', 'demo@gmail.com.com');
        insert into employee (id, name, birthday, email) values (2, 'DemoName', '1999-01-01', 'demo@gmail.com.com');
        insert into employee (id, name, birthday, email) values (3, 'DemoName', '1999-01-01', 'demo@gmail.com.com');
        insert into employee (id, name, birthday, email) values (4, 'DemoName', '1999-01-01', 'demo@gmail.com.com');
        insert into employee (id, name, birthday, email) values (5, 'DemoName', '1999-01-01', 'demo@gmail.com.com');
        ......
```

3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```SQL
        UPDATE employee SET name = 'demonameUpdate'
        WHERE id = 5
        RETURNING;

        UPDATE employee SET name = 'demonameUpdate4'
        WHERE id = 4
        RETURNING;

        UPDATE employee SET name = 'demonameUpdate2'
        WHERE id = 2
        RETURNING;

        UPDATE employee SET name = 'demonameUpdate1'
        WHERE id = 1
        RETURNING;

        UPDATE employee SET name = 'demonameUpdate3'
        WHERE id = 3
        RETURNING;
```

4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```SQL
        DELETE FROM employee
        WHERE id = 5
        RETURNING * ; 

        DELETE FROM employee
        WHERE id = 3
        RETURNING * ;

        DELETE FROM employee
        WHERE id = 4
        RETURNING * ;

        DELETE FROM employee
        WHERE id = 2
        RETURNING * ;

        DELETE FROM employee
        WHERE id = 1
        RETURNING * ;
```