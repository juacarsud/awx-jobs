

curl -k -u elastic -H "Content-Type: application/json" -d @index.json -XPUT https://localhost:9200/iacprov


curl -k -u elastic -XGET -H 'Content-Type: application/json' 'https://10.73.13.226:9200/iacprov/_search' -d '
{
    "query" : {
        "match_all" : {}
    }
}'

curl -k -u elastic -XDELETE -H 'Content-Type: application/json' 'https://10.73.13.226:9200/iacprov/doc-type/YI6FXncBHalwL5zuD0SG

/var/cloudbees-jenkins-distribution/workspace/PROVISIONING/IBM_GTS_REGISTER_ELASTIC/roles/register_elastic

curl -k -XPUT -u elastic -H 'Content-Type: application/json' 'https://10.73.13.226:9200/iacprov/_mapping' -d '
{
  "properties": {
    "@timestamp": {
       "type": "date"
    }
  }
} '
curl -XPUT -H 'Content-Type: application/json' 'http://localhost:9200/iacprov/_mapping' -d '
{
  "properties": {
    "@timestamp": {
       "type": "date"
    }
  }
} '


Los templates deben tener tener la siguiente nomenclatura 
ANSRHL77
ANSW2K16

curl -k -XPOST -u elastic http://10.73.13.226:9200/test-index/_doc -H "Content-Type: application/json" -d @request.json