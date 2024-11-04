# SQL Sorguları Readme Dosyası

Bu döküman, belirli SQL sorgularının nasıl çalıştığını ve ne amaçla kullanıldığını açıklamaktadır. Her sorgu, bir veritabanı üzerinde belirli bir veriyi çekmek, saymak veya filtrelemek için hazırlanmıştır. 

---

## Sorgular

### 1. Farklı Replacement Cost Değerlerini Listeleme

```sql
SELECT DISTINCT replacement_cost FROM film;
```
Bu sorgu, film tablosundaki replacement_cost sütununda bulunan benzersiz (tekrar etmeyen) değerleri listeler. DISTINCT ifadesi, aynı değerlerin yalnızca bir kez gösterilmesini sağlar. Bu sayede, farklı replacement_cost değerlerini görebiliriz.

### 2. Farklı Replacement Cost Değerlerinin Sayısını Bulma
```sql
SELECT COUNT(DISTINCT replacement_cost) FROM film;
```
Bu sorgu, film tablosundaki replacement_cost sütununda kaç farklı değer olduğunu döndürür. COUNT ve DISTINCT ifadesiyle, bu sütundaki tekrar etmeyen (benzersiz) değerlerin toplam sayısı elde edilir.

### 3. "T" ile Başlayan ve Rating Değeri "G" Olan Film Sayısını Bulma
```sql
SELECT COUNT(*) FROM film 
WHERE title LIKE 'T%' AND rating = 'G';
```
Bu sorgu, film tablosundaki title sütununda "T" harfi ile başlayan ve rating sütunu "G" olan film kayıtlarının sayısını döndürür. LIKE 'T%' ifadesi, "T" ile başlayan film isimlerini, rating = 'G' ifadesi ise rating sütununda değeri "G" olan kayıtları filtreler.

### 4. İsmi 5 Karakterden Oluşan Ülke Sayısını Bulma
```sql
SELECT COUNT (*) FROM country
WHERE LENGTH (country) = 5;
```
Bu sorgu, country tablosundaki country sütununda 5 karakter uzunluğunda olan ülke isimlerinin sayısını döndürür. LENGTH fonksiyonu, ülke isimlerinin uzunluğunu belirlemek için kullanılır ve WHERE ifadesi, uzunluğu 5 olanları filtreler.

### 5. "R" veya "r" Harfi ile Biten Şehir İsimlerinin Sayısını Bulma
```sql
SELECT COUNT(*) FROM city
WHERE city ILIKE '%r';
```
Bu sorgu, city tablosundaki city sütununda "R" veya "r" harfi ile biten şehir isimlerinin sayısını döndürür. ILIKE ifadesi büyük/küçük harf duyarsız bir eşleşme sağlar ve '%r' deseni, "R" veya "r" harfiyle biten şehir isimlerini bulur.

