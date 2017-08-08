# Instagram

A simple Instagram clone recreated with Phở Networks

## TODO

Instagram, by design, is very similar to [Twitter](https://github.com/pho-recipes/Twitter). The only difference would be 
the main object, [Tweet.pgql](https://github.com/pho-recipes/Twitter/blob/master/Nodes/Tweet.pgql) where the "content" field
would be a URL.

In short, this is what Instagram's Photo.pgql would look like:

```
# pho-graphql-v1

type Photo implements ObjectNode 
@edges(in:"User:Post, User:Like, User:Consume", out:"Tag")
@permissions(mod: "0x07555", mask: "0xfffff") # owner can write, all others can read and like (subscribe)
@properties(expires: 0, editable: false, volatile: false, revisionable: false)
{
    id: ID!,
    url: String! @constraints(regex: "^https?:\\/\\/.+\$"),
    create_time: Date! @now
}
```

The other changes would be:

* Mention should be renamed as Tag
* Twitter should be renamed as Instagram.

## 🏆🏆 Challenge 🏆🏆

Create Instagram, compile it, and make a pull request here on our Github repo.
