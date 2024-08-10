# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch`
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.


cds init bookshop
cd bookshop/
cds add tiny-sample


https://cap.cloud.sap/docs/node.js/cds-ql#select

# REPL
Initialse repl
```cds repl```

initialise test
```await cds.test()```

```cds.entities```

``` for (x in cds.entites) console.log(x)```

``` for (x of cds.entites) console.log(x)```

```SELECT.from(cds.entities['Books'])```

```await SELECT.from(cds.entities['Books'])```

```await SELECT.from(cds.entities['Books']).where({ID:'251'})```

```await SELECT.from('my.bookshop.Books',271)```

```await SELECT.from(cds.entities['Books']).columns('ID','title')```

```await SELECT.from(cds.entities['Books'], b => { b.ID, b.title })```

```await SELECT.from(cds.entities['Books']).where({stock:{'<':12}})```

```await SELECT.from(cds.entities['Books']).where({stock:{'<':12}})```

```await SELECT.from(cds.entities['Books']).columns('title').where({stock:{'<':12}})```

```await SELECT.from(cds.entities['Books']).columns('title as Name').where({stock:{'<':12}})```

```await SELECT.from(cds.entities['Books'].author, {ID:201, locale:'de'})```

insert with error (into wrong entity)
```await INSERT.into(cds.entities['Books']).entries({ID: 111,name: 'Enid Blyton',dateOfBirth: '1897-08-11',dateOfDeath: '1968-11-28',placeOfBirth: 'East Dulwich, London',placeOfDeath: 'Hampstead, London'})```

insert success
```INSERT.into(cds.entities['Authors']).entries({ID: 111,name: 'Enid Blyton',dateOfBirth: '1897-08-11',dateOfDeath: '1968-11-28',placeOfBirth: 'East Dulwich, London',placeOfDeath: 'Hampstead, London'})```

```await SELECT.from(cds.entities['Authors']).where({name:'Enid Blyton'})```

inset into Books
```await INSERT.into(cds.entities['Books']).entries({ID: 211,author_ID: 111,title: 'Five on a Treasure Island',descr: `When siblings Julian, Dick and Anne cannot go for their usual summer holiday to Polseath, they are invited to spend the summer with their Aunt Fanny and Uncle Quentin at their home Kirrin Cottage, in the coastal village of Kirrin.`,stock: 10,price: 13.13, currency_code: 'USD'})```

