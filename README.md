# Sequelize tips and tricks

## Introduction

The purpose of this guide is to provide guidance on building applications using Sequelize by showing tips and tricks about it. All examples were made using AdventureWorks database.

[Official documentation!](http://docs.sequelizejs.com/)

## Table of Content 

1. [Setup](#setup)
1. Structure
1. Log
1. Mappings and Configurations
1. Migrations
1. Queries
1. Write Operations
1. Tests

## Setup

* Fixing de "sequelize deprecated String based operators are now deprecated. Please use Symbol based operators for better security" message.

To fix this message you need to set the `operatorsAliases` in the sequelize configuration properties with `false` or `Sequelize.Op`

```typescript
const sequelize = new Sequelize('AdventureWorks2016CTP3', 'my-user', 'my-password', {
  ...
  operatorsAliases: false, // Sequelize.Op
  ... 
});
```

See more at: [http://docs.sequelizejs.com/manual/tutorial/querying.html#operators](http://docs.sequelizejs.com/manual/tutorial/querying.html#operators)
