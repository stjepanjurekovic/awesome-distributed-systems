# awesome-distributed-systems

A (hopefully) curated list on awesome material on distributed systems, inspired by
other awesome frameworks like [awesome-python](https://github.com/vinta/awesome-python).
Most links will tend to be readings on architecture itself rather than code itself.

## Bootcamp
Read things here before you start.
- [CAP Theorem](http://en.wikipedia.org/wiki/CAP_theorem), Also [plain english](http://ksat.me/a-plain-english-introduction-to-cap-theorem) explanation
- [Fallacies of Distributed Computing](http://en.wikipedia.org/wiki/Fallacies_of_distributed_computing), expect things to break, *everything*
- [Distributed systems theory for the distributed engineer](http://the-paper-trail.org/blog/distributed-systems-theory-for-the-distributed-systems-engineer/), most of the papers/books in the blog might reappear in this list again. Still a good BFS approach to distributed systems.
- [FLP Impossibility Result (paper)](https://groups.csail.mit.edu/tds/papers/Lynch/jacm85.pdf), an easier [blog post](http://the-paper-trail.org/blog/a-brief-tour-of-flp-impossibility/) to follow along
- [An Introduction to Distributed Systems](https://github.com/aphyr/distsys-class) @aphyr's excellent introduction to distributed systems

## Books
- [Distributed Systems for fun and profit](http://book.mixu.net/distsys/single-page.html) [Free]
- [Distributed Systems Principles and Paradigms, Andrew Tanenbaum](https://www.distributed-systems.net/index.php/books/ds3/) [Free with registration]
- [Scalable Web Architecture and Distributed Systems](http://www.aosabook.org/en/distsys.html) [Free]
- [Principles of Distributed Systems](http://dcg.ethz.ch/lectures/podc_allstars/lecture/podc.pdf) [Free] [ETH Zurich University]
- [Making reliable distributed systems in the presence of software errors](http://www.erlang.org/download/armstrong_thesis_2003.pdf), [Free] Joe Amstrong's (Author of Erlang) PhD thesis
- [Designing Data Intensive Applications](https://www.amazon.com/Designing-Data-Intensive-Applications-Reliable-Maintainable/dp/1449373321) [Amazon Link]
- [Distributed Machine Learning Patterns, Yuan Tang](https://github.com/terrytangyuan/distributed-ml-patterns), Practical patterns for scaling machine learning from your laptop to a distributed cluster
- [Distributed Computing, Hagit Attiya and Jennifer Welch](http://hagit.net.technion.ac.il/publications/dc/)
- [Distributed Algorithms, Nancy Lynch](https://www.amazon.com/Distributed-Algorithms-Kaufmann-Management-Systems/dp/1558603484) [Amazon Link]
- [Impossibility Results for Distributed Computing](http://www.morganclaypool.com/doi/abs/10.2200/S00551ED1V01Y201311DCT012) [paywall]
- [Designing Distributed Systems, Brendan Burns](https://azure.microsoft.com/en-us/resources/designing-distributed-systems/) [Free with registration]
- [Distributed Systems: Concepts and Design, George Coulouris](https://www.amazon.com/Distributed-Systems-Concepts-Design-5th/dp/0132143011) [Amazon Link]
- [Akka in Action, Second Edition](https://www.manning.com/books/akka-in-action-second-edition) 
- [Systemantics: how systems work and especially how they fail](https://openlibrary.org/books/OL4904457M/Systemantics)

## Papers
Must read papers on distributed systems. While nearly *all* of Lamport's work should feature here, just adding a few that *must* be read.
- [Times, Clocks and Ordering of Events in Distributed Systems](http://research.microsoft.com/en-us/um/people/lamport/pubs/time-clocks.pdf) Lamport's paper, the Quintessential distributed systems primer
- [Session Guarantees for Weakly Consistent Replicated Data](http://www.cs.utexas.edu/~dahlin/Classes/GradOS/papers/SessionGuaranteesPDIS.pdf) a '94 paper that talks about various recommendations for session guarantees for eventually consistent systems, many of this would be standard vocabulary in reading other dist. sys papers, like monotonic reads, read your writes etc.

### Storage & Databases
- [Dynamo: Amazon's Highly Available Key Value Store](http://bnrg.eecs.berkeley.edu/~randy/Courses/CS294.F07/Dynamo.pdf)
Paraphrasing @fogus from their [blog](http://blog.fogus.me/2011/09/08/10-technical-papers-every-programmer-should-read-at-least-twice/), it is very rare for a paper describing an active production system to influence the state of active research in any industry; this is one of those seminal distributed systems paper that solves the problem of a highly available and fault tolerant database in an elegant way, later paving the way for systems like Cassandra, and many other AP systems using a consistent hashing.
- [Bigtable: A Distributed Storage System for Structured Data](http://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf)
- [The Google File System](http://static.googleusercontent.com/external_content/untrusted_dlcp/research.google.com/en/us/archive/gfs-sosp2003.pdf)
- [Cassandra: A Decentralized Structured Storage System](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.161.6751&rep=rep1&type=pdf) Inspired heavily by Dynamo, an now an open source
- [CRUSH: Controlled, Scalable, Decentralized Placement of Replicated Data](http://www.ssrc.ucsc.edu/Papers/weil-sc06.pdf), the algorithm for the basis of Ceph distributed storage system, for the architecture itself read [RADOS](http://ceph.com/papers/weil-rados-pdsw07.pdf)

### Messaging systems
- [The Log: What every software engineer should know about real-time data's unifying abstraction](http://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying), a somewhat long read, but covers brilliantly on logs, which are at the heart of most distributed systems
- [Kafka: a Distributed Messaging System for Log Processing](http://notes.stephenholiday.com/Kafka.pdf)

### Distributed Consensus and Fault-Tolerance
- [Practical Byzantine Fault Tolerance](http://pmg.csail.mit.edu/papers/osdi99.pdf)
- [The Byzantine Generals Problem](http://bnrg.cs.berkeley.edu/~adj/cs16x/hand-outs/Original_Byzantine.pdf)
- [Impossibility of Distributed Consensus with One Faulty Process](http://macs.citadel.edu/rudolphg/csci604/ImpossibilityofConsensus.pdf)
- [The Part Time Parliament](http://research.microsoft.com/en-us/um/people/lamport/pubs/lamport-paxos.pdf) Paxos, Lamport's original Paxos paper, a bit difficult to understand, may require multiple passes
- [Paxos Made Simple](http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf), a more terse readable Paxos paper by Lamport himself. Shorter and more easier compared to the original.
- [The Chubby Lock Service for loosely coupled distributed systems](http://static.googleusercontent.com/media/research.google.com/en//archive/chubby-osdi06.pdf) Google's lock service used for loosely coupled distributed systems. Sort of Paxos as a Service for building other distributed systems. Primary inspiration behind other Service Discovery & Coordination tools like Zookeeper, etcd, Consul etc.
- [Paxos made live - An engineering perspective](http://research.google.com/archive/paxos_made_live.html) Google's learning while implementing systems atop of Paxos. Demonstrates various practical issues encountered while implementing a theoretical concept.
- [Raft Consensus Algorithm](https://raftconsensus.github.io/) An alternative to Paxos for distributed consensus, that is much simpler to understand. Do checkout an [interesting visualization of raft](http://thesecretlivesofdata.com/raft/)
- [Conflict-free Replicated Data Types](https://pages.lip6.fr/Marc.Shapiro/papers/RR-7687.pdf) presents an approach for Strong Eventual Consistency which as been applied in projects such as [Riak](http://basho.com/products/riak-kv/), [Redis](https://redis.io/) and [Akka](https://akka.io/). A great talk on the subject by Martin Kleppmann can be found [here](https://www.youtube.com/watch?v=B5NULPSiOGw)

### Testing, monitoring and tracing
While designing distributed systems are hard enough, testing them is even harder.
- [Dapper](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/36356.pdf), Google's large scale distributed-systems tracing infrastructure, this was also the basis for the design of open source projects such as [Zipkin](http://zipkin.io/), [Apache SkyWalking](https://github.com/apache/incubator-skywalking), [Pinpoint](https://github.com/naver/pinpoint) and [HTrace](http://htrace.incubator.apache.org/).

### Programming Models
- [Distributed Programming Model](http://web.cs.ucdavis.edu/~pandey/Research/Papers/icdcs01.pdf)
- [PSync: a partially synchronous language for fault-tolerant distributed algorithms](http://www.di.ens.fr/~cezarad/popl16.pdf) Video: [Conference Video](https://www.youtube.com/watch?v=jxfq9_L9T1U&t=51s)
- [Programming Models for Distributed Computing](http://heather.miller.am/teaching/cs7680/)
- [Logic and Lattices for Distributed Programming](http://db.cs.berkeley.edu/papers/UCB-lattice-tr.pdf)

### Verification of Distributed Systems
- Curated list of resources on [testing distributed systems](https://asatarin.github.io/testing-distributed-systems/) includes links to materials on testing by various companies (Google, Amazon, Netflix, Microsoft, Dropbox, etc) and research papers.
- [Jepsen](https://github.com/jepsen-io/jepsen) A framework for distributed systems verification, with fault injection
  @aphyr has featured enough times in this list already, but Jepsen and the blog posts that go with are a quintessntial addition to any distributed systems reading list.
- [Verdi](http://verdi.uwplse.org/) A Framework for Implementing and Formally Verifying Distributed Systems [Paper](http://verdi.uwplse.org/verdi.pdf)

## Videos
- [Distributed Deep Dive](https://www.ably.io/blog/introducing-distributed-deep-dive-interview-series-by-ably-realtime/) interview series by [Ably Relatime](https://ably.io).
- [Distributed Systems in One Lesson](https://www.youtube.com/watch?v=Y6Ev8GIlbxc&t=17s) Distributed Systems in One Lesson by Tim Berglund

## Courses
- [Reliable Distributed Algorithms, Part 1](https://learning.edx.org/course/course-v1:KTHx+ID2203.1x+3T_2017), KTH Sweden
- [Reliable Distributed Algorithms, Part 2](https://learning.edx.org/course/course-v1:KTHx+ID2203.2x+2016T4), KTH Sweden
- [Cloud Computing Concepts](https://class.coursera.org/cloudcomputing-001), University of Illinois
- [CMU: Distributed Systems](http://www.cs.cmu.edu/~dga/15-440/F12/syllabus.html) in Go Programming Language
- [Software Defined Networking](https://www.coursera.org/course/sdn) , Georgia Tech.
- [ETH Zurich: Distributed Systems](http://dcg.ethz.ch/lectures/podc_allstars/)
- [ETH Zurich: Distributed Systems Part 2](http://dcg.ethz.ch/lectures/distsys), covers  Distributed control algorithms, communication models, fault-tolerance among other things. In particular fault tolerance issues (models, consensus, agreement) and replication issues (2PC,3PC, Paxos), which are critical in understanding distributed systems are explained in great detail.
- [Distributed Systems Course](http://www.distributedsystemscourse.com/), A beginner course on distributed system by Chris Colohan, A google employee who contributed to  SUIF, MapReduce, TCMalloc, Percolator, Caffeine, Borg, Omega, and Piper.
- [MIT 6.824](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-824-distributed-computer-systems-engineering-spring-2006/), [Youtube-playlist](https://www.youtube.com/playlist?list=PLrw6a1wE39_tb2fErI4-WkMbsvGQk9_UB) MIT distributed system lectures, in each video they discuss papers like GFS, Zookeeper, RAFT, Spanner...
- [Distributed Systems](https://www.cl.cam.ac.uk/teaching/2021/ConcDisSys/), Lectures 9 to 16 of the Cambridge University lecture "Concurrent and Distributed Systems", given by Dr. Martin Kleppmann. [Youtube-playlist](https://www.youtube.com/playlist?list=PLeKd45zvjcDFUEv_ohr_HdUFe97RItdiB). A computer science entrance course, covered basic models and algorithms in distributed systems, also discussed CRDT, collaboration software and google's spanner.


## Blogs and other reading links
- [Amazon Builder's Library](https://aws.amazon.com/builders-library/), a collection of Amazon's learnings on distributed systems
- [How we implemented consistent hashing efficiently](https://blog.ably.io/how-to-implement-consistent-hashing-efficiently-fe038d59fff2)
- [Notes on Distributed Systems for Young Bloods](http://www.somethingsimilar.com/2013/01/14/notes-on-distributed-systems-for-young-bloods/)
- [High Scalability](http://highscalability.com/) Several architectures of huge internet services, for eg [twitter](http://highscalability.com/blog/2013/7/8/the-architecture-twitter-uses-to-deal-with-150m-active-users.html), [whatsapp](http://highscalability.com/blog/2014/2/26/the-whatsapp-architecture-facebook-bought-for-19-billion.html)
- [There is No Now](http://queue.acm.org/detail.cfm?id=2745385), Problems with simultaneity in distributed systems
- [Turing Lecture: The Computer Science of Concurrency: The Early Years](http://cacm.acm.org/magazines/2015/6/187316-turing-lecture-the-computer-science-of-concurrency/fulltext), An article by Leslie Lamport on concurrency
- [The Paper Trail](http://the-paper-trail.org/blog/tag/distributed-systems/) blog, a very readable blog covering various aspects of distributed systems
- [aphyr](https://aphyr.com/tags/Distributed-Systems), Posts on [jepsen](https://github.com/aphyr/jepsen) series are pretty awesome
- [All Things Distributed](http://www.allthingsdistributed.com/) - Wernel Vogel's (Amazon CTO) blog on distributed systems
- [Distributed Systems: Take Responsibility for Failover](http://ivolo.me/distributed-systems-take-responsibility-for-failover/)
- [The C10K problem](http://www.kegel.com/c10k.html)
- [On Designing and Deploying Internet-Scale Services](http://static.usenix.org/event/lisa07/tech/full_papers/hamilton/hamilton_html/)
- [Files are hard](http://danluu.com/file-consistency/) A blog post on filesystem consistency, pretty important to read if you are into distributed storage or databases.
- [Distributed Systems Testing: The Lost World](http://tagide.com/blog/research/distributed-systems-testing-the-lost-world/) Testing distributed systems are hard enough, a well researched blog post which again covers a lot of links to various approaches and other papers
- [SWIM Protocol explained](https://asafdav2.github.io/2017/swim-protocol/) A blog post on popular SWIM failure detector


## Research
- [ACM Symposium on Principles of Distributed Computing (PODC) and International Symposium on Distributed Computing (DISC)](https://podc-disc.github.io/), a list of resources from PODC–DISC community including conference series, mailing lists, youtube, twitter, etc.
- [IEEE International Parallel & Distributed Processing Symposium (IPDPS)](http://www.ipdps.org/), an international forum for engineers and scientists to present their latest research findings.
- [Springer Distributed Computing Journal](https://www.springer.com/journal/446), a journal about theory, design, specification, and implementation of distributed systems.


## Meta Lists
Other lists like this one
- [Readings in distributed systems](http://christophermeiklejohn.com/distributed/systems/2013/07/12/readings-in-distributed-systems.html)
- [Distributed Systems meta list](https://gist.github.com/macintux/6227368)
- [List of required readings for Distributed Systems](http://www.andrew.cmu.edu/course/15-749/READINGS/required/) Part of CMU's Engineering Distributed Systems course
- [The Distributed Reader](http://reiddraper.github.io/distreader/)
- [A Distributed Systems Reading List](https://dancres.github.io/Pages/), A collection of material, mostly papers on Distributed Systems Theory as well as seminal industry papers
- [Distributed Systems Readings](https://henryr.github.io/distributed-systems-readings/), A comprehensive list of online courses related to distributed systems
- [Awesome Distributed Consensus](https://github.com/dgryski/awesome-consensus), Another list of materials on distributed consensus protocols
- [Beginner's Guide to Distributed Systems](https://techbelle.medium.com/one-beginners-guide-to-learning-about-distributed-systems-7c8528c2fcaf) A blog post with some useful getting started links for distributed systems
