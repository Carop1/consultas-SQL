# Consultas en bases de datos en SQL

1. Realice la inserción de los siguientes datos:

   ```sql
   INSERT INTO FABRICANTE(codigo,nombre) VALUES (1, 'Asus'),(2, 'Levono'),(3, 'Hewlett_Packard'),(4, 'Samsung'),(5, 'Seagate'),(6, 'Crucial'),(7, 'Gigabyte'),(8, 'Huawei'),(9, 'Xiaomi');
   
   ```

   ​				

```sql
INSERT INTO PRODUCTO(codigo,nombre,precio,codigo_fabricante) VALUES (1, 'Disco duro SATA3 1TB', 86.99, 5), 
(2, 'Memoria RAM DDR4 8GB', 120, 6), 
(3, 'Disco SSD 1 TB', 150.99, 4),
(4, 'GeForce GTX 1050Ti', 185, 7),
(5, 'GeForce GTX 1080 Xtreme', 755, 6),
(6, 'Monitor 24 LED Full HD', 202, 1), 
(7, 'Monitor 27 LED Full HD', 245.99, 1),
(8, 'Portátil Yoga 520', 559, 2),
(9, 'Portátil Ideapd 320', 444, 2),
(10, 'Impresora HP Deskjet 3720', 59.99, 3),
(11, 'Impresora HP Laserjet Pro M26nw', 180, 3);
```

## Consultas sobre una tabla

1. ```sql
   SELECT nombre FROM PRODUCTO;
   ```

   

2. ```sql
   SELECT nombre, precio FROM PRODUCTO;
   ```

   

3. ```sql
   SELECT codigo,nombre,precio,codigo_fabricante FROM PRODUCTO;
   ```

   

4. ```sql
   SELECT nombre,precio,precio*tasa_cambio AS precioUSD FROM PRODUCTO, (SELECT 1.18 AS tasa_cambio) AS conversion;
   ```

   

5. ```sql
   SELECT 
       nombre AS "nombre de producto",
       precio AS euros,
       precio * 1.18 AS dólares
   FROM 
       PRODUCTO;
   ```

   

6. ```sql
   SELECT 
       UPPER(nombre) AS nombre_en_mayusculas,
       precio
   FROM 
       PRODUCTO;
   ```

   

7. ```sql
   SELECT 
       LOWER(nombre) AS nombre_en_minusculas,
       precio
   FROM 
       PRODUCTO;
   ```

   

8. ```sql
   SELECT 
       UPPER(SUBSTRING(nombre FROM 1 FOR 2)) AS dos_primeros_caracteres
   FROM 
       FABRICANTE;
   ```

   

9. ```sql
   SELECT 
       nombre,ROUND(precio,1) AS rendondeado
   FROM 
       PRODUCTO;
   ```

   

10. ```sql
    SELECT 
        nombre,ROUND(precio,0) AS rendondeado
    FROM 
        PRODUCTO;
    
    ```

    

11. ```sql
    SELECT 
        p.codigo_fabricante 
    FROM 
        PRODUCTO AS p, FABRICANTE AS f
    WHERE 
        f.codigo = p.codigo_fabricante;
    ```

12. ```sql
    SELECT 
        DISTINCT p.codigo_fabricante 
    FROM 
        PRODUCTO AS p, FABRICANTE AS f
    WHERE 
        f.codigo = p.codigo_fabricante;
    
    ```

    

13. ```sql
    SELECT f.nombre
    FROM FABRICANTE AS f
    ORDER BY f.nombre Asc
    ```

    

14. ```sql
    SELECT f.nombre
    FROM FABRICANTE AS f
    ORDER BY f.nombre DESC
    ```

15. ```sql
    SELECT nombre, precio
    FROM PRODUCTO
    ORDER BY nombre ASC, precio DESC;
    ```

16. ```sql
    SELECT nombre, codigo
    FROM FABRICANTE
    LIMIT 5;
    ```

17. ```sql
    SELECT codigo, nombre
    FROM FABRICANTE
    LIMIT 3,3;
    ```

18. ```sql
    SELECT nombre, precio
    FROM PRODUCTOS
    ORDER BY precio ASC
    LIMIT 1;
    ```

19. ```sql
    SELECT nombre, precio
    FROM PRODUCTOS
    ORDER BY precio DESC
    LIMIT 1;
    ```

20. ```sql
    SELECT p.nombre
    FROM PRODUCTO AS p, FRABRICANTE AS f
    JOIN f ON p.codigo_fabricante = f.id
    WHERE f.id = 2;
    
    ```

    






