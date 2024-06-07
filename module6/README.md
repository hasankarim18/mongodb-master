`6-0:` [Intro to aggregation](#6-0-intro-to-aggregation)

`6-1:` [$match, $project aggregation peoject](#6-1-match-project-aggregation-peoject)

`6-2:` [$addFields, $out, $merge aggregation stage](#6-2-addfields-out-merge-aggregation-stage)

`6-3:` [$group, $sum, $push agrregation stage](#6-3-group-sum-push-agrregation-stage)

`6-4:` [explore more about $group and $project](#6-4-explore-more-about-group-and-project)

`6-5:` [explore $group with $unwind agrregation stage](#6-5-explore-group-with-unwind-agrregation-stage)

`6-6:` [$bucket,$sort, and $limit aggregation stage](#6-6-bucket-sort-and-limit-aggregation-stage)

`6-7:` [$facet, mutliple pipeline aggregation stage](#6-7-facet-mutliple-pipeline-aggregation-stage)

`6-8:` [$lookup stage, embedding vs referencing.mp4](#6-8-lookup-stage-embedding-vs-referencing-mp4)

`6-9:` [$what is indexing, COLLSCAN vs IXSCAN](#6-9-what-is-indexing-collscan-vs-ixscan)

`6-10:` [Explore compound index and text index](#6-10-explore-compound-index-and-text-index)

`6-11:` [Practice Task-2](#6-11-practice-task-2)

# `6-0` Intro to aggregation

#### # What is aggregation?

- Aggregation is a way of processing a large number of documents in a collection by means of passing them through `different stages`

- The stages make up what is known as a pipeline

- The `stages` in a pipeline can filter, sort, group, reshape, and modify documents that pass through the pipeline

<div>
    <img src="../imges/mongodb-aggregation-pipeline.png" width="100%" >
</div>

#### `$match` Stage - filters those documents we need to work with, those that fit our needs

#### `$group` Stage - Does the aggregation job

#### `$sort` Stage - sorts the resulting documents the way we require (assending or descending)

- The input of the pipeline can be a single collection, where others can be merged later down the pipeline.

#### `Syntax`

```
db.collection.aggregate(
    [
        {},                               // state-1 pipeline
        {},                               // state-2 pipeline
        {}                                // state-3 pipeline
    ]
)
```

# `6-1` $match, $project aggregation peoject

# `6-2` $addFields, $out, $merge aggregation stage

# `6-3` $group, $sum, $push agrregation stage

# `6-4` explore more about $group and $project

# `6-5` explore $group with $unwind agrregation stage

# `6-6` $bucket, $sort, and $limit aggregation stage

# `6-7` $facet, mutliple pipeline aggregation stage

# `6-8` $lookup stage, embedding vs referencing mp4

# `6-9` $what is indexing, COLLSCAN vs IXSCAN

# `6-10` Explore compound index and text index

# `6-11` Practice Task-2
