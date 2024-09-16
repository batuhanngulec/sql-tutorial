Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.


1. film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

```SQL
        Select AVG(rental_rate) 
        AS average_rental_rate
        FROM film ;
```

2. film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```SQL
        SELECT COUNT(*) 
        AS count_as_films
        FROM film 
        WHERE title LIKE 'C%';
```

1. film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```SQL
        SELECT MAX(length) 
        AS max_length
        FROM film 
        WHERE rental_rate=0.99;
```

4. film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```SQL
        SELECT COUNT(DISTINCT replacement_cost) 
        AS unique_replacement_cost_count
        FROM film 
        WHERE length > 150 ;
```