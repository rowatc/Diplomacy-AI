# Diplomacy-AI
We're building an AI to play the board game Diplomacy!

## tl;dr

[Diplomacy](https://en.wikipedia.org/wiki/Diplomacy_(game)) embeds simple board play in a framework of rich, unstructured negotiations; using reinforcement learning to play the 'gunboat' variant (without negotiations) should be relatively easy, but involves coalitions; the natural language processing of full Diplomacy will be a real challenge.

## Basics

For more details about Diplomacy and bots playing it, see [these slides](200513_Diplomacy_AI.pdf), based on [this lightning talk](https://youtu.be/Ojpn3UXZuGM?t=1033) at [Bornhack](https://bornhack.dk) 2018.

We intend to develop this project via the [Diplomacy AI](https://www.meetup.com/Diplomacy-AI-Meetup-Group/) Meetup.  Please join us - either in person - or on Slack by e-mailing [Colin Rowat](href=mailto:c.rowat@espero.org.uk).

## Goals

1. near term: an **AI that systematically out-performs state-of-the-art bots (e.g. Albert, D-Brane, KestasBot) in Gunboat Diplomacy** (without negotiation).
<!-- 1. 2020 or later: a **winning entry in the annual Automated Negotiating Agents' Competition (ANAC) Diplomacy League**.  Entrants submit negotiating agents that play by being coupled to [D-Brane](https://link.springer.com/article/10.1007/s10489-017-0919-y), which picks moves.  See the [2019 call for participation](http://www.iiia.csic.es/~davedejonge/bandana/files/call_for_participation_2019.pdf) (deadline 20 May); negotiations use the [BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana), which has well-defined semantics.
-->
1. **articles in internationally recognised AI journals** describing members' work.  (The ANAC Diplomacy League was part of the [IJCAI](https://www.ijcai.org), International Joint Conferences on Artificial Intelligence.)
1. **beat human players** in online Diplomacy fora (e.g. [webDiplomacy](webdiplomacy.net)).  Initially, Gunboat Diplomacy, then full Diplomacy online and, finally, full Diplomacy face-to-face (e.g. at [WorldDipCon](https://en.wikipedia.org/wiki/Diplomacy_(game)#Major_championship_tournaments)).

## Key resources

### de Jonge, Baarslag, Aydo&#287;an, Jonker, Fujita and Ito (2018), "[The Challenge of Negotiation in the Game of Diplomacy](http://www.iiia.csic.es/~davedejonge/homepage/files/articles/The%20Challenge%20of%20Negotiation%20in%20Diplomacy.pdf)", The 6th International Conference on Agreement Technologies 2018, Bergen, Norway.

The best introduction to negotiating agents in Diplomacy.  This article contains a brief overview of Diplomacy, the BANDANA environment, leading entries in 2017, 2018 ANAC Diplomacy Challenges and the challenges facing negotiating agents.  None of the entries so far seem to engage in learning, much less reinforcement learning.

> none of the negotiation algorithms ... have been able to significantly improve the performance over a non-negotiating baseline agent

> Now that modern Chess and Go computers are already far superior to any human player [[15](https://www.nature.com/articles/nature16961)], we expect that Diplomacy will start to draw more attention as the next big challenge for computer science.

> we are not expecting the Diplomacy Challenge to have a winner any time soon. We regard it as a long term challenge which might take several years to tackle.

### [The BANDANA framework](http://www.iiia.csic.es/~davedejonge/bandana)

A Java framework for developing automated agents to play Diplomacy.  It calls the [Parlance](https://pypi.org/project/Parlance) game server.  BANDANA extends the [DipGame](http://www.dipgame.org/) framework; neither support convoy orders. 

[Downloads](http://www.iiia.csic.es/~davedejonge/bandana/download.php) include:
* [March 2018 manual](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%201.3%20Manual.pdf): download this first and follow the installation instructions for the BANDANA Java framework and Parlance game server;
* the accompanying [Java framework](http://www.iiia.csic.es/~davedejonge/bandana/files/Bandana%20Framework%201.3.1.zip);
* [2018 ANAC agents](http://www.iiia.csic.es/~davedejonge/bandana/files/Agents%20submitted%20to%20the%20ANAC%202018%20Diplomacy%20Challenge.zip).

The scoring system (12 points for a solo victory, etc.) is drawn from [PlayDiplomacy's](https://www.playdiplomacy.com/forum/viewtopic.php?f=7&t=30974).

### [The Rules of Diplomacy](https://media.wizards.com/2015/downloads/ah/diplomacy_rules.pdf) (Avalon Hill)

2008, 5th edition.  Here is the [2000 4th edition](https://web.archive.org/web/20040611030459/http://www.wizards.com/avalonhill/rules/diplomacy.pdf).  See Kruijswijk's [DATC](http://web.inter.nl.net/users/L.B.Kruijswijk/#3) for a list of previous editions.

### Paquette, Lu, Bocco, Smith, Ortiz-Gagné, Kummerfeld, Singh, Pineau and Courville (2019), "[No Press Diplomacy: Modeling Multi-Agent Gameplay](http://papers.nips.cc/paper/8697-no-press-diplomacy-modeling-multi-agent-gameplay.pdf)", NIPS

Introduces DipNet, a gunboat bot that is first trained (supervised learning) on a dataset of about 150,000 human Diplomacy games (of which c. 33,000 are gunboat), primarily from [webDiplomacy](webdiplomacy.net); this initialises self-play reinforcement learning. Its reward function includes both local terms (as supply centres are won/lost) and a terminal one (34 points for a solo victory, etc.).  As inputs, the model takes the "current board state and previous phase orders".

DipNet outperforms a number of benchmark bots, including Jason van Hal's [Albert](https://sites.google.com/site/diplomacyai/home), its benchmark bot.

The Python 3 DipNet code is available [here](https://github.com/diplomacy/research).  The code also includes a game server, implemented as an OpenAI gym.  DipNet bots are implemented on [webdiplomacy.net](webdiplomacy.net), allowing a human to play against six bots (of which there are two variants).  

>  the supervised agent was able to learn to coordinate support orders while this behaviour appears to deteriorate during self-play training.

A discussion of this is [here](http://webdiplomacy.net/contrib/phpBB3/viewtopic.php?f=5&t=1938), where Squigs44 explains the deterioration during self-play: "when it learned from webdip, it was able to more effectively support others. When it learned from itself, it was less effective at supporting others, and was more effective at winning. The goal of the bot isn't to support, it is to win. Since the bot is in a gunboat setting, it makes sense that supporting other countries wasn't as rewarding." 

Episode 52 of the [Diplomacy Games podcast series](http://diplomacygames.com/), the [Rise of the Bots](https://diplomacygames.com/rise-of-the-bots/) discusses these bots.  The 'Jane' bot is drawn from [Ender's Game](https://en.wikipedia.org/wiki/Jane_(Ender%27s_Game)).  The ethical question of whether to add messaging (thus, teaching bots to lie to humans) is raised, and countered by the observation that bots already bluff in poker.  It's noted (without explanation) that the bots' performance declines as game progress.

### Anthony, Eccles, Tacchetti, Kramár, Gemp, Hudson, Porcel, Lanctot, Pérolat, Everett, Singh, Graepel, Bachrach, "[Learning to Play No-Press Diplomacy with Best Response Policy Iteration](https://arxiv.org/pdf/2006.04635.pdf)", DeepMind

Built on Paquette et al. (2019) by introducing sampled best responses (SBRs) for policy iteration.  Along with some changes to the DipNet neural architecture, the result outperforms existing benchmarks, including DipNet.  The agents will be made open source once the paper is accepted for publication.

### de Jonge and Sierra (2017), "[D-Brane: a diplomacy playing agent for automated negotiations research](https://link.springer.com/article/10.1007/s10489-017-0919-y)", Applied Intelligence

Detailed description of the D-Brane (Diplomacy BRAnch & bound NEgotiator) modules, which seek to myopically maximise the Supply Centres gained _in the current round_ using And/Or tree search with Branch & Bound.  Thus, while tactically strong, it is not built for longer-term planning.

## Other resources

### [Parlance](https://pypi.org/project/Parlance/)

A Python 2 framework for playing the Diplomacy board game over a network.  [BANDANA](http://www.iiia.csic.es/~davedejonge/bandana) calls it.  Successor to [DAIDE](https://daide.org.uk).

### [Parang](https://pypi.org/project/Parang/)

A set of bots to play Diplomacy over Parlance, from **blabberbot** ("A simple bot that sends constant streams of random press") to **neurotic** ("A neural-network bot, which unfortunately has no memory yet") and **peacebot** ("A simple bot that invites each player to be peaceful").

### Kemmerling, Ackermann, Preuss (2011), "[Nested look-ahead evolutionary algorithm based planning for a believable diplomacy bot](http://ls11-www.cs.tu-dortmund.de/_media/rudolph/planning-diplomacy-bot.pdf)", European Conference on the Applications of Evolutionary Computation

Provides a history of Diplomacy bots, including Stragotiator (reportedly able to pass the Turing Test in some short games).  Estimates that the number of possible placements for 34 units is 4.09 x 10^27, with each capable of executing about 7.24 moves on average (without convoying).  Reports on results of play by a version of Stragotiator with enhanced planning against raw Stragotiator and Albert.

### Shapiro, Fuchs and Levinson (2002), "[Learning a Game Strategy Using Pattern-Weights and Self-Play](https://link.springer.com/chapter/10.1007/978-3-540-40031-8_4)", Third International Conference on Computers and Games

Trained a TD RL system on an existing knowledge base.  In contrast to the ANAC project, this system plays 'gunboat' Diplomacy, moving without negotiations.  &#0167;2 describes the game graph and action space.

### Stormont and Allan (2012), "[A comparison of Diplomacy gameboard graph search algorithms](https://scitepress.org/papers/2012/37531/37531.pdf)", Fourth International Conference on Agents and Artificial Intelligence (ICAART)

"This paper addresses one element of creating a planner for a Diplomacy agent: an efficient search algorithm for determining the shortest path to achieving victory in the game".

### [World Diplomacy Database](http://world-diplomacy-database.com)

Includes:
1. [tournaments](http://world-diplomacy-database.com/php/results/tournament_list.php);
1. player [rankings](http://world-diplomacy-database.com/php/ranking/index.php) under a number of systems;
1. different [scoring systems](http://world-diplomacy-database.com/php/scoring/scoring.php).

### [Diplomacy Archive](http://www.diplomacy-archive.com/)

An archive of 'zines and articles; FAQ last updated in 2002.

### online Diplomacy games

Some online fora for playing Diplomacy are:

#### [webDiplomacy](https://webdiplomacy.net/)

A [GitHub project](https://github.com/kestasjk/webDiplomacy), which - in 2019 - became the first online Diplomacy game to [host bots](http://webdiplomacy.net/contrib/phpBB3/viewtopic.php?f=5&t=1938) (see Paquette et al. 2019, above).

In Sept/Oct 2019, webDiplomacy ran its first human v bot [Terminator Tournament](http://www.webdiplomacy.net/contrib/phpBB3/viewtopic.php?f=10&t=1937).  The overall rate of solo victories by the c. 70 human players was about 30%; of the c. 20 top human players, the solo rate was still less than 50%.  Discussions on webDiplomacy and in the [Rise of the Bots](https://diplomacygames.com/rise-of-the-bots/) podcast indicate that the bots are unexpectedly strong.

webDiplomacy's Discord channel is [here](https://discord.gg/dPm4QnY).

#### [PlayDiplomacy](https://www.playdiplomacy.com/)

Top 25 players are displayed [here](https://www.playdiplomacy.com/stats.php?sub_page=1).  Like Elo ratings, [PlayDiplomacy rankings](https://www.playdiplomacy.com/stats.php?sub_page=3) reflect the strength of the opposition that players have overcome.  The exact formula is deliberately secret to prevent "[play[ing] the system rather than the game](https://www.playdiplomacy.com/forum/viewtopic.php?f=129&t=34913#p602092)", but seems to assign 12 points for a solo victory, and decreasing weight to older games (a system called '[fading echoes](https://www.playdiplomacy.com/forum/viewtopic.php?f=7&t=30974)').

A basic order adjudication tool is available [here](https://www.playdiplomacy.com/judge/new_manual.php).  Their online discussion forum is [here](https://www.playdiplomacy.com/forum/).

#### [Backstabbr](https://www.backstabbr.com)

Backstabbr's order adjudication [claims to be compliant](https://www.backstabbr.com/faq) with [DATC](http://web.inter.nl.net/users/L.B.Kruijswijk/).  It is supported by a [Discord server](https://discordapp.com/invite/4CVbMjh).

#### [The DPjudge](http://uk.diplom.org/)

A deceptively unimpressive website disguising serious games and content, including [The Diplomatic Pouch 'zine](http://uk.diplom.org/pouch/Zine), dating back to 1995.  Their order adjudication algorithm is described [here](http://uk.diplom.org/?page=Algorithm). They provided messages for analysis by [Niculae et al. (2015)](http://vene.ro/betrayal).

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

### Kruijswijk's [Diplomacy Adjudicator Test Cases](http://web.inter.nl.net/users/L.B.Kruijswijk/) (DATC)

Detailed discussion of algorithmic order adjudication based primarily on the 2000 Diplomacy rules.  Last updated in 2009.

### [Diplomacy AI Development Environment](http://daide.org.uk) (DAIDE)

A UK-based Diplomacy AI community project begun in 2002, which is now moribund.  There seems to have been no significant new material added to the website since 2013.  A brief history is [here](DAIDE-brief-history.md).

Its message syntax is the most sophisticated developed for Diplomacy AIs.  The March 2010 DAIDE Message Syntax document is [here](http://www.ellought.demon.co.uk/dipai/daide_syntax.pdf).

### NLP

#### Niculae, Kumar, Boyd-Graber, Danescu-Niculescu-Mizil (2015), "[Linguistic Harbingers of Betrayal: A Case Study on an Online Strategy Game](https://www.aclweb.org/anthology/P15-1159)", Proceedings of the 53rd Annual Meeting of the Association for Computational Linguistics and the 7th International Joint Conference on Natural Language Processing, pages 1650–1659, Beijing, China

Collected 145,000 dyadic messages from 249 games (JSON format) played on [The DPjudge](http://uk.diplom.org) and another online forum.  The messages were then analysed using tools such as Stanford's [Sentiment Analyzer](https://nlp.stanford.edu/sentiment) and [politeness classifiers](https://nlp.stanford.edu/pubs/politeness.pdf).

> half of the games have over 515 messages exchanged between the players, while the top quartile has over 750 messages per game. Also, non-trivial messages (with at least one sentence) tend to be complex: over half of them have at least five sentences, and the top quartile consists of messages with eight or more sentences.

> The resulting model achieves a cross-validation accuracy of 57% and a Matthews correlation coefficient of 0.14, significantly above chance ... This indicates that, unlike the actual players, the classifier is able to exploit subtle linguistic signals that surface in the conversation.

![alt text](http://vene.ro/betrayal/time.png "The dynamics of betrayal")

The authors' page [here](http://vene.ro/betrayal/) summarises their findings and presents their anonymised data, and video and slides from their ACL 2015 talk.  Also mentioned by security expert [Bruce Schneier's blogpost](https://www.schneier.com/blog/archives/2015/08/detecting_betra.html).

### Masters' theses

#### Cruz and Lopes Cardoso (2019), "[Deep Reinforcement Learning in Strategic Multi-Agent Games: the case of No-Press Diplomacy](https://github.com/BlueDi/DeepDip)", Universidade do Porto

Introduces DeepDip, an openAI gym based on Parlance and BANDANA to play no-press Diplomacy on three map variants: the original, a three-player version, and a two-player version.

#### Fernandes de Mascarenhas (2017), "[AI player for board game Diplomacy](https://fenix.tecnico.ulisboa.pt/downloadFile/1970719973966529/Thesis.pdf)", Técnico Lisboa

Surveys DAIDE, including the bots developed for it, and presents Tagus, its own (hard-coded) bot.

#### Webb, Chin, Wilkins, Payce, Dedoyard (2008), "[Automated Negotiation in the Game of Diplomacy](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.466.6361&rep=rep1&type=pdf)", Imperial College

Project report of MEng students, supervised by Iain Phillips.  On AI/ML:

> Machine Learning Currently most bots learn very little during the course of play. If a bot can be designed that interprets and learns from the actions of its opponents a better bot may be created.

#### Huff, Chan, Tondelier, Bundred, Egan (2005), "[Automated Negotiation in the Game of Diplomacy](https://www.tofgarion.net/lectures/XX201/diplomacy/reportHuff.pdf)", Imperial College

Project report of MEng students, again supervised by Iain Phillips.  &#0167;2 reviews existing Diplomacy bots.  No AI/ML used.

#### Ritchie (2003), "[Diplomacy — A.I.](http://daide.org.uk/external/ritchie200309.pdf)", University of Glasgow

MSc thesis supervised by Ron Poet.  Chapter 3 discusses theories of Diplomacy play.

### podcasts!?

Yup, a [This American Life podcast](https://www.thisamericanlife.org) episode, [Absolutely Stabulous](https://www.thisamericanlife.org/531/got-your-back/act-one), emphasising the importance of the strategies beyond the board:

> "And the way he said it to me made me feel like it wasn't a manipulation." (Ambassador [Dennis Ross](https://en.wikipedia.org/wiki/Dennis_Ross))

> "I want to tell you how much ... I was impressed by this" (Ambassador [Dennis Ross](https://en.wikipedia.org/wiki/Dennis_Ross))

The podcast covers some of the material in David Hill's "[The Board Game of the Alpha Nerds](http://grantland.com/features/diplomacy-the-board-game-of-the-alpha-nerds/)":

> If you’ve ever heard of Diplomacy, chances are you know it as “the game that ruins friendships.”

> Edi took out scissors and a pen from a drawer and set to work on the letter, painstakingly doctoring it. When he was finished he held up the letter proudly and read it to himself. *I am against a three-way draw and I will take three more supply centers …* He put the forgery in the mail to the third player. Then he waited.

> “What I love about the game is that no one can really play the game ‘right,’” Birsan said. “Otherwise, after 50 years, that would have been discovered long ago and the hobby would have died of boredom.”

Would you believe, a whole [Diplomacy Games podcast series](http://diplomacygames.com/)?

### [Diplicity](https://play.google.com/store/apps/details?id=se.oort.diplicity)

Android app implementing a non-copyrighted variant of Diplomacy; the "spiritual successor" to Droidippy.

