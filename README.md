# Sequelize tips and tricks

## Introduction

The purpose of this guide is to provide guidance on building applications using Sequelize by showing tips and tricks about it. All examples were made using [AdventureWorks](https://www.microsoft.com/en-us/download/details.aspx?id=49502) database.

[Official documentation!](http://docs.sequelizejs.com/)
[Complementary documentation!](https://sequelize.readthedocs.io/en/latest/)

## Table of Content 

1. [Setup](#setup)
1. Structure
1. Mappings and Configurations
1. Migrations
1. Queries
1. Write Operations
1. Tests

## Setup

* Dowloading SQL Server Adventure Works database - https://www.microsoft.com/en-us/download/details.aspx?id=49502

* Loggin

You can enable/disable or customize sequelize logs using property `logging` in the sequelize configuration:
```typescript
const sequelize = new Sequelize('AdventureWorks2016CTP3', 'my-user', 'my-password', {
  ...
  logging: false // or true or console.log (or another log app)
  ... 
});
```

* Fixing de "sequelize deprecated String based operators are now deprecated. Please use Symbol based operators for better security" message.

To fix this message you need to set the `operatorsAliases` in the sequelize configuration properties with `false` or `Sequelize.Op`:

```typescript
const sequelize = new Sequelize('AdventureWorks2016CTP3', 'my-user', 'my-password', {
  ...
  operatorsAliases: false, // Sequelize.Op
  ... 
});
```

See more at: [http://docs.sequelizejs.com/manual/tutorial/querying.html#operators](http://docs.sequelizejs.com/manual/tutorial/querying.html#operators)

