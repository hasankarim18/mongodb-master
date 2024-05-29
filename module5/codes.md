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
