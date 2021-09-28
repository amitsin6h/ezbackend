---
sidebar_position: 1
---

# EzModel

Schemas represent how data gets put into the database (DB)

You can imagine this by comparing it to excel,

- The **DB** is an **excel file** where the data is stored
- The **Table** refers to a single **excel sheet** where the data is stored. A single **schema** makes a table
- The **column names** which specify what goes into the excel sheet are the **schema properties**

## Create your first EzModel

For example, if we want a pet, add the following to `.ezb/index.ts`

```ts title=".ezb/index.ts"
import { EzModel, Type } from "@ezbackend/common";

const pets = new EzModel('Pets', {
    name: Type.VARCHAR, //String
    species: Type.VARCHAR,
    age: Type.INT //Integer
})
```

### Breaking it down

```ts
const pets = new EzModel('Pets',{...})
```
We make a new model using the `new EzModel()`. It will be stored with the name `Pets` in the database

```ts
{
    name: Type.VARCHAR, //String
    species: Type.VARCHAR,
    age: Type.INT //Integer
}
```

You can view all of the available types [here](types)

:::info
EzBackend automatically generates default CRUD routes for each of your defined models
:::

## Accessing your database

Once you run

```
npm run ezb

or

yarn ezb
```

Your backend will start, as well as a window with a complete reference of how exactly to connect to your backend and manipulate your database, generated automatically with [fastify-swagger](https://github.com/fastify/fastify-swagger)


<!-- TODO: Insert image of swagger CRUD -->