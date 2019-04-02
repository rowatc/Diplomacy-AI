# Diplomacy-AI
We're building an AI to play the board game Diplomacy!

## tl;dr

[Diplomacy](https://en.wikipedia.org/wiki/Diplomacy_(game))'s a fun game invented by [Allan Calhamer](https://en.wikipedia.org/wiki/Allan_B._Calhamer); there's an [annual competition for bots](http://mmi.tudelft.nl/negotiation/tournament); using RL to play the 'gunboat' variant should be relatively easy, but involves coalitions; full Diplomacy also involves natural language processing, so will be a real challenge.

## Basics

For more details about Diplomacy and bots playing it, see [these slides](http://wrongdoing.org/181004_Diplomacy_AI.pdf), based on [this lightning talk](https://youtu.be/Ojpn3UXZuGM?t=1033) at [Bornhack](https://bornhack.dk) 2018.

We intend to develop this project via the [London Reinforcement Learning](https://www.meetup.com/London-Reinforcement-Learning/) Meetup.

## Goals

1. an **AI that systematically out-performs [D-Brane](https://link.springer.com/article/10.1007/s10489-017-0919-y) in Gunboat Diplomacy** (without negotiation).
1. a **winning entry in the annual Automated Negotiating Agents' Competition (ANAC) Diplomacy League**.  Entrants submit negotiating agents that play by being coupled to [D-Brane](https://link.springer.com/article/10.1007/s10489-017-0919-y), which picks moves.  See the [2019 call for participation](http://www.iiia.csic.es/~davedejonge/bandana/files/call_for_participation_2019.pdf) (deadline 20 May); negotiations use the [BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana), which has well-defined semantics.
1. an **article in an internationally recognised AI journal** describing our work.  (The ANAC competition has been held as part of the [IJCAI](https://www.ijcai.org), International Joint Conferences on Artificial Intelligence.)
1. **beat human players** in online Diplomacy fora such as [PlayDiplomacy](https://www.playdiplomacy.com/) or [Backstabbr](https://www.backstabbr.com).  Initially, Gunboat Diplomacy, then full Diplomacy online and, finally, full Diplomacy face-to-face (e.g. at [WorldDipCon](https://en.wikipedia.org/wiki/Diplomacy_(game)#Major_championship_tournaments)).

## Key resources

### de Jonge, Baarslag, Aydo&#287;an, Jonker, Fujita and Ito (2018), "[The Challenge of Negotiation in the Game of Diplomacy](http://www.iiia.csic.es/~davedejonge/homepage/files/articles/The%20Challenge%20of%20Negotiation%20in%20Diplomacy.pdf)", The 6th International Conference on Agreement Technologies 2018, Bergen, Norway.

The best introduction to negotiating agents in Diplomacy.  This article contains a brief overview of Diplomacy, the BANDANA environment, leading entries in 2017, 2018 ANAC Diplomacy Challenges and the challenges facing negotiating agents.  None of the entries so far seem to engage in learning, much less reinforcement learning.

> none of the negotiation algorithms ... have been able to significantly improve the performance over a non-negotiating baseline agent

> Now that modern Chess and Go computers are already far superior to any human player [[15](https://www.nature.com/articles/nature16961)], we expect that Diplomacy will start to draw more attention as the next big challenge for computer science.

> we are not expecting the Diplomacy Challenge to have a winner any time soon. We regard it as a long term challenge which might take several years to tackle.

### [The BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana)

A Java framework for developing automated agents to play Diplomacy.  It calls [Parlance](https://pypi.org/project/Parlance).

[Downloads](http://www.iiia.csic.es/~davedejonge/bandana/download.php) include:
* [March 2018 manual](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%201.3%20Manual.pdf): download this first and follow the installation instructions for the BANDANA Jave framework and Parlance game server;
* the accompanying [Java framework](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%20Framework%201.3.1.zip);
* [2018 ANAC agents](http://www.iiia.csic.es/~davedejonge/bandana/files/Agents%20submitted%20to%20the%20ANAC%202018%20Diplomacy%20Challenge.zip).

The scoring system (12 points for a solo victory, etc.) is drawn from [PlayDiplomacy's](https://www.playdiplomacy.com/forum/viewtopic.php?f=7&t=30974).

### [The Rules of Diplomacy](http://www.wizards.com/avalonhill/rules/diplomacy_rulebook.pdf) (Avalon Hill)

2008, 5th edition.  Here is the [2000 4th edition](http://www.wizards.com/avalonhill/rules/diplomacy.pdf).  See the [DATC](http://web.inter.nl.net/users/L.B.Kruijswijk/#3) for a list of previous editions.

## Other resources

### [Parlance](https://pypi.org/project/Parlance/)

A Python framework for playing the Diplomacy board game over a network.  [BANDANA](http://www.iiia.csic.es/~davedejonge/bandana) calls it.  Successor to [DAIDE](https://daide.org.uk).

### de Jonge and Sierra (2017), "[D-Brane: a diplomacy playing agent for automated negotiations research](https://link.springer.com/article/10.1007/s10489-017-0919-y)", Applied Intelligence

Detailed description of the D-Brane (Diplomacy BRAnch & bound NEgotiator) modules, which seek to myopically maximise the Supply Centres gained in the current round using And/Or tree search with Branch & Bound.

> the success of a negotiating agent may sometimes depend more on the accuracy and efficiency in which it calculates utility values than on the bargaining strategy it applies

### Shapiro, Fuchs and Levinson (2002), "[Learning a Game Strategy Using Pattern-Weights and Self-Play](https://link.springer.com/chapter/10.1007/978-3-540-40031-8_4)", Third International Conference on Computers and Games, Edmonton, Canada.

Trained a TD RL system on an existing knowledge base.  In contrast to the ANAC project, this system plays 'gunboat' Diplomacy, moving without negotiations.  &#0167;2 describes the game graph and action space.

### [World Diplomacy Database](world-diplomacy-database.com)

Includes:
1. [tournaments](http://world-diplomacy-database.com/php/results/tournament_list.php);
1. player [rankings](http://world-diplomacy-database.com/php/ranking/index.php) under a number of systems;
1. different [scoring systems](http://world-diplomacy-database.com/php/scoring/scoring.php).

### online Diplomacy games

Some online fora for playing Diplomacy are:

#### [PlayDiplomacy](https://www.playdiplomacy.com/)

Top 25 players are displayed [here](https://www.playdiplomacy.com/stats.php?sub_page=1).  Like Elo ratings, [PlayDiplomacy rankings](https://www.playdiplomacy.com/stats.php?sub_page=3) reflect the strength of the opposition that players have overcome.  The exact formula is deliberately secret to prevent "[play[ing] the system rather than the game](https://www.playdiplomacy.com/forum/viewtopic.php?f=129&t=34913#p602092)", but seems to assign 12 points for a solo victory, and decreasing weight to older games (a system called '[fading echoes](https://www.playdiplomacy.com/forum/viewtopic.php?f=7&t=30974)').

A basic order adjudication tool is available [here](https://www.playdiplomacy.com/judge/new_manual.php).  Their online discussion forum is [here](https://www.playdiplomacy.com/forum/).

#### [The DPjudge](http://uk.diplom.org/)

A deceptively unimpressive website disguising serious games and content, including [The Diplomatic Pouch 'zine](http://uk.diplom.org/pouch/Zine), dating back to 1995.  Their order adjudication algorithm is described [here](http://uk.diplom.org/?page=Algorithm). They provided messages for analysis by [Niculae et al. (2015)](http://vene.ro/betrayal).

#### [webDiplomacy](https://webdiplomacy.net/)

A GitHub project.

#### [Backstabbr](https://www.backstabbr.com)

Backstabbr's order adjudication [claims to be compliant](https://www.backstabbr.com/faq) with [DATC](http://web.inter.nl.net/users/L.B.Kruijswijk/).  It is supported by a [Discord server](https://discordapp.com/invite/4CVbMjh).

### books

#### Sharp (1978), "[The game of Diplomacy](https://books.google.co.uk/books?isbn=0213166763)"

Written with dated verve, this book colourfully introduces Diplomacy theory, including opening and endgame theory informed by basic statistics.  Available online [here](http://www.diplomacy-archive.com/god.htm).

> consider one of the most important facts about the game of Diplomacy: each player is outnumbered six to one

> I had pulled off a particularly vicious stab (not even a very good one, as it turned out) on an ally who had served me faithfully for five game years. I waited, cringing, for the next development; and there in the next post was a letter with the familiar postmark. I opened it apprehensively.
> 'Dear Richard,' it began. 'Ouch! That hurt. It looks as if I shall be playing a rather minor role in our partnership from now on. ...' And it went on to discuss some tactical possibilities for the coming season. Now, this letter had two effects: first, it made me feel like a louse; second, it induced me to let him off the hook, because I knew that in the last resort I would rather get a letter from him than from any of the other potential allies in that area. That is the way to treat a stab.

> I once induced England to play it as part of an elaborate long-term bargain: England was never to occupy the North Sea, in exchange for which Germany undertook to build no fleets at all.

#### Kostick (2015), "[The Art of Correspondence in the Game of Diplomacy](https://books.google.co.uk/books?isbn=0993415105)"

A book about negotiation in (human) Diplomacy by [Conor Kostick](https://en.wikipedia.org/wiki/Conor_Kostick), historian, novelist, game designer and international Diplomacy champion.

### online communities

* a [subreddit](https://www.reddit.com/r/diplomacy); 
* a [Discord server](https://discordapp.com/invite/TEsAsyM);
* rec.games.diplomacy newsgroup (or via [Google Groups](https://groups.google.com/forum/#!forum/rec.games.diplomacy))

### [Diplomacy Adjudicator Test Cases](http://web.inter.nl.net/users/L.B.Kruijswijk/) (DATC)

Detailed discussion of algorithmic order adjudication based primarily on the 2000 Diplomacy rules.  Last updated in 2009.

### [Diplomacy AI Development Environment](http://daide.org.uk) (DAIDE)

A UK-based Diplomacy AI community project begun in 2002, which is now moribund.  There seems to have been no significant new material added to the website since 2013.

### Masters' theses

#### Webb, Chin, Wilkins, Payce, Dedoyard (2008), "[Automated Negotiation in the Game of Diplomacy](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.466.6361&rep=rep1&type=pdf)"

Project report of Imperial College MEng students, supervised by Iain Phillips.  On AI/ML:

> Machine Learning Currently most bots learn very little during the course of play. If a bot can be designed that interprets and learns from the actions of its opponents a better bot may be created.

#### Huff, Chan, Tondelier, Bundred, Egan (2005), "[Automated Negotiation in the Game of Diplomacy](https://www.tofgarion.net/lectures/XX201/diplomacy/reportHuff.pdf)"

Project report of Imperial College MEng students, again supervised by Iain Phillips.  &#0167;2 reviews existing Diplomacy bots.  No AI/ML used.

#### Ritchie (2003), "[Diplomacy — A.I.](http://daide.org.uk/external/ritchie200309.pdf)"

University of Glasgow MSc thesis supervised by Ron Poet.  Chapter 3 discusses theories of Diplomacy play.

### Niculae, Kumar, Boyd-Graber, Danescu-Niculescu-Mizil (2015), "[Linguistic Harbingers of Betrayal: A Case Study on an Online Strategy Game](https://www.aclweb.org/anthology/P15-1159)", Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing, pages 1650–1659, Beijing, China

Collected 145,000 dyadic messages from 249 games (JSON format) played on [The DPjudge](http://uk.diplom.org) and another online forum.  The messages were then analysed using tools such as Stanford's [Sentiment Analyzer](https://nlp.stanford.edu/sentiment) and [politeness classifiers](https://nlp.stanford.edu/pubs/politeness.pdf).

> half of the games have over 515 messages exchanged between the players, while the top quartile has over 750 messages per game. Also, non-trivial messages (with at least one sentence) tend to be complex: over half of them have at least five sentences, and the top quartile consists of messages with eight or more sentences.

> The resulting model achieves a cross-validation accuracy of 57% and a Matthews correlation coefficient of 0.14, significantly above chance ... This indicates that, unlike the actual players, the classifier is able to exploit subtle linguistic signals that surface in the conversation.

![alt text](http://vene.ro/betrayal/time.png "The dynamics of betrayal")

The authors' page [here](http://vene.ro/betrayal/) summarises their findings and presents their anonymised data, and video and slides from their ACL 2015 talk.  Also mentioned by security expert [Bruce Schneier's blogpost](https://www.schneier.com/blog/archives/2015/08/detecting_betra.html).

### podcasts!?

Yup, a [This American Life podcast](https://www.thisamericanlife.org/531/got-your-back/act-one) emphasising the importance of the strategies beyond the board:

> "And the way he said it to me made me feel like it wasn't a manipulation." (Ambassador [Dennis Ross](https://en.wikipedia.org/wiki/Dennis_Ross))

> "I want to tell you how much ... I was impressed by this" (Ambassador [Dennis Ross](https://en.wikipedia.org/wiki/Dennis_Ross))

The podcast covers some of the material in David Hill's "[The Board Game of the Alpha Nerds](http://grantland.com/features/diplomacy-the-board-game-of-the-alpha-nerds/)":

> If you’ve ever heard of Diplomacy, chances are you know it as “the game that ruins friendships.”

> Edi took out scissors and a pen from a drawer and set to work on the letter, painstakingly doctoring it. When he was finished he held up the letter proudly and read it to himself. *I am against a three-way draw and I will take three more supply centers …* He put the forgery in the mail to the third player. Then he waited.

> “What I love about the game is that no one can really play the game ‘right,’” Birsan said. “Otherwise, after 50 years, that would have been discovered long ago and the hobby would have died of boredom.”

Would you believe, a whole[ Diplomacy Games podcast series](http://diplomacygames.com/)?

### [Diplicity](https://play.google.com/store/apps/details?id=se.oort.diplicity)

Android app implementing a non-copyrighted variant of Diplomacy; the "spiritual successor" to Droidippy.

