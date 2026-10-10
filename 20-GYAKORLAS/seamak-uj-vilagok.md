# Új gyakorló világok – sémahelyőrzők

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE TABLE city (
  city_id NUMBER PRIMARY KEY,
  name VARCHAR2(100) NOT NULL
);
CREATE TABLE person (
  person_id NUMBER PRIMARY KEY,
  full_name VARCHAR2(100) NOT NULL,
  email VARCHAR2(120),
  birth_date DATE,
  city_id NUMBER REFERENCES city(city_id)
);

CREATE TABLE customer (
  customer_id NUMBER PRIMARY KEY,
  name VARCHAR2(100) NOT NULL
);
CREATE TABLE order_hdr (
  order_id NUMBER PRIMARY KEY,
  customer_id NUMBER REFERENCES customer(customer_id),
  order_date DATE NOT NULL,
  status VARCHAR2(20)
);
CREATE TABLE order_item (
  order_id NUMBER REFERENCES order_hdr(order_id),
  line_no NUMBER,
  product_name VARCHAR2(100),
  qty NUMBER,
  price NUMBER,
  PRIMARY KEY (order_id, line_no)
);

CREATE TABLE movie (
  movie_id NUMBER PRIMARY KEY,
  title VARCHAR2(200) NOT NULL,
  release_year NUMBER
);
CREATE TABLE actor (
  actor_id NUMBER PRIMARY KEY,
  name VARCHAR2(100) NOT NULL
);
CREATE TABLE movie_cast (
  movie_id NUMBER REFERENCES movie(movie_id),
  actor_id NUMBER REFERENCES actor(actor_id),
  role_name VARCHAR2(100),
  PRIMARY KEY (movie_id, actor_id)
);

CREATE TABLE owner (
  owner_id NUMBER PRIMARY KEY,
  name VARCHAR2(100) NOT NULL,
  phone VARCHAR2(40)
);
CREATE TABLE car (
  car_id NUMBER PRIMARY KEY,
  plate VARCHAR2(20) UNIQUE,
  brand VARCHAR2(40),
  price NUMBER,
  reg_date DATE,
  owner_id NUMBER REFERENCES owner(owner_id)
);
```
