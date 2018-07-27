# SQL Access:-
---

Elasticsearch SQL aims to provide a powerful yet lightweight SQL interface to Elasticsearch.if you want more information about this to follow this link <https://www.elastic.co/guide/en/elasticsearch/reference/6.x/sql-overview.html>

Elasticsearch SQL:-
---

To start using Elasticsearch SQL, create an index with some data:

PUT /library/book/_bulk?refresh
{"index":{"_id": "Leviathan Wakes"}}
{"name": "Leviathan Wakes", "author": "James S.A. Corey", "release_date": "2011-06-02", "page_count": 561}
{"index":{"_id": "Hyperion"}}
{"name": "Hyperion", "author": "Dan Simmons", "release_date": "1989-05-26", "page_count": 482}
{"index":{"_id": "Dune"}}
{"name": "Dune", "author": "Frank Herbert", "release_date": "1965-06-01", "page_count": 604}

And now you can execute SQL using the SQL REST API right away:

how to produce output like table:-
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT * FROM library WHERE release_date < '2000-01-01'"
}

Which should return something along the lines of:

    author     |     name      |  page_count   | release_date
---------------+---------------+---------------+------------------------
Dan Simmons    |Hyperion       |482            |1989-05-26T00:00:00.000Z
Frank Herbert  |Dune           |604            |1965-06-01T00:00:00.000Z

how to produce output like json:-
---

POST /_xpack/sql?format=json
{
    "query": "SELECT * FROM library WHERE release_date < '2000-01-01'"
}

Which should return something like this:

{
  "columns": [
    {
      "name": "author",
      "type": "text"
    },
    {
      "name": "name",
      "type": "text"
    },
    {
      "name": "page_count",
      "type": "long"
    },
    {
      "name": "release_date",
      "type": "date"
    }
  ],
  "rows": [
    [
      "Dan Simmons",
      "Hyperion",
      482,
      "1989-05-26T00:00:00.000Z"
    ],
    [
      "Frank Herbert",
      "Dune",
      604,
      "1965-06-01T00:00:00.000Z"
    ]
  ]
}

You can also use the SQL CLI. There is a script to start it shipped in x-pack’s bin directory:

$ ./bin/elasticsearch-sql-cli
From there you can run the same query:

sql> SELECT * FROM library WHERE release_date < '2000-01-01';
    author     |     name      |  page_count   | release_date
---------------+---------------+---------------+------------------------
Dan Simmons    |Hyperion       |482            |1989-05-26T00:00:00.000Z
Frank Herbert  |Dune           |604            |1965-06-01T00:00:00.000Z

more information to follow this link <https://www.elastic.co/guide/en/elasticsearch/reference/6.x/sql-getting-started.html>

# Date and Time Functions:-
---

> This function use to get the data and time. if you want more information about this follow this link<https://www.elastic.co/guide/en/elasticsearch/reference/6.x/sql-functions-datetime.html>

### Extract the year from a date (YEAR)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT YEAR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS year"
}

     year
---------------
2018


### Extract the month of the year from a date (MONTH_OF_YEAR or MONTH)
---

POST /_xpack/sql?format=txt
{
"query":"SELECT MONTH_OF_YEAR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS month"
}
     month
---------------
2


### Extract the week of the year from a date (WEEK_OF_YEAR or WEEK)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT WEEK_OF_YEAR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS WEEK"
}

     week
---------------
8


### Extract the day of the year from a date (DAY_OF_YEAR or DOY)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT DAY_OF_YEAR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS DAY"
}

      day
---------------
50


### Extract the day of the month from a date (DAY_OF_MONTH, DOM, or DAY)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT DAY_OF_MONTH(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS day"
}

      day
---------------
19

### Extract the day of the week from a date (DAY_OF_WEEK or DOW). Monday is 1, Tuesday is 2, etc.
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT DAY_OF_WEEK(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS day"
}

      day
---------------
1


### Extract the hour of the day from a date (HOUR_OF_DAY or HOUR). Monday is 1, Tuesday is 2, etc.
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT HOUR_OF_DAY(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS hour"
}

     hour
---------------
10


### Extract the minute of the day from a date (MINUTE_OF_DAY)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT MINUTE_OF_DAY(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS minute"
}

    minute
---------------
623

### Extract the minute of the hour from a date (MINUTE_OF_HOUR, MINUTE)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT MINUTE_OF_HOUR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS minute"
};

    minute
---------------
23

### Extract the second of the minute from a date (SECOND_OF_MINUTE, SECOND)
---

POST /_xpack/sql?format=txt
{
    "query": "SELECT SECOND_OF_MINUTE(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS second"
}

    second
---------------
27


### Extract
---

As an alternative, one can support EXTRACT to extract fields from datetimes. You can run any datetime function with EXTRACT(<datetime_function> FROM <expression>). So

POST /_xpack/sql?format=txt
{
    "query": "SELECT EXTRACT(DAY_OF_YEAR FROM CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS day"
}

      day
---------------
50

is the equivalent to


POST /_xpack/sql?format=txt
{
    "query": "SELECT DAY_OF_YEAR(CAST('2018-02-19T10:23:27Z' AS TIMESTAMP)) AS day"
}

      day
---------------
50
