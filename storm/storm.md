# Notes on Storm

## API
Storm has a simple and easy to use API. When programming on Storm, you manipulate and transform streams of tuples, and a tuple is a named list of values. Tuples can contain objects of any type; if you want to use a type Storm doesn't know about it's very easy to register a serializer for that type.

## Components: Spout, Bolt and Topologies
There are just three abstractions in Storm: spouts, bolts, and topologies.

### Spout
A spout is a source of streams in a computation. Typically a spout reads from a queueing broker such as Kestrel, RabbitMQ, or Kafka, but a spout can also generate its own stream or read from somewhere like the Twitter streaming API. Spout implementations already exist for most queueing systems.

### Bolt
A bolt processes any number of input streams and produces any number of new output streams. Most of the logic of a computation goes into bolts, such as functions, filters, streaming joins, streaming aggregations, talking to databases, and so on.

### Topology
A topology is a network of spouts and bolts, with each edge in the network representing a bolt subscribing to the output stream of some other spout or bolt. A topology is an arbitrarily complex multi-stage stream computation. Topologies run indefinitely when deployed.

## Local mode
Storm has a "local mode" where a Storm cluster is simulated in-process. This is useful for development and testing. The "storm" command line client is used when ready to submit a topology for execution on an actual cluster.


## References:
* http://storm.apache.org/about/simple-api.html
* http://storm.apache.org/documentation/Home.html
* http://storm.apache.org/documentation/Tutorial.html
* http://storm.apache.org/about/multi-language.html
