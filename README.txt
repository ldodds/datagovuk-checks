A set of checks to test RDF datasets against the best practices of the data.gov.uk project

The tests consist of a set of SPARQL queries that are used to probe the data. 

The tests are designed to be run using the sparql-check command-line tool which is available from:

http://github.com/ldodds/sparql-check

The tool supports:

* Parsing RDF files and applying tests to them
* Querying a SPARQL endpoint
* Querying data held in a local Jena TDB index

The typical workflow will therefore be:

* Convert or generate the data
* Load the data into a triple store with a SPARQL endpoint, or locally using TDB
* Run the tests to generate a best practice report
 
Assuming the data is in SPARQL endpoint, you can run the tests like so:

export SPARQLCHECK_HOME=/tools/sparql-check
java -jar $SPARQLCHECK_HOME/sparql-check.jar -test all-tests.ttl -id http://source.data.gov.uk/acceptance-tests -remote http://localhost:2020/sparql
