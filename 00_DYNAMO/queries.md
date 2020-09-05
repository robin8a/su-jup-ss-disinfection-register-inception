```sql
CREATE TABLE registers (
    id SERIAL,
    regSegundoNombre VARCHAR(50),
    regVehSeguros VARCHAR(50),
    regCreatedAt VARCHAR(50),
    regIsAcceptedTerms VARCHAR(50),
    regVehMailPropietario VARCHAR(50),
    regVehSOATCompany VARCHAR(50),
    regVehSegurosCompany VARCHAR(50),
    regVehRTMCompany VARCHAR(50),
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
  PRIMARY KEY (id)
)
```
aws dynamodb scan \
    --table-name Register-ehtiz42qs5hirpzs4rikhmcx6a-disregapi \
    --query "Items[*].[regCedula.S, regVehPlaca.S, regVehSOAT.S, regVehSeguros.S, regVehNombrePropietario.S, regVehTelefonoPropietario.S,regVehMailPropietario.S, regCreatedAt.S,regOwnerId.S, regVideoSrc.S, regLocation.S, regIsAcceptedTerms.S, regOwnerUsername.S, regVehPropCedula.S,regVehEmpresa.S, regVehSOATCompany.S, regVehRTMCompany.S, regVehSegurosCompany.S]" \
    --output text > dataDump.csv




   