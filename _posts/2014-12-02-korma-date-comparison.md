---
layout: post_page
title: Timestamp comparison in Korma
---

It seems that I've been barking at the wrong tree.

I wanted to filter rows from MySQL based on column that is of `timestamp` type. In the project we are using [Korma](http://sqlkorma.com/) for interacting with DB.

After lots of time full of struggles while trying to use various date types that are available in Clojure, I've found out that to write your SQL WHERE condition based on `timestamp` column one should use plain old String. Amazing!

Here is an example that ilustrates how to work with `timestamp` type in the `where` clause with Korma:


```clojure
    (defn example []
      (select records
          (fields :date)
          (where {:date [< "2014-12-02"]})))
```

I've learned that lesson. I hope this might help for someone.


