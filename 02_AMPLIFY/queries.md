## AppSync
### Credentials
sujups49f21a91_app_clientWeb
ClientId: 7bbd83mv76rsh8qm9e2749s3r
Username: javigomez@yopmail.com
Password: 4dm1n2020$$


```js
mutation {
  createCity(
    input: {
      title: "CALI", 
      selected: false, 
      key: "city"
      createdAt:""
    }
  ) {
    id
  }
}

query MyQuery {
  listCitys {
    items {
      id
      title
    }
  }
}


query MyQuery {
  listLocations {
    items {
      city {
        title
      }
      id
      title
    }
  }
}


```

```json
{
  "data": {
    "listCitys": {
      "items": [
        {
          "id": "29cc7d4d-bcd1-46b5-915e-174962b45e4b",
          "title": "CALI"
        },
        {
          "id": "6f403423-d11d-43d2-8a2e-ba87691432d2",
          "title": "BUCARAMANGA"
        },
        {
          "id": "cb032be6-867d-42ef-993a-961ae640606f",
          "title": "BOGOTA"
        },
        {
          "id": "cf2da0c6-d112-4800-8c8e-c2462af336d5",
          "title": "CUCUTA"
        },
        {
          "id": "c44a3228-4cf8-4b79-9100-640afc969335",
          "title": "PEREIRA"
        },
        {
          "id": "fd796958-24ed-4874-8e4d-e14a7fbcf588",
          "title": "MEDELLIN"
        }
      ]
    }
  }
}

```