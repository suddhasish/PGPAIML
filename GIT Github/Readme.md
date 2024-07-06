LVCS --> Local Version control system
CVCS

CVS (Concurrent Version System) --> Opensource --> founded in 1986

SVN (Apache Subversion) --> Opensource --> founded in 1990


DVCS (Distributed version control system) --> Git / mercurilal / perforce / Bitkeeper




To summarise what you saw in the video, there are three main types of version control systems:

Local Version Control System

Centralised Version Control System

Distributed Version Control System

The Local Version control system maintains the database of different versions in the local computer. The problem with using the local version control system is that it is difficult to collaborate and disaster recovery after your local machine crashes is impossible.


To fix these problems, thus, the Central Version control system (CVCS) came into existence.

In CVCS, all the versions of a file were saved in a central server that enables collaboration.

It also eliminates the problems associated with local system crashes, as the probability of central server crashing is less than the probability of local system crashing. 
However, as you can see in the following diagram, the developer needs to interact with the central server every time they need to save a version of the code. Further, there is a possibility of central server failure too.


Then, the Distributed Version control system (DVCS) came to the rescue by fixing all such problems. As shown in the following diagram, the entire database of different versions is present on the local machines of developers as well as the central server. Even if the central server crashes, this database is available on all the local machines as well. You might be thinking that this is a huge waste of storage. However, as the code files are text files, they take up minimal space.



GitHub, Gitlab, BitBucket

USAZUITS50859

Agent.Name