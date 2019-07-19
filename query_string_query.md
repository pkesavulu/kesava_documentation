 {\"match\": {\"q\" "+":"+"\""+ query+"\"" +"}},\r\n" + 
 
 query string query:-
 ---
 
 
 GET posteventanalysisforhpflexnetworkarchitecturenonattendee18
{
  "query": {
    "match_all": {}
  }
}

get _all

GET /_cat/indices?v

get /_search

GET perforredingtonvmwaretrivandrumheldon26thfebanonattendee18/_search

GET /perforredingtonvmwaretrivandrumheldon26thfebanonattendee18/_search
{
  "query": {
    "bool": {
      "must": {
        "bool": {
          "must": [
            {"match": {"firstname": "Sreejith"}},
            {"match": { "lastname": "S"}}
          ]
        }
      }
    }
  }
}

GET /perforredingtonvmwaretrivandrumheldon26thfebanonattendee18/_search
{
  "query": {
    "bool": {
      "must": {
        "bool": {
          "should": [
            {"match": {"firstname": "Sreejith"}},
            {"match": { "lastname": "S"}}
          ]
        }
      }
    }
  }
}

GET /perforredingtonvmwaretrivandrumheldon26thfebanonattendee18/_search
{
  "query": {
    "bool": {
      "must": {
        "bool": {
          "must_not": [
            {"match": {"firstname": "Sreejith"}},
            {"match": { "lastname": "S"}}
          ]
        }
      }
    }
  }
}

GET /_search
{
  "query": {
  "simple_query_string":{
    "bool": {
      "must": {
        "bool": {
          "must": [
            {"match": {"query": "Sreejith"}},
            {"match": { "query": "S"}}
          ]
        }
      }
    }
  }
}
}


GET _search?q="Sreejith"


GET _search
{
 "query": {
   "match": {
     "FIELD": "Sreejith"
   }
 } 
}

GET /_search
{
  "query": {
    "simple_query_string": {
      "query": "s sreejith technopark",
      "default_operator": "AND"
    }
  }
}


--------------


java coding 
===

/*	String query = "firstname";
		String value = "Sreejith";
		// {\"match\": {\"firstname\": \"Sreejith\"}},\r\n" +
		HttpEntity entity1 = new NStringEntity(
				 "{\n" +
				"    \"query\" : {\n" +
				"    \"bool\": {\r\n" + 
				"      \"must\": {\r\n" + 
				"        \"bool\": {\r\n" + 
				"          \"should\": [\r\n" + 
				"            {\"match\": {"+"\""+query +"\""+":"+"\""+ value+"\"" +"}},\r\n" + 
				"            {\"match\": { \"lastname\": \"S\"}}\r\n" + 
				"          ]\r\n" + 
				"        }\r\n" + 
				"      }\r\n" + 
				"	}\n"+
				"} \n"+
				"}", ContentType.APPLICATION_JSON);
						
*/