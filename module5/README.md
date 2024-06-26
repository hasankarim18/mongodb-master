`5-0:` [Introduction](#5-0-introduction)

`5-1-A:` [Install MongoDB compass and No SQL Booster Windows](#5-1-a-install-mongodb-compass-and-no-sql-booster-windows)

`5-1-B:` [Install MongoDB compass and No SQL Booster Max Linux](#5-1-b-install-mongodb-compass-and-no-sql-booster-mac-linux)

`5-2:` [Insert, InsertOne, find, findOne, field, filtering, project](#5-2-insert-insertone-find-findone-field-filtering-project)

`Special` [`MongoDb Operators`](#mongodb-operators)

`5-3:` [$eq, $neq, $gt, $gte, $lte](#5-3-eq-neq-gt-gte-lte)

`5-4:` [$in, $nin, implicit and condition](#5-4-in-nin-implicit-and-condition)

`5-5:` [$and, $or, implicit vs explicit](#5-5-and-or-implicit-vs-explicit)

`5-6:` [$exists, $type, $size / Element query operator](#5-6-exists-type-size)

`5-7:` [$all, $elemMatch](#5-7-all-elemmatch)

#### [Update Mongo Db](#update-mongo-db)

`5-8:` [$set, $addToSet, $push](#5-8-set-addtoset-push)

`5-9:` [$unset, $pop, $pull, $pullAll](#5-9-unset-pop-pull-pullall)

`5-10:` [ More about $set, how to explore documentation](#5-10-more-about-set-how-to-explore-documentation)

`5-11:` [delete documents, drop collection and how to explore by yoursef](#5-11-delete-documents-drop-collection-and-how-to-explore-by-yoursef)

`5-12:` [Practice task-1](#5-12-practice-task-1)

`5-13:` [Database Command List](#5-13-database-command-list)

`5-14:` [Mongodb Shell Setup](#5-14-mongodb-shell-setup)

## 5-0 Introduction

#### What we are going to learn ?

- Mongodb basic query
- Powerful Aggregation Framework
- Indexing for faster queries
- Express.js and it's core concept
- Mongoose Fundamentals
- Crud operation using Express, Mongoose and Typescript
- Assignment 2

#### What is `Mongodb`

- Mongodb is a NoSql database which helps us to store data in a JSON like format
- NoSql database break form traditional relational model
- Ideal for managing vast data.
- Mongodb stands out for its
  - scalibility
  - flxibility
  - performance
- Users include google, facebook, eBay etc.
- Big company use mongdb for their micro services

#### Why should we use MongoDb

- Scalable high-performance and open source.
- Document-oriented Database
- Cost-Effective solutions.
- Rich Ecosystem of Tools, Documentation and Community.
- In Traditional database you must follow schema
- But in Mongodb you can have felxibility
- You can put structure data in mongodb and if you wish you can put unstructured data in mongodb

<table>
    <tr>
        <th>Feature</th>
        <th>Mongodb</th>
        <th>Traditional Database</th>
    </tr>
    <tr>
        <td>Data Model</td>
        <td>Document-oriented</td>
        <td>Relational</td>
    </tr>
    <tr>
        <td>Schema</td>
        <td>Flexible</td>
        <td>Rigid</td>
    </td>
    <tr>
       <td>Scalability</td>
        <td>Horizontal and vertical</td>
        <td>Vertical</td>
    </tr>
    <tr>
     <td>Performance</td>
        <td>Optimized for unstructured or semi-structured data</td>
        <td>Optimized for sturctured quries</td>
    </tr>
    
</table>

---

<div>
    <img width="100%"  src="../imges/db-comparison.png" width="350" title="hover text">
</div>

---

- In simple terms
<table>
    <tr>
        <th>RDBMS</th>
        <th></th>
        <th>MongoDB</th>
    </tr>
    <tr>
        <td>Database</td>
        <td>>-- are called in mongodb -></td>
        <td>Database</td>
    </tr>
    <tr>
        <td>Tables</td>
         <td>>-- are called in mongodb -></td>
        <td>Collectins</td>
    </tr>
     <tr>
        <td>Rows</td>
         <td>>-- are called in mongodb -></td>
        <td>Documents</td>
    </tr>
    <tr>
        <td>Columns</td>
         <td>>-- are called in mongodb -></td>
        <td>Fields</td>
    </tr>
</table>

---

### Extra features of MongoDb

- Json-like Document (BSON)
- Indexing
- Aggregation Framework
- Security Features
- Free Atlas Database
- Mongodb Compass (GUI-> graphical user interface)

### Where Mongodb will be a good choice

- E-commerce applications
- Social media applications
- Gamming applications
- Web applications
- Mobile applicatins
- Real-time applications

## 5-1-A Install MongoDB compass and No SQL Booster Windows

- Install Mongodb shell
- go to c --> Program Files --> Mongodb --> Server --> 7.0 --> bin

- copy the path -- C:\Program Files\MongoDB\Server\7.0\bin

- go to serach box

- write "edit environment variable"

- dobule click on "path"

- click new

- paste the path (C:\Program Files\MongoDB\Server\7.0\bin)

- `check` version of mongodb shell version

- `mongod` --version

- `starting command`
  - mongosh
  - Write command as usuas on your terminal and use
  - You will not get suggestions here

## 5-1-B Install MongoDB compass and No SQL Booster Mac Linux

- Only for mac users

## 5-2 insert insertOne find findOne field filtering project

#### <u> Difference between </u> db.getCollection('test') and db.test

<u>For Example: </u>

- db.getCollection('test').find()
  <br> or <br>
- db.test.find()

both `db.getCollection('test')` and `db.test.find()` can be used for `CRUD` operation but

- `db.getCollection('test')` can used in `Dynamic Collection Names` when the collection name is stored in a variable or needs to be constructed dynamically.

  - অর্থাৎ daynamic query এর ক্ষেত্রে ব্যাবহৃত হবে

```
let collectionName = "test";
db.getCollection(collectionName).find();
```

- `db.test.find():` is for `Static Collection Names` Use db.test when the collection name is known and fixed at the time of writing the query.

```
db.test.find();
```

- এক্ষেত্রে collection name আগে থেকে জানা অর্থৎ fixed/static, কোন dynamic query এর ক্ষেত্রে ব্যবহৃত হবেনা ।

- [5-2 insert](#5-2-insert)
- [5-2 insertOne](#5-2-insertone)
- [5-2 find](#5-2-find)
- [5-2 findOne](#5-2-findone)
- [5-2 field filtering](#5-2-field-filtering)
- [5-2 project ](#5-2-project)

#### 5-2 insert

- shell command
  - type --> use databaseName
  - type --> db.collectionName.insertOne()
  - type --> db.collectionName.insertMany()

```
    db.user.insertOne({name:"user one"})
```

- in the above code db --> indicates which database you are using
- db.user ---> `user` is the collection under database
- db.user.insertMany --> is the

`insertMany` <br>

- Aray of object parameter হিসাবে দিতে হবে

#### 5-2 insertOne

#### 5-2 find

`db.practice.find({age:17})`

- এর মানে হল db-->practice Collection --> document --> field
- practice collection এর ভিতরে document {} --> একটা field হল ‍`age`
- অর্থাৎ collection এর সকল field খুজবে এবং যেসব document {} এ age নামক field পাবে সেই সব document কে output দেখাবে ।
- match হওয়া সকল document দেখাবে

#### 5-2 findOne

`db.practice.findOne({age:17})`

- How MongoDB Selects the Document

  - Natural Order: MongoDB typically returns documents in the natural order, which is the order in which they were inserted into the collection. However, this order can change due to updates, deletions, or other operations that may affect the physical storage of documents.

  - Arbitrary Selection: If there are multiple documents that match the query criteria, and no sort order is specified, MongoDB may return any one of these documents. This means the result can be somewhat arbitrary when using findOne.

#### 5-2 field filtering

- কি কি field filter out করে নিয়ে আসবা ।

- যদি document এর সব data দরকার না হয় শুধু মাত্র কিছু field এর data দরকার হয় তাহলে আমরা field filtering করতে পারি

```
db.practice.find({gender:"Male"}, {name:1, gender:1, age:1})
```

- এখানে find এর ভিতরে second parameter হিসাবে field filtering দেয়া হয়েছে
- এই query দ্বারা শুধুমাত্র name, gender, age এর data আসবে অন্য field এর data আসবেনা ।

```
{
	"_id" : ObjectId("6406ad63fc13ae5a40000066"),
	"name" : {
		"firstName" : "Otto",
		"lastName" : "Mirfin"
	},
	"gender" : "Male",
	"age" : 12
},

- আবার field filtering এ 1 এর জায়গায় 0 দিলে সেই গুলো বাদে অন্য গুলো আসবে ।

```

```
db.practice.find({gender:"Male"}, {name:0, gender:0, age:0})
```

- উপরের query তে সেই সব document আসবে যাদের gender:"Male" এবং সেখানে name, gender, age এই ৩ field বাদে অন্য সকল field এর value থাকবে ।

#### 5-2 project

- এই field filtering আমরা chaining করে করতে পারি `project` এর মধ্যমে

```
db.practice.find({gender:"Male"}).project({name:1, gender:1})
```

N.b - `project` শুধু মাত্র `find` এর জন্য ব্যাবহার করা যায় `findOne` এর ক্ষেত্রে `project` support করেনা । সেক্ষেত্রে আগের নিয়মে second parameter দিয়ে ব্যাবহার করতে হবে

---

---

## Mongodb Operators

- <a target="_blank" href="https://www.mongodb.com/docs/manual/reference/operator/">Mongodb operators documents Link</a>
<ul>
   <li>
       Query and Projection Operators
       <ul>
         <li> goto Sidebar --> Reference --> Operators -->Query and Projection Operators </li>        
         <ul>
            <li>Comparison Operators --> $eq, $gt, $gte, $in, $lt, $lte, $ne, $nin </li>
            <li>Logical query operators --> $and, $not, $nor, $or, (explicit operators) </li>
            <li>Element Query Operators --> $exists, $type, </li>
            <li>Evaluation Query Operators --> $expr, $jsonSchema, $mod, $regex, $text, $where</li>
            <li>Geospatial Query Operators --> $geoWithin, $center, $centerSphere, $box, $polygon, $geoIntersects, $geometry, $near, $minDistance, $maxDistance, $nearSphere, $geoWithinSphere</li>
            <li>Array Query Operators --> $all, $elemMatch(query), $size </li>
            <li>Bitwise Query Operators --> $bitsAllClear, $bitsAllSet, $bitsanyClear, $bitsAnySet </li>
            <li>Projection  Operators --> $(projection), $elemMatch(projection), $slice(projection), </li>
            <li>Miscellaneous Query Operators --> $comment, $rand, $natural </li>
         </ul>
       </ul>
   </li>
   <li>Update Operators</li>
   <li>Aggregation Stages</li>
   <li>Aggregation Operators</li>
</ul>
- Operators Resources
  -Query and Projection Operators
  - Goto Sidebar --> Reference --> Operators
    - Operators
- Update Operators

#### `Comparison Oeprator below 5-3 and 5-4`

### Thumb rule`: যখন কোন operator আনব তখন দুই পাসে second bracket দিয়ে দিব

## 5-3 $eq $ne $gt $gte $lte

- `$eq = equal`
- `$ne = not equal`
- `$gt = greater than`
- `$gte = greater than or equal to`
- `$lt = less than`
- `$lte = less than or equal to`

### $eq === equal to

- $eq has following form

```
{<field>: {$eq:<value>}}
```

- Example

```
db.practice.find({gender:{$eq:"Male"}})
// or
db.practice.find({age:{$eq:12}})
```

- প্রথমটায় যাদের gender শুধু মাত্র male তাদের কে খুজে নিয়ে আসবে
- age equal to 12

```
db.practice.find({age:{$gt:12}})  // greater than 12
db.practice.find({age:{$gte:12}}) // greater than or equal to 12
db.practice.find({age:{$lt:12}}) // less than 12
db.practice.find({age:{$lte:12}}) // less than or equal to 12

```

### $ne == not euqul

```
db.practice.find({age:{$ne:12}}).sort({age:-1}) // বড় থেকে ছো্ট
db.practice.find({age:{$ne:12}}).sort({age:1}) // ছোট থেকে বড়
```

- সকল collection search করবে এবং যেসব document এর ভিতরে age নামক field আছে তাদের যাদের যাদের value 12 নয় তাদেরকে দেখাবে ।

- sort এর মাধ্যমে data sort করা যায়, এখানে বয়স এর উপর ভিত্তি করে sort করা হয়েছে ।

## 5-4 $in, $nin, implicit and condition

- $in operator selects the `documents` where the value of a field equals any value in the specified array.

```
{ field: { $in: [<value1>, <value2>, ... <valueN> ] } }
```

- $in এর ভিতরে field value array আকারে দেয়া হয়,
- field এর যেসব value গুলো মিলবে সেসব document কে query করে নিয়ে আসবে ।

```
db.practice.find({age:{$in:[12,34,40,30]}}).project({name:1, age:1})
```

- Practice collection [{}, {}, {}], যেসব docment {} আছে তাদের ভিতরে age field এর ভিতর যেসব value 12,34,40,30 এই 4 টি সংখার যেকোন একটির সাথে মিলে যাবে সেই সব document গুলোকে show করবে ।
- অর্থাৎ যে document এর সাথে মিলবে সেই document কেই দিবে

### implicit and condition

#### implicit and

- `implicit (অন্তর্নিহিত) `: it is not explicitly defined by the system but happen automatically by the system is called implicit.
- অর্থাৎ এমন একটা বিহেভিয়র যা mongodb এর নিজস্ব সিস্টিম দ্বারা সয়ংক্রিয় ভাবে ঘটে । অর্তাৎ default behaviour.

- `implicit and` comma এর মাধ্যমে লেখা হয় for example, আমরা ১৮ থেকে ৩০ বছর বয়স যাদের document গুলো দেখতে চাই ।

```
db.practice.find({age:{$gt:18, $lt:30}}, {name:1,age:1}).sort({age:1})
```

- উপরে আমরা query `{age:{$gt:18, $lt:30}}` লিখছি, এই কমা দিয়ে ‍ সেপারেট করা কেই আমরা `inplicit and` বলতেছি । কেননা কমা হল এখানে একটা default mongodb behaviour.
- কমা দিয়ে `and` করতে পারতেছি

#### `implicity and` in `filed` query

```


db.practice.find({gender:"Male",age:18}) // ----১

db.practice.find({gender:"Male",age:{$gt:18}}) // ---- ২

db.practice.find({gender:"Male",age:{$gt:18, $lt:30}}) // ----৩

db.practice.find({gender:"Female",age:{$gt:18, $lt:30}}) // ----৪

```

১. সেই সব document যাদের gender = Male এবং বয়স ১৮

২. সেই সব document যাদের gender = Male এবং বয়স ১৮ এর বেশি

৩. সেই সব document যাদের gender = Male এবং বয়স ১৮ এর বেশি এবং ৩০ এর কম

৪. সেই সব document যাদের gender = `Female` এবং বয়স ১৮ এর বেশি এবং ৩০ এর কম

- একটা query example

```
// 1
db.practice.find(
    {
        gender:"Male",
        age: { $gt: 18, $lt: 30 }
    }, { name: 1, age: 1, gender: 1 }
)
    .sort({ age: 1 })
```

```
/// 2
db.practice.find(
    {
        gender: { $in: ["Male", "Female"] },
        age: { $gt: 18, $lt: 30 }
    }, { name: 1, age: 1, gender: 1 }
)
    .sort({ age: 1 })
```

---

1. {gender:"Male",age:{$gt:18, $lt:30}} == gender:Male ,বয়স ১৮ থেকে ৩০ <br>
   a. find এর ২য় parameter {name:1,age:1, gender:1} == query তে name,age, gender দেখাতে হবে <br>
   b. sort, age দিয়ে করা হয়েছে asscending order (ছোট থেকে বড় )

2. {gender:{$in:["Male", "Female"]},age:{$gt:18, $lt:30}} == gender:Male এবং Female ,বয়স ১৮ থেকে ৩০ <br>

```
db.practice.find(
    {
        gender:"Male",                          // gender Male হতে হবে
        age: {$nin:[18,20,22,24,26,28] },       // age 18,20,22,24,26,28 বাদে অন্য হতে হবে
        interests:{$in:['Cooking', "Gaming"]}   // interest Cooking অথবা Gaming যেকোন একটা হতে হবে
    },
     { name: 1, age: 1, gender: 1,interests:1 }  // find এর ২য় parameter -- কি কি দেখাবে
)
    .sort({ age: 1 })                            // age, assencding order এ sort করবে
```

## 5-5 $and $or implicit-vs-explicit

- implicit `or, and` and explicit `or  + and`
- find() এর ভিতর একই field ২ বার লেখা যাবেনা
  `db.practice.find({age:{$ne:15 }, age:{$lt:50}})` // wrong approach
- একই field এর ভিতর condition দিতে গেলে ওই field এর ভিতর ব্যাবহার করতে হবে এবং একই bracket এর ভিতর নিয়ে যেতে হবে

- example for implicit `and ` in a same field

```
db.practice.find({age:{$ne:15, $lt:30 }})

```

- example for `implicit or` in same field and different field

```
db.practice.find({age:{$ne:15, $lt:30 }, gender:"Male"}).project({age:1, gender:1}).sort({age:1})
```

### # Mongodb Logical Operators are called `Explicit operators`

# `$and` <br>

`{ $and: [ { <expression1> }, { <expression2> } , ... , { <expressionN> } ] }`

- comparison operator এর সময় আগে field তারপর second bracket দিয়ে operator
- loggical operator এর সময় আগে operator তার পর field

```
db.practice.find({age:{$gt:15, $lt:30 }, gender:"Male"}) // implicit and


db.practice.find({ $and: [{ age: { $gt: 18, $lt: 30 } }, { gender: "Male" }] }) // explicit and / logical and / logical oparator

```

- ভেঙ্গে ভেঙ্গে লিখলে

`implicit and` একই field দুই বার ব্যাবহার করা যাবেনা

```
db.practice.find(
    {
        age: { $gt: 18, $lt: 30 },                       // age field আগে এবং কমা দিয়ে দিয়ে implicit and
        gender: "Male"                                   // gender আর একটা field
    }
)
```

```
// explicit and এর জন্য
db.practice.find(
    {
        $and: [                                          // explicit / logical and প্রথমেই  and oparator
            { age: { $gt: 18, $lt: 30 } },               // array এর ভিতরে field সমূহ
            { gender: "Male" }
        ]
    }
)
```

- একই field দুইবার ব্যাবহার করা যাবে উপরের code কে নিচের মত করে লেখা যায়

```
db.practice.find(
    {
        $and: [
            { age: { $gt: 18 } },                                 // age field প্রথম বার
            { age: {$lt: 30 } },                                  // age field ২য় বার
            { gender: "Male" }
        ]
    }
)
```

- sort and project filter

```
db.practice.find(
    {
        $and: [
            { age: { $gt: 18 } },
            { age: { $lt: 30 } },
            { gender: "Male" }
        ]
    }
).project({ age: 1, gender: 1 })
    .sort({ age: 1 })
```

# `$or`

`db.inventory.find( { $or: [ { quantity: { $lt: 20 } }, { price: 10 } ] } )`

- যেকোন condition সত্য হলেই আসবে

```
db.practice.find({
    $or: [
        {interests:"Cooking"},                            // interests হয় Gardening অথবা Cooking হবে
        {interests:"Gardening"}
        ]
}).project({
    interests:1
})

// or using $in comparison oparator

db.practice.find({
    $or: [
        {interests:{$in:["Cooking", "Gardening"]}},
        ]
}).project({
    interests:1
})

```

### Array of object এর ভিতর query `explicit or`

- এমন document গুলো চাই যাদের মধ্যে PYTHON অথবা JAVASCRIPT যেকোন একটি আছে

```
db.practice.find(
    {
        $or: [
                {"skills.name":"JAVASCRIPT"},
                {"skills.name":"PYTHON"},
            ],

    }
    ).project({skills:1})
```

- উপরের code `implicit in` দিয়েও করা সম্ভব field এর নাম same হলে

```
db.practice.find(
    {
        "skills.name": { $in: ["JAVASCRIPT", "PYTHON"] }
    }).project({ "skills.name": 1, "skills.level": 1 })
```

-

# `$not`

`{ field: { $not: { <operator-expression> } } }` // array হবেনা

- performs a logical `NOT` operation on the `specified <operator-expression>` and selects the documents that do not match the <operator-expression>. This includes documents that do not contain the `field`

```
db.inventory.find( { price: { $not: { $gt: 1.99 } } } )
```

- This query will select all documents in the `inventory` collection where:
  - The `price` field value is less than or equal to 1.99 or
  - The `price` does not exists

# `$nor`

- `$nor` performs a logical `NOR` operation on an array of one or more query expression and selects the documents that fail all the query expression in the array.
  `{ $nor: [ { <expression1> }, { <expression2> }, ...  { <expressionN> } ] }`
- For Example

```
db.inventory.find( { $nor: [ { price: 1.99 }, { sale: true } ]  } )
```

#### This query will return all document that:

- contain the `price` field whose value `is not equal to 1.99` and contain `sale` field value `is not equal to true` or

- Contain the `price` field whose value `is not equal to 1.99` but do not containthe `scale` field or

- do not contain the `price` field but not contain the `sale` field whose value is not equal to `true` or

- do not contain the `price` field and do not contain the sale

## 5-6 $exists, $type, $size

# Element query operator

- element query return data based on field existence or data types
- এমন কয়েরি যা document এ কোন field আছে কিনা তা খুজে বের করা
- অর্থাৎ কোন একটা field docuement এ exists করে কিনা তা দেখাবে

# `$exists`

- This operator matches documents that contain or do not contain a specific field
- `Syntax`: `{ field: { $exists: <boolean> } }`

- when `<boolean>` is true,$exists matches the document that contain the field, including documents where the field value is `null`.

- If `<boolean>` is false, the query returns only the documents that do not contain the field.

```
db.practice.find({age:{$exists:false}})  // - সেসব document গুলোকে দেখোবে যেখানে `age` field টা নাই


db.practice.find({age:{$exists:true}})  // - সেসব document গুলোকে দেখোবে যেখানে `age` field টা আছে
```

- যদি field না থাকে তাহলে কোন result show করবে না 0 result দিবে

```
db.practice.find({unknown:{$exists:true}}) // 0 result return করবে কেননা unknown নামের কোন field নাই
```

- just বলে দিবে field টা আছে নাকি নাই থাকলে result show করবে না থাকলে result 0 দেখাবে ‍/ show করবেনা

# `$type`

`{ field: { $type: <BSON type> } }`
<br> it cal also take array as input<br>

`{ field: { $type: [ <BSON type1> , <BSON type2>, ... ] } }`

- আমরা ইচ্ছা করলে type search করতে পারব
- selects documents where the value of the field is an instance of the specifie <a target="_blank" href="https://www.mongodb.com/docs/manual/reference/operator/query/type/#std-label-document-type-available-types">BSON Type </a>.

```
db.practice.find({
    $and:[
        {company:{$exists:true}},
        {company:{$type:"null"}}
        ]
}).project({name:1, company:1})
```

- উপরের উদাহরণে $and operator use করা হয়েছে
- `$exists` দ্বারা query হয়েছে যাদের company field আছে
- `$type` দ্বারা query হয়েছে যাদের company field এর value "null" অর্থাৎ value এর type check করা হয়েছে ।

- simplified version only type search ⬇️

```
db.practice.find({
    company:{$type:"null"}
}).project({name:1, company:1})
```

```
db.practice.find({
    friends:{$type:"array"}
})
```

- ⬆️ will show all the documents in collection practice which have a `friend field` and this `field` is an `array`

# `$size`

`db.collection.find( { field: { $size: 2 } } );`

- Only for `array`
- The `$size` operator matches any array with the number of elements specified by the argument.

- ⬇️ এমন document সমূহ দেখাও যাদের friend array তে ৩ টা element আছে

```
db.practice.find({
    friends:{$size:3}
}).project({
    friends:1
})
```

- ⬇️ এমন document সমূহ দেখাও যাদের friend array তে 0 টা element আছে অর্থাৎ ‍friend field টা empty array

```
db.practice.find({
    friends:{$size:0}     // শুধুমাত্র সেই document কেই select করবে যার friend:[]
}).project({              // অর্থাৎ empty array
    friends:1
})
```

## 5-7 $all $elemMatch

- আমরা জানব
  - `array qurey`
  - `object query`
  - `array of object query`

⭐ Array query <br>

- ⬇️ এখানে interrests field ‍array এর ভিতরে search করবে এবং interests:[..] field array এর যেকোন element "Cooking" হলেই সেই document কে দেখাবে

```
db.practice.find({
    interests:"Cooking"
}).project({interests:1})
```

- ⬆️ উপরের query কে নিচের ⬇️ মত `$in` operator দিয়েও করা যায়

```
db.practice.find({
    interests:{$in:["Cooking"]}
}).project({interests:1})
```

- ⭐ array position হিসাব করে আমরা data বের করতে চাই
- দর ২ নম্বর index এ “cooking” আছে এমন data বের করতে চাই

```
db.practice.find({
    "interests.2":{$in:["Cooking"]}
}).project({interests:1})
```

or

```
db.practice.find({
    "interests.2":"Cooking"
}).project({interests:1})
```

### exactly match search in array

```
db.practice.find({
    "interests":[ "Cooking", "Writing", "Reading" ]
}).project({
    interests:1
})
```

- ⬆️ same to same array will be matched and same array with same index position will be returned.

# `$all`

- যেকোন position এই থাকুক না কেন element গুলো থাকলেই হবে

`{ <field>: { $all: [ <value1> , <value2> ... ] } }`

```
db.practice.find({
    "interests": {$all: [ "Cooking", "Writing", "Reading" ]}
}).project({
    interests:1
})
```

- এটা exact match করবেনা শুধু মা element গুলো থাকলেই হবে

### query in `array of object` like array

```
db.practice.find({
    "skills.name":"JAVASCRIPT"
}).project({
    skills:1
})
```

### exact match query in `array of object`

```
db.practice.find({
    skills:{
        name:'JAVASCRIPT',
        level:"Expert",
        isLearning:false
    }
}).project({
    skills:1
})
```

# `$elemMatch`

- `এখন আমরা চাই element match করুক exact match না করুক `
- আমরা namme:"JAVASCRIPT" ও level:"Expert" চাই কিন্তু inLearning true / false হতে পারে

```
db.practice.find({
    skills:{$elemMatch:{name:"JAVASCRIPT", level:"Expert"}}
}).project({
    skills:1
})
```

# Update Mongo Db

## 5-8 $set $addToSet $push

### `$set` --> update primitive value

### `$addToSet` --> update array but `do not allow` duplicate value

### `$push` --> update array but `allow` duplicate value

# `$set` popular update operator

- কাকে অর্থৎ কোন document কে update করব
- $set -- কোন কোন field update করব // কি আপডেট করব

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")}, // যে document কে update করা হবে
    {
        $set:{                                      // $set --> takes object
            age:100                                // field: updated_value
        }
   }
)

```

- field যদি object হয়ে থাকে

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")},
    {
        $set:{
            age:100,
            "name.firstName":"Hasan Mahbub"             // field property dobule quatation
                                                        // দিয়ে access করতে হবে
        }
    }
    )
```

- Primitive value এর জন্য $set কোন প্রবলেম নয়

- but for non-primitive value $set will replace the previous value and rewrite new value

- for non-primitive, if data is entirely replaced by new data you can use `$set`, otherwise user other operators like `$addToSet`

# `$addToSet` --

- The $addToSet operator adds a value to an array unless the value is already present, in which case $addToSet does nothing to that array.
- `$addToSet` operator array তে নতুন value add করে, যদি আগে সেই value থেকে থাকে তাহলে `$addToSet` কোন change করবেনা ।
- Array এর ভিতর set করে দিবে কিন্তু duplicate value আসবেনা

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")},
    {
        $set:{
            age:80,
            "name.firstName":"Hasan Mahbub",
        },
        $addToSet: {
            interests:"Gamming"
        }
    }
    )
```

- before update: interest:["Cooking","Reading", "Writting"]
- after update: interest:["Cooking","Reading", "Writting", "Gamming"]

- `$each` modifire
- একের অধিক value সেট করতে হলে `$each` modifire use করতে হবে

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")},
    {
        $set:{
            age:80,
            "name.firstName":"Hasan Mahbub",
        },
        $addToSet: {
            interests:{$each:["Gamming", "Travelling", "Swimming"]}
        }
    }
    )
```

# `$push`

- `$addToSet` এর মতই কিন্তু duplicate value allow করবে আর `$addToSet` কখনই duplicate value এলাও করবেনা ।

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")},
    {
        $set:{
            age:80,
            "name.firstName":"Hasan Mahbub",
        },
        $addToSet: {
            interests:{$each:["Gamming", "Travelling", "Swimming"]}
        }
    }
    )
```

# Delete Mongo Db

## 5-9 $unset $pop $pull $pullAll

#### `$unset` ---> deletes a perticular field

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000065")},
    {
      $unset:{birthday:""}               // birthday field will be removed
    }
    )

```

#### `$pop` ---> remove first or last element of an array <br>

      `{ $pop: { <field>: <-1 | 1>, ... } }` 1 == last element <br/>
      `{ $pop: { <field>: <-1 | 1>, ... } }` -1 == first element <br/>

#### `$pull` ---> remove first or last element of an array

#### `$pullAll` ---> remove first or last element of an array

## 5-10 More about $set, how to explore documentation

- $set in `object`

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000066")},
    {
      $set:{
          "address.city":"Dhaka123"                      // object এর ভিতরের property change
      }
    }
    )

```

- Updating multiple objects

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000066")},
    {
      $set:{
          "address.city":"Dhaka123",
          "address.country":"Bangladesh123",
          "address.postCode":"1200",
          "address.postalCode":7600
      }
    }
    )
```

- Updating `Array of Objects`

```
db.practice.updateOne(
    {"_id" : ObjectId("6406ad63fc13ae5a40000066"), "education.major":"History"},
    {
      $set:{
          "education.$.major":"Cse"
      }
    }
    )

```

- `$` signifies first property matched

## 5-11 delete documents, drop collection and how to explore by yoursef

## 5-12 Practice task-1

## 5-13 Database Command List

<table>
    <tr>
        <th>
            Purpose
        </th>
        <th>
            Command
        </th>
    </tr>
    <tr>
        <td>
            Create Database
        </td>
        <td>
            use databaseName (use practice)
        </td>
    </tr>
    <tr>
        <td>
            Show all Database
        </td>
        <td>
            show database
        </td>
    </tr>
    <tr>
        <td>Create Collection</td>
        <td> db.createCollection("collection name") </td>
    </tr>
    <tr>
        <td>insert One data in collection</td>
        <td>
        db.getCollection("collectionName").insertOne({name:"Next Level"})
        </td>
    </tr>
    <tr>
        <td>Find a collection</td>
        <td>
            db.getCollection("collectionName").find()
        </td>
    </tr>
    <tr>
        <td>
        </td>
        <td></td>
    </tr>
</table>

## # 5-14 Mongodb Shell Setup

- Install Mongodb shell
- go to c --> Program Files --> Mongodb --> Server --> 7.0 --> bin

- copy the path -- C:\Program Files\MongoDB\Server\7.0\bin

- go to serach box

- write "edit environment variable"

- dobule click on "path"

- click new

- paste the path (C:\Program Files\MongoDB\Server\7.0\bin)

- `check` version of mongodb shell version

- `mongod` --version

- `starting command`
  - mongosh
  - Write command as usuas on your terminal and use
  - You will not get suggestions here

```

```

```

```

```

```
