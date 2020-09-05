# Dynamo export - import

# An overview of tools to export from DynamodDB to CSV.
https://medium.com/@quodlibet_be/an-overview-of-tools-to-export-from-dynamoddb-to-csv-d2707ad992ac

# Export Dynamo to CSV

https://github.com/edasque/DynamoDBtoCSV

```sh
~/.aws/credentials
npm install
node dynamoDBtoCSV.js -t Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi -d

node dynamoDBtoCSV.js -t Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi -f output.csv
```

# Import
https://aws.amazon.com/blogs/database/implementing-bulk-csv-ingestion-to-amazon-dynamodb/

su-desinfection-register-dynamodb-csv-dump-stack
su-desinfection-register-dynamodb-csv-dump
Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi
registers_data_dump.csv

# Postgres import csv
https://www.postgresqltutorial.com/import-csv-file-into-posgresql-table/

```sql
CREATE TABLE registers (
    pk_id SERIAL,
    regSegundoNombre VARCHAR(50),
    regVehSeguros VARCHAR(50),
    regCreatedAt VARCHAR(50),
    regIsAcceptedTerms VARCHAR(50),
    regVehMailPropietario VARCHAR(50),
    regVehSOATCompany VARCHAR(50),
    regVehSegurosCompany VARCHAR(50),
    regVehRTMCompany VARCHAR(50),
    id VARCHAR(50),
    regOwnerUsername VARCHAR(50),
    regVehRTM VARCHAR(50),
    regFechaNacimiento VARCHAR(50),
    __typename VARCHAR(50),
    regPrimerApellido VARCHAR(50),
    regSegundoApellido VARCHAR(50),
    regVehEmpresa VARCHAR(50),
    createdAt VARCHAR(50),
    regVehNombrePropietario VARCHAR(50),
    regVehPlaca VARCHAR(50),
    regCelularConductor VARCHAR(50),
    regPrimerNombre VARCHAR(50),
    regVehTelefonoPropietario VARCHAR(50),
    regCedula VARCHAR(50),
    updatedAt VARCHAR(50),
    regVehSOAT VARCHAR(50),
    regOwnerId VARCHAR(50),
    regVideoSrc VARCHAR(50),
    regVehPropCedula VARCHAR(50),
    regLocation VARCHAR(50),
    regEpoch VARCHAR(50),
    location VARCHAR(50),
    insuranceSOAT VARCHAR(50),
    insuranceRTM VARCHAR(50),
    insurancePRC VARCHAR(50),
    company VARCHAR(50),
  PRIMARY KEY (pk_id)
)
```

```sql
COPY registers (regSegundoNombre,regVehSeguros,regCreatedAt,regIsAcceptedTerms,regVehMailPropietario,regVehSOATCompany,regVehSegurosCompany,regVehRTMCompany,id,regOwnerUsername,regVehRTM,regFechaNacimiento,__typename,regPrimerApellido,regSegundoApellido,regVehEmpresa,createdAt,regVehNombrePropietario,regVehPlaca,regCelularConductor,regPrimerNombre,regVehTelefonoPropietario,regCedula,updatedAt,regVehSOAT,regOwnerId,regVideoSrc,regVehPropCedula,regLocation,regEpoch)
FROM '/Users/robin8a/Documents/node_js_ws/DynamoDBtoCSV/output_1.csv' 
DELIMITER ',' 
CSV HEADER;

COPY registers (regSegundoNombre,regVehSeguros,regCreatedAt,regIsAcceptedTerms,regVehMailPropietario,regVehSOATCompany,regVehSegurosCompany,regVehRTMCompany,id,regOwnerUsername,regVehRTM,regFechaNacimiento,__typename,regPrimerApellido,regSegundoApellido,regVehEmpresa,createdAt,regVehNombrePropietario,regVehPlaca,regCelularConductor,regPrimerNombre,regVehTelefonoPropietario,regCedula,updatedAt,regVehSOAT,regOwnerId,regVideoSrc,regVehPropCedula,regLocation,regEpoch)
FROM '/Users/robin8a/Documents/node_js_ws/DynamoDBtoCSV/output_1.csv' 
DELIMITER ',' 
CSV HEADER;
```

```sql
SELECT 
   table_name, 
   column_name, 
   data_type 
FROM 
   information_schema.columns
WHERE 
   table_name = 'registers';

SELECT * FROM registers;

DELETE FROM registers;

UPDATE registers SET regsegundonombre = upper(regsegundonombre);

UPDATE registers SET regvehmailpropietario=lower(regvehmailpropietario);

SELECT DISTINCT regvehsoatcompany FROM registers;

UPDATE table
SET col = new_value
WHERE col = old_value
AND other_col = some_other_value;


UPDATE some_table
SET    column_x = CASE WHEN should_update_x THEN new_value_for_x ELSE column_x END
     , column_y = CASE WHEN should_update_y THEN new_value_for_y ELSE column_y END
     , column_z = CASE WHEN should_update_z THEN new_value_for_z ELSE column_z END
FROM   ...

```

# postgresql string functions

https://www.postgresql.org/docs/8.2/functions-datetime.html
https://w3resource.com/PostgreSQL/substring-function.php
https://popsql.com/learn-sql/postgresql/how-to-query-date-and-time-in-postgresql
https://www.postgresqltutorial.com/postgresql-to_date/

```sql

SELECT TO_DATE(regvehseguros, 'DD/MM/YYYY') FROM registers;

SELECT 
       CASE WHEN extract(month from TO_DATE(regvehseguros, 'DD/MM/YYYY')) = 3 THEN 'one'
            WHEN extract(month from TO_DATE(regvehseguros, 'DD/MM/YYYY')) = 2 THEN 'two'
            ELSE 'other'
       END
FROM registers;
```

## Is date
https://stackoverflow.com/questions/25374707/check-whether-string-is-a-date-postgresql

```sql
create or replace function is_date(s varchar) returns boolean as $$
begin
  perform s::date;
  return true;
exception when others then
  return false;
end;
$$ language plpgsql;


SELECT is_date(regvehseguros) FROM registers;

```

## Import csv to Dynamodb

https://acloudpage.com/2019/02/27/load-csv-to-aws-dynamodb/


## Store Serverless Ecommercee  
https://aws.amazon.com/blogs/mobile/appsync-microservices/