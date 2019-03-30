# Diplomacy-AI
We're building an AI to play the board game Diplomacy!

## tl;dr

[Diplomacy](https://en.wikipedia.org/wiki/Diplomacy_(game))'s a fun game; there's an [annual competition for bots](http://mmi.tudelft.nl/negotiation/tournament); using RL to play the 'gunboat' variant should be relatively easy, but involves coalitions; full Diplomacy also involves natural language processing, so will be a real challenge.

## Introduction

For more details about Diplomacy and bots playing it, see [these slides](http://wrongdoing.org/181004_Diplomacy_AI.pdf), based on [this lightning talk](https://youtu.be/Ojpn3UXZuGM?t=1033) at [Bornhack](https://bornhack.dk) 2018.

## Goals

1. a **winning entry in the annual Automated Negotiating Agents' Competition (ANAC) Diplomacy League**.  Entrants submit negotiating agents that play by being paired to the [D-Brane](https://link.springer.com/article/10.1007/s10489-017-0919-y) module, which picks moves.  See hhe [2019 call for participation](http://www.iiia.csic.es/~davedejonge/bandana/files/call_for_participation_2019.pdf) (deadline 20 May); negotiations use the [BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana), which has well-defined semantics.
1. an **article in an internationally recognised AI journal** describing our work.  (The ANAC competition has been held as part of the [ICJAI](https://www.ijcai.org), International Joint Conferences on Artificial Intelligence.)
1. **beat human players** in online Diplomacy fora such as [PlayDiplomacy](https://www.playdiplomacy.com/) or [Backstabbr](https://www.backstabbr.com).

## Key resources

### de Jonge, Baarslag, Aydo&#287;an, Jonker, Fujita and Ito (2018), "[The Challenge of Negotiation in the Game of Diplomacy](http://www.iiia.csic.es/~davedejonge/homepage/files/articles/The%20Challenge%20of%20Negotiation%20in%20Diplomacy.pdf)", The 6th International Conference on Agreement Technologies 2018, Bergen, Norway.

The best introduction to negotiating agents in Diplomacy.  This article contains a brief overview of Diplomacy, the BANDANA environment, leading entries in 2017, 2018 ANAC Diplomacy Challenges and the challenges facing negotiating agents.  None of the entries so far seem to engage in learning, much less reinforcement learning.

> none of the negotiation algorithms ... have been able to significantly improve the performance over a non-negotiating baseline agent

> Now that modern Chess and Go computers are already far superior to any human player [15](https://www.nature.com/articles/nature16961), we expect that Diplomacy will start to draw more attention as the next big challenge for computer science.

> we are not expecting the Diplomacy Challenge to have a winner any time soon. We regard it as a long term challenge which might take several years to tackle.

### [The BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana)

[Downloads](http://www.iiia.csic.es/~davedejonge/bandana/download.php) include:
* [March 2018 manual](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%201.3%20Manual.pdf);
* the accompanying [Java framework](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%20Framework%201.3.1.zip);
* [2018 ANAC agents](http://www.iiia.csic.es/~davedejonge/bandana/files/Agents%20submitted%20to%20the%20ANAC%202018%20Diplomacy%20Challenge.zip).

### de Jonge and Sierra (2017), "[D-Brane: a diplomacy playing agent for automated negotiations research](https://link.springer.com/article/10.1007/s10489-017-0919-y)", Applied Intelligence

Detailed description of the D-Brane (Diplomacy BRAnch & bound NEgotiator) modules, which seek to myopically maximise the Supply Centres gained in the current round using And/Or tree search with Branch & Bound.

> the success of a negotiating agent may sometimes depend more on the accuracy and efficiency in which it calculates utility values than on the bargaining strategy it applies

### [The Rules of Diplomacy](https://www.wizards.com/avalonhill/rules/diplomacy_rulebook.pdf) (Avalon Hill)

## Other resources

### Shapiro, Fuchs and Levinson (2002), "[Learning a Game Strategy Using Pattern-Weights and Self-Play](https://link.springer.com/chapter/10.1007/978-3-540-40031-8_4)", Third International Conference on Computers and Games, Edmonton, Canada.

Trained a TD RL system on an existing knowledge base.  In contrast to the ANAC project, this system plays 'gunboat' Diplomacy, moving without negotiations.  &#0167;2 describes the game graph and action space.

### [Diplomacy AI Development Environment](http://daide.org.uk) (DAIDE)

A Diplomacy AI community project begun in 2002, which is now somewhat moribund.  There seems to have been no significant new material added to the website since 2013.

### Webb, Chin, Wilkins, Payce, Dedoyard (2008), "[Automated Negotiation in the Game of Diplomacy](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.466.6361&rep=rep1&type=pdf)"

Project report of Imperial College MEng students, supervised by Iain Phillips.  On AI/ML:

> Machine Learning Currently most bots learn very little during the course of play. If a bot can be designed that interprets and learns from the actions of its opponents a better bot may be created.

### Huff, Chan, Tondelier, Bundred, Egan (2005), "[Automated Negotiation in the Game of Diplomacy](https://www.tofgarion.net/lectures/XX201/diplomacy/reportHuff.pdf)"

Project report of Imperial College MEng students, again supervised by Iain Phillips.  &#0167;2 reviews existing Diplomacy bots.  No AI/ML used.

### Ritchie (2003), "[Diplomacy — A.I.](http://daide.org.uk/external/ritchie200309.pdf)"

University of Glasgow MSc thesis supervised by Ron Poet.  Chapter 3 discusses theories of Diplomacy play.

### Kostick (2015), "[The Art of Correspondence in the Game of Diplomacy](https://books.google.co.uk/books?isbn=0993415105)"

A discussion of Diplomacy negotiations, for humans.
