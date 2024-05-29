- [explicit and implicit and](#explicit-and-implicit-and)
- [sort and project filter](#sort-and-project-filter)

### implicit and

```
db.practice.find({age:{$gt:18, $lt:30}})
```

- Running query age greater than 18 less than 30 `and === ,`
- কমা দিয়ে `and` করতে পারতেছি

### implicit and in field query

```
db.practice.find({gender:"Male",age:18}) // ----১

db.practice.find({gender:"Male",age:{$gt:18}}) // ---- ২

db.practice.find({gender:"Male",age:{$gt:18, $lt:30}}) // ----৩

db.practice.find({gender:"Female",age:{$gt:18, $lt:30}}) // ----৪

```

- একটা query example

```

db.practice.find(
    {gender:"Male",age:{$gt:18, $lt:30}}
    ,{name:1,age:1, gender:1}
    )
    .sort({age:1})

db.practice.find(
    {
        gender: { $in: ["Male", "Female"] },
        age: { $gt: 18, $lt: 30 }
    }, { name: 1, age: 1, gender: 1 }
)
    .sort({ age: 1 })
```

- example for implicit `and ` in a same field

```
db.practice.find({age:{$ne:15, $lt:30 }})

```

- example for `implicit or` in same field and different field

```
db.practice.find({age:{$ne:15, $lt:30 }, gender:"Male"}).project({age:1, gender:1}).sort({age:1})
```

### explicit and implicit and

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

### sort and project filter

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
