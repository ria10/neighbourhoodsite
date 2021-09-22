# Neighbourhood Community Website

## Description

This API provides all the endpoints for retrieving and editing information regarding houses and their owners.

## Technologies

- SQL
- PostgreSQL
- JavaScript

## Request Response Path

| Path        | HTTP Verb | Action |
|-------------|-----------|--------|
| /houses     | GET       | show   |
| /houses/:id | GET       | show   |
| /houses     | POST      | create |
| /houses/:id | PATCH     | edit   |
| /owners     | GET       | show   |
| /owners/:id | GET       | show   |
| /owners     | POST      | create |
| /owners/:id | PATCH     | edit   |
| /owners/:id | DELETE    | delete |

## Schemas

Require two tables: 

| Houses       | Data Type       |
|--------------|-----------------|
| house_id     | primary key INT |
| house number | VARCHAR         |
| street name  | VARCHAR         |
| zip code     | VARCHAR         |
| owner_id     | INT             |

for the houses and

| Owners    | Data Type       |
|-----------|-----------------|
| owner_id  | primary key INT |
| firstName | VARCHAR         |
| lastName  | VARCHAR         |
| DOB       | DATE            |
| house_id  | INT             |

for the owners.

## Query Parameters

| q (string format) | SW1P1RT    | Search query term or phrase.        |
| name              | Smith      | Last name of owner.                 |
| street            | highstreet | Street of the address of the house. |
| zip               | SW1P1RT    | Zip code of the house.              |
| age               | 30-50      | Age bracket of the owner.           |
| size              | 4          | Size of the household.              |

Examples of request paramters:

`/owners?size=4&name=smith`
`/houses?street=highstreet&zip=sw1p1rt`

Responses returned will be in a JSON format for example for houses we have

    {
        "house_number": "2",
        "street_name": "highstreet",
        "zip": "sw1p1rt",
        "owner_name": "John Smith",
    }

for owners we have

    {
        "owner_name": "John Smith",
        "age": 40,
        "household_size": 4
    }