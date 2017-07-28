# Knex Migrations and Seeds Demo

## Setup

Clone repo:
```
git clone https://github.com/jamiesonbates/knex-migrations-seeds-demo.git
npm init -y
```

Setup DB:
```
createdb states_dev
```

## Configure knexfile && knex commands
Utilize article to:
* Configure knexfile.js so that you can connect to your database.
* Add a knex command to "scripts" within package.json

## Create a Migration
Create a migration file for a table named "cities.""

The cities table should have the following columns:
* id
* name
* state
* population
* timestamps

When you have created a migration file, use the following command to check your work:
```
npm run knex migrate:latest
```

If successful, you should see something like this:
![](https://students-gschool-production.s3.amazonaws.com/uploads/asset/file/615/1._fish__-Users-jamiesonbates-Projects-g56-lectures-knex-migrations-seeds-demo__fish__iTerm2__Today_at_8.00.24_AM.png)


Also run this command to view information about the created table:
```
psql states_dev -c '\d states'
```

You should be able to view details about the table you just created with a migration.

## Create a Seeds
Use the following data to create a seed for the table named "cities."

```javascript
const cities = [
  {
    name: 'Seattle',
    state: 'Washington',
    population: 704352
  },
  {
    name: 'Tacoma',
    state: 'Washington',
    population: 211277
  },
  {
    name: 'Bellingham',
    state: 'Washington'.
    population: 87574
  }
]
```
