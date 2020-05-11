# DAIDE - A Brief History

Back around 2002, there had already been a number of projects looking at Diplomacy AIs. Danny Loeb had written a number of scientific 
papers on the subject as part of his post-degree studies, including creating a negotiating language for AIs using a tokenised language 
which contained all the major concepts of Diplomacy negotiation, submitting orders and receiving results. Sean Lorber had also done a 
significant amount of development work on his AI, SeanAI1 (which quickly became known as SeaNail).

However, there was one issue which seemed to be common to all attempts so far - they were getting very little use. This was, to a large 
extent, because the way they tended to be used was that the AI would generate orders. The person running the AI would then put these 
into an email and send them to one of the [Ken Lowe Email Diplomacy Judges](https://en.wikipedia.org/wiki/Internet_Diplomacy#Ken_Lowe_Judge),
and then when the results came back, they would be copied and pasted into the AI so it could generate its next orders.

What I felt was apparent, was that the next step was not to do more development of AIs, but to develop an environment where AIs could 
play each other. Hence [DAIDE](daide.org.uk) - the Diplomacy AI Development Environment - was born.

The concept was simple. At its heart is a TCP/IP server which would run the games. Each AI would then be a TCP/IP client. By using 
TCP/IP, AIs could be developed in any language on any platform (whereas for instance, if the AIs had been DLLs, it would have restricted 
the project to Windows). And in order to allow humans to play against the AIs, a client, the DAIDE Mapper, was created, which simply 
displayed the results on a map, and allowed a human to enter their orders via point and click. It also provided a message-building 
function, which allowed players to click options to build negotiation messages in the tokenised language used by the project.

In order to make development easy, the [negotiating language](http://www.ellought.demon.co.uk/dipai/daide_syntax.pdf) was broken down 
into levels, starting with level 0 (no negotiation) and moving up through the ability to offer peace and an alliance, to actually 
discussing making specific orders, and then on up into the more complex negotiation structures which were available. Hence developers 
did not have to implement the full range of the language in order to be able to get involved.

The early days were spent formalising the communications protocol, and then writing the [Server and Mapper](http://daide.org.uk/news.html#New%20versions%20of%20Server%20and%20Mapper%20released), 
as well as writing a C++ framework that did all the low level comms, storing the current position and latest moves, etc, so that the 
developer could quickly get on with actual AI work.

I wrote the first AI in a couple of days - DumbBot - which just looked at the current position, placed a value on each province, and 
then attacked the most valuable ones. It was surprisingly good for the small amount of effort put into it. But it was no match for 
[Albert](https://sites.google.com/site/diplomacyai/home), which Jason van Hal wrote.

David Norman (10 May, 2020)
