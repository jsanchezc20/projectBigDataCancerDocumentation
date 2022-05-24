=CONCAT("C";C2;"___";E2)
=CONCAT("C";C2;)

Importar CSV a MySQL

1 Crear tabla:
CREATE TABLE diseases_cleanup (
    id						MEDIUMINT UNSIGNED NOT NULL AUTO_INCREMENT,
	country_code			CHAR(2) NOT NULL,
	year					SMALLINT UNSIGNED NOT NULL,
	sex						BOOLEAN NOT NULL,
	deaths_0				SMALLINT UNSIGNED NOT NULL,
	deaths1					SMALLINT UNSIGNED NOT NULL,
	deaths2					SMALLINT UNSIGNED NOT NULL,
	deaths3					SMALLINT UNSIGNED NOT NULL,
	deaths4					SMALLINT UNSIGNED NOT NULL,
	deaths5_9				SMALLINT UNSIGNED NOT NULL,
	deaths10_14				SMALLINT UNSIGNED NOT NULL,
	deaths15_19				SMALLINT UNSIGNED NOT NULL,
	deaths20_24				SMALLINT UNSIGNED NOT NULL,
	Deaths25_29d			SMALLINT UNSIGNED NOT NULL,
	deaths30_34				SMALLINT UNSIGNED NOT NULL,
	deaths35_39				SMALLINT UNSIGNED NOT NULL,
	deaths40_44				SMALLINT UNSIGNED NOT NULL,
	deaths45_49				SMALLINT UNSIGNED NOT NULL,
	deaths50_54				SMALLINT UNSIGNED NOT NULL,
	Deaths55_59				SMALLINT UNSIGNED NOT NULL,
	deaths60_64				SMALLINT UNSIGNED NOT NULL,
	deaths65_69				SMALLINT UNSIGNED NOT NULL,
	deaths70_74				SMALLINT UNSIGNED NOT NULL,
	Deaths75_79d			SMALLINT UNSIGNED NOT NULL,
	Deaths80_84d			SMALLINT UNSIGNED NOT NULL,
	deaths85_89				SMALLINT UNSIGNED NOT NULL,
	deaths90_94				SMALLINT UNSIGNED NOT NULL,
	deaths95_or_mored		SMALLINT UNSIGNED NOT NULL,
	deaths_age_unspecified	SMALLINT UNSIGNED NOT NULL,
	deaths0_days			SMALLINT UNSIGNED NOT NULL,
	deaths1_6days			SMALLINT UNSIGNED NOT NULL,
	deaths7_27days			SMALLINT UNSIGNED NOT NULL,
	deaths28_365days		SMALLINT UNSIGNED NOT NULL,
	disease_type_code		CHAR(3)	NOT NULL,
	PRIMARY KEY (id)
);

2 Iniciar usuario en consola:
C:\xampp\mysql\bin
mysql -u admin -p
JsZT*-Hf!t_DWwq)

3 Cambiar a la Base de datos
use big_data_cancer

3 Importar datos:
LOAD DATA INFILE 'D:\ProjecteM12\projectBigDataCancerDocumentation\data\diseases_cleanup.csv'
INTO TABLE diseases_cleanup 
FIELDS TERMINATED BY ',' 
ENCLOSED BY '"' 
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;

4 Importar diseases_data.sql
Iniciar usuario en consola
C:\xampp\mysql\bin

Escribir comando
mysql -u admin -p big_data_cancer < D:\ProjecteM12\projectBigDataCancerDocumentation\data\diseases_data.sql

pedirá password
JsZT*-Hf!t_DWwq)

Si da fallo hay que modificar el my.ini
max_allowed_packet=32M
