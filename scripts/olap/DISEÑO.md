#  diseño de la bodega de datos 

## Alquiler

**Dim_Tiempo** llave surrogada es una llave diseñada para ser lo mas rápido posible.
- un numero, pequeño, con "cierto" orden
- no va a cambiar a pesar que la llave de negocio luego cambie 

| Columnan         | Tipo     | Restricciones |
|------------------|----------|---------------|
| date_key         | int      | PK,NN         |
| date_value       | date     | NN            |
| month_numbrer    | int      | NN            |
| month_name       | char(12) | NN            |
| year4            | int      | NN            |
| day_of_week      | int      | NN            |
| day_of_week_name | char(12) | NN            |
| year_month       | char(8)  | NN            |

**Fact_alquiler**

| Columnan         | Tipo     | Restricciones      |
|------------------|----------|--------------------|
| rental_Key       | int(8)   | PK,NN              |
| rental_id        | int      | UK,NN              |
| date_key         | int      | FK(dim_tiempo), NN |
| count_rental     | int      | NN                 |
