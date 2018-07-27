# ElasticSearch:-
---
> communication with the search server is done through a HTTP REST API

	- curl -X<REST Verb> <Node>:<Port>/<Index>/<Type>/</ID>
	- Ex:- curl -XGET http://localhost:9200/employees/employee/123
	
> Schema-less JSON document (like NoSQL databases)

> Near real-time search	

> It is developed in java and it is document based search.

> developer name "Shay Banon"

### create a index:-
---

curl -XPUT http://localhost:9200/india 

### check the index details
---

curl -XGET http://localhost:9200/_cat/indices?v

it is use to find replics etc.

### delete a index :-
---

curl -XDELETE http://localhost:9200/india

### mapping:-
---

it is use to mapping the type

curl -XPUT http://localhost:9200/india{"mapping":{"states":{"properties":{"name":{"type":"text"}},"district":{"name":"text"}}}}

### Add date into type:-
---
curl -XPUT http://localhost:9200/india/101{ "statename":"ap","dist":"chittoor"}

### check the data in type:-
---
> curl -XPOST http://localhost:9200/india/_search

> curl -XGET http://localhost:9200/india/101

### udpate the type:-
---

PUT /india/_mapping/state
{
  
      "properties": {
        "statename": {
          "type": "text"
        },
        "dist": {
          "type": "text"
        },
        "pin":{
          "type":"double"
        }
      }
    }

### bool query:-
---

must:-
---
it follows the 'and' condition

GET /india/state
{
  "query": {
    "bool": {
      "must": [
        { "match": { "dist": "chittoor" } },
        { "match": { "dist": "uuu" } }
      ]
    }
  }
}

should:-
---
it follows the 'and' condition

GET /india/state
{
  "query": {
    "bool": {
      "should": [
        { "match": { "dist": "chittoor" } },
        { "match": { "dist": "uuu" } }
      ]
    }
  }
}

must_not:-
---

GET india/state/_search
{
  "query":{
    "bool": {"must_not": [
      {"match": {
        "statename": "ap"
      }
      }
    ]}
  }
}

Filter:-
---

GET india/state/_search
{
  "query":{
    "bool":{
      "must": [
        {"match_all": {}}
      ]
      , "filter": {"range": {
        "pincode":{
          "gte": 517501,
		  "lte": 600000
        }
      }}
    }
  }
}

udpate perticular fied:-
---

POST india/state/105/_update
{
  "doc": {"pincode":"12222"}
}

bulk load:-
---

POST /india/_bulk

{ "index" : {"_id" : "110","_type" : "state"} }
{"statename":"karnataka","dist":"banglore"}
{"index" : {"_id":"109","_type":"state"}}
{"statename":"maharastra","dist":"munbai"}

query search:-
---

GET /india/state/_search?q=chennai

> In this check the state chennai matched or not.

GET /india/state/_search?q=state:(ap AND tn)

> In this check the both are matched or not if it is matched will display that otherwise not display.

GET /india/state/_search?q=state:(ap OR tn)

> In this any one right or match will display the result

GET /india/state/_search?q=(state:(ap OR tn) AND dist:chittoor)

> First here apply the OR condition after will apply the AND condition.

GET /india/state/_search?q=statename:+utharapradesh -1235

> here use to arithmetic sings.

# Indices for Relations:-
---
Now i am comparing this elasticsearch enginee into RDBMs. You can (very roughly) think of an index like a database.

MySQL => Databases => Tables => Columns/Rows
ElasticSearch => Indices => Types => Documents with Properties

An ElasticSearch cluster can contain multiple Indices (databases), which in turn contain multiple Types (tables). These types hold multiple Documents (rows), and each document has Properties (columns).

So in your car manufacturing scenario, you may have a SubaruFactory index. Within this index, you have three different types:

People
Cars
Spare_Parts

Each type then contains documents that correspond to that type (e.g. a Subaru Imprezza doc lives inside of the Cars type. This doc contains all the details about that particular car).

> Searching and querying takes the format of: http://localhost:9200/[index]/[type]/[operation]

So to retrieve the Subaru document, I may do this:

```  
	$ curl -XGET localhost:9200/SubaruFactory/Cars/SubaruImprezza
```

Indices for Logging:-
--- 

Now, the reality is that Indices/Types are much more flexible than the Database/Table abstractions we are used to in RDBMs. They can be considered convenient data organization mechanisms, with added performance benefits depending on how you set up your data.

To demonstrate a radically different approach, a lot of people use ElasticSearch for logging. A standard format is to assign a new index for each day. Your list of indices may look like this:

logs-2013-02-22
logs-2013-02-21
logs-2013-02-20

ElasticSearch allows you to query multiple indices at the same time, so it isn't a problem to do:

```
  $ curl -XGET localhost:9200/logs-2013-02-22,logs-2013-02-21/Errors/_search=q:"Error Message"
``` 

Which searches the logs from the last two days at the same time. This format has advantages due to the nature of logs - most logs are never looked at and they are organized in a linear flow of time. Making an index per log is more logical and offers better performance for searching.

# queries:-
---

1.match,
2.range
3.fuzzy,
4.match_all

   
match:
---

curl -XPOST http://localhost:9200/_search

{
	"query":{
		"match":
		{
			"name":"kesava"
		}
	}
} 

range:
---

curl -XPOST http://localhost:9200/_search

{
	"query":{
		"range":
		{
			"id":{
			"gte":1,
			"lte":9
			}
		}
	}
} 

fuzzy:
---

curl -XPOST http://localhost:9200/_search

{
	"query":{
		"fuzzy":
		{
			"name":"pava*"
		}
	}
}

match_all:
---

curl -XPOST http://localhost:9200/_search

{
	"query":{
		"match_all":{}
	}
}

To load bulk data:-
---

curl -s -XPOST http://localhost:9200/_bulk --data-binary @finlname.json

sorting:-
---

{
  "query": {
    "match_all": {}
  },
  "sort": {
    "id": "desc"
  }
}

find missing fieds:-
---
{
  "query": {
    "constant_score": 
	{
		"filter":
		{
			"missing":
				{
				"fieds":"hm"
				}
		}
	}
   }
}

prefix:-
---
{
  "query": {
    "prefix": {
      "name": "ke"
    }
  }
}

wildcard:-
---
{
  "query": {
    "wildcard": {
      "name": "pa*"
    }
  }
}
