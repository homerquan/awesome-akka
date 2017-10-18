# Awesome AKKA

Author: Homer Quan (hi@homerquan.com)

## SCALA and AKKA

* How to code in Scala
	* (A quick intro from twitter) https://twitter.github.io/scala_school/basics.html
    * Effective scala: http://twitter.github.io/effectivescala/
	* https://class.coursera.org/progfun-004
	* https://www.coursera.org/curse/reactive
	* (A style guide) http://docs.scala-lang.org/style/
	* (ref) http://www.scala-lang.org/docu/files/ScalaReference.pdf
* Become an expert
    * http://danielwestheide.com/scala/neophytes.html
    * http://www.slideshare.net/shinolajla/effective-akka-scalaio
    * using typesafe console http://resources.typesafe.com/docs/console/manual/getting-started.html
    * https://github.com/alexandru/scala-best-practices
    * Some useful libs for scala: https://github.com/lauris/awesome-scala
* scala projects 
    * github https://github.com/trending?l=scala
    * template http://www.typesafe.com/activator/templates 
    * alternative template: https://github.com/dph01/scala-sbt-template
* Start your first scala project: http://www.johnmurray.io/log/2014/04/15/Starting-a-Scala-Project.html
* Best practices in coding: https://github.com/alexandru/scala-best-practices

## Why Scala

JVM and Java compatibility 
Functional and OO style: productivity
Actor: flexible scale up/down, maintainable, fault tolerance *
Real time: Scala is built for stream, async processing (lambda, future, promise)

## Why AKKA 

https://www.typesafe.com/community/core-projects/akka
http://blog.confluent.io/2015/01/29/making-sense-of-stream-processing/
http://www.typesafe.com/blog/reactive-streams-webinar-qa

### How to code in Akka stream

http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M2/scala/stream-cookbook.html

### Async style programming

Scala and AKKA is non-blocking async language. Please familiar yourself with concepts such as Future and Promise

## Actors

Scala and AKKA provides a concurrency mechanism called “Actor”. It would benefit WISE in scalability and  resilience. 

Actor is an isolated resource unit and communicate with each other via messages. It needs a storage persistence to recover from failure or bootstrap. We select cassandra as storage provider. Sample code: https://github.com/krasserm/akka-persistence-cassandra

Find vehicles by spitial query: build index in memory http://jspatial.sourceforge.net/

Actor is built for share nothing. But sometime it has to use share status: http://stackoverflow.com/questions/7307217/akka-sharing-mutable-state

Common Actor patterns https://doc.akka.io/docs/akka/2.5.4/scala/howto.html

## HA

Akka persistent: http://www.slideshare.net/ktoso/akka-persistence-event-sourcing-in-30-minutes

## Multi tenant

* Each account will has its own actor system

## AKKA streem

* Akka stream cookbook http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M2/scala/stream-cookbook.html
* Stream graph http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M4/scala/stream-graphs.html
* Akka stream custom process stage (writing nodes in CEP network) http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M4/scala/stream-customize.html
* Using actor with stream: http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M4/scala/stream-integrations.html
* http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M5/stream-design.html

### Important cencepts

* Graph: Flow (lines in the graph e.g., f1, f2 … ) + source (in) + sink (out) + junctions (bcast and merge)
* Flow:  A linear processing unit composited by stages e.g., f1:  s1=>s2=>s3
* Stage:  The basic processing unit, which can be 
	* pull
    * push
    * pushpull (for most stream processing)
    * stateful (if change internal status)

### Code samples

* Processing node https://github.com/carlpulley/lift/blob/model/server/exercise/src/main/scala/com/eigengo/lift/exercise/classifiers/workflows/SlidingWindow.scala
* Unit test: https://github.com/carlpulley/lift/blob/model/server/exercise/src/test/scala/com/eigengo/lift/exercise/classifiers/workflows/SlidingWindowTest.scala

### Actors

* Actors for resilliance and scalability http://doc.akka.io/docs/akka/snapshot/scala/persistence.html, http://www.slideshare.net/bantonsson/akka-persistencescaladays2014
* Message dispatcher in AKKA actor system http://doc.akka.io/docs/akka/snapshot/scala/dispatchers.html
* An akka actor example (stock) https://github.com/typesafehub/reactive-stocks#master
* Use actor with sream http://doc.akka.io/docs/akka-stream-and-http-experimental/1.0-M3/scala/stream-integrations.html http://doc.akka.io/api/akka-stream-and-http-experimental/0.7/index.html#akka.stream.actor.ActorPublisher
* http://www.slideshare.net/NLJUG/akka-in-practice-age-mooij-and-raymond-roestenburg
* http://stackoverflow.com/questions/3931994/design-patterns-best-practice-for-building-actor-based-system
* Integration http://doc.akka.io/docs/akka/snapshot/scala/camel.html
* Actor pattern http://letitcrash.com/post/30585282971/discovering-message-flows-in-actor-systems-with
* EPI pattern https://gist.github.com/jboner/8556813
* HA http://danielwestheide.com/blog/2013/03/20/the-neophytes-guide-to-scala-part-15-dealing-with-failure-in-actor-systems.html


### Other

* FSM in AKKA http://doc.akka.io/docs/akka/snapshot/scala/fsm.html
* AKKA CEP with stream http://typesafe.com/activator/template/akka-with-esper#code/src/main/scala/experiments/streams/StreamCEP.scala
* Scala scheduler http://doc.akka.io/docs/akka/2.0/scala/scheduler.html
* Scala agent http://doc.akka.io/docs/akka/2.1.0/scala/agents.html
* A CEP based on spark stream http://spark-summit.org/2014/talk/stratio-streaming-a-new-approach-to-spark-streaming
* http://doc.akka.io/docs/akka/2.0/scala/dataflow.html
* http://www.scala-lang.org/api/2.10.4/index.html#scala.util.continuations.package
* https://github.com/scala/async  
