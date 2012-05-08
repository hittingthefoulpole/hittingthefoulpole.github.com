---
layout: post
title: Introducing Manager Wins Above Expected
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '2'
  dsq_thread_id: '546271056'
author: sirsean
---
A lot of people have spent a lot of time thinking about how to measure the performance of a player on the field, and they've largely done the same for the performance of a GM in his office. But when it comes to the manager, there's the hand-wavy "Well it's the players' talent that's important, the manager doesn't do anything" dismissal.* Some go so far as to say a good manager can be worth up to a couple extra wins over the course of the season; conversely, perhaps, a bad manager may be worth a couple of extra losses.

<em>* This dismissal seems strange to me, given that there are new stats like WXRL and WPA/LI, etc, which take into account success -- and opportunities -- in tough, meaningful situations. IE, exactly the situations in which a good manager is supposed to make the moves that put the right players in the best position to succeed. If there's something to what a manager does, and it's not just random dice rolling that determines whether that reliever records a strikeout or that pinch hitter hits a home run, then there must be some way to measure it.</em>

But it seems that nobody's tried to actually measure a manager's impact. The "best manager" discussion is always couched in terms of total wins, or total championships, or total-number-of-nostalgic-stories-told-by-old-sportswriters, rather than attempting to objectively discover who have been the best (and worst) managers in the history of baseball.

Thus, I have set out to try and figure it out.

I start with the notion that a team's Pythagorean record "predicts" how many games a team should win based on its totals of runs scored versus runs against. I would say that one (significant) goal of every manager is to attempt to squeeze more actual wins out of the team's runs for/against than the formula would predict. (Though I doubt many managers would couch their goals in terms like that.)

So I went through the entire Retrosheet database from 1871-2008, counting the actual win-loss record and summing the runs scored and given up for all the managers, ever. It doesn't go by team, but by manager; for example, if Ron Gardenhire were suspended for arguing with an umpire, and Scott Ullger replaced him for a couple of games, then those games and runs would count toward Ullger rather than Gardenhire. Similarly, if Ned Yost is fired in the middle of the season and Dale Sveum takes over, any games Sveum managed count towards Sveum, not Yost. Should be obvious enough.

Once I've summed up the win-loss record and the runs for/against, I can calculate each manager's expected win total based on their Pythagorean record. If this method makes sense, then good managers will have more actual wins than expected wins, and bad managers will have fewer than expected.

Retrosheet's gamelog files for many seasons in the 1970s-1990s have been down for weeks. Thus, my data are incomplete, which is too bad. Hopefully at some point I'll be able to pull down the rest of Retrosheet's data to complete my analysis. In the meantime, I've limited my analysis to 2002-2008, which is the only modern stretch for which I have data. I also decided to limit it to managers with at least 200 total wins, to keep any small-sample-size bias out.

In any case, looking at the limited data, here are the 11 managers who were able to average one win more than expected, per season, over the course of the last seven years:
<pre>+----------------+------------+------------------+-----------+------------+-----------------+
| manager_name   | total_wins | total_diff       | max(diff) | min(diff)  | average_diff    |
+----------------+------------+------------------+-----------+------------+-----------------+
| Felipe Alou    |        341 | 15.1456443071365 |   6.07211 |    1.95034 | 3.7864110767841 |
| Ozzie Guillen  |        432 | 13.0560693144798 |    6.8328 |   -1.13229 |  2.611213862896 |
| Jack McKeon    |        241 | 7.37834513559937 |   3.75759 | -0.0560862 | 2.4594483785331 |
| Frank Robinson |        385 | 10.7293409258127 |   4.19535 |   0.104871 | 2.1458681851625 |
| Joe Torre      |        673 | 14.6219349503517 |   11.7966 |   -4.97134 | 2.0888478500502 |
| Ron Gardenhire |        615 | 14.1632239818573 |   7.41682 |   -1.74507 | 2.0233177116939 |
| Mike Scioscia  |        645 | 12.9273184239864 |   11.4814 |   -4.00882 | 1.8467597748552 |
| Ken Macha      |        368 | 6.79638695716858 |   7.24576 |   -5.83313 | 1.6990967392921 |
| Bob Melvin     |        481 | 9.29994755983353 |   12.5254 |   -5.65932 | 1.5499912599723 |
| Ned Yost       |        457 | 6.62773448228836 |   4.62946 |   -3.30011 | 1.1046224137147 |
| Tony LaRussa   |        634 | 7.61316386237741 |   7.79336 |   -3.73349 | 1.0875948374825 |
+----------------+------------+------------------+-----------+------------+-----------------+</pre>
Felipe Alou's second career as a manager -- with the Giants -- was shortlived, but he did a hell of a job. He averaged +3.79 wins per season above expected, and was never worse than +1.9 wins. (I don't have any data from his time with the Expos, unfortunately, so this is just when he was with the Giants.)

It's absolutely not surprising that Scioscia is high on the list, given that he was +11 Wins Above Expected in 2008 alone. (Indeed, if you removed 2008 from the sample, his average would drop from +1.8 to +0.2.)

Ozzie Guillen, Frank Robinson, Joe Torre, and Ron Gardenhire are generally regarded as good managers, and they appear high on the list. Tony LaRussa is well regarded, but for all his late inning machinations, he's only +1 WAE/year recently. (Perhaps he was better when he was younger. Further investigation is needed.)

Also, how would you like to be Ned Yost, fired at the end of a season in which you guided your team to the playoffs, after having been a top ten manager over the course of the decade? Probably wouldn't like it much.

If this is a viable investigation, looking at the bottom of the list should show bad managers. So let's look for everyone who won at least 100 games in the last seven years, and averaged worse than -1 WAE (ie, they were one game worse than expected per season).
<pre>+----------------+------------+-------------------+-----------+-----------+------------------+
| manager_name   | total_wins | total_diff        | max(diff) | min(diff) | average_diff     |
+----------------+------------+-------------------+-----------+-----------+------------------+
| Alan Trammell  |        186 | -14.2434198856354 |  -3.14609 |  -7.35206 | -4.7478066285451 |
| Jimy Williams  |        214 | -13.0165817737579 |  -1.92939 |   -7.8883 | -4.3388605912526 |
| Eric Wedge     |        495 | -22.6846791505814 |   3.61521 |  -11.6051 | -3.7807798584302 |
| John Gibbons   |        308 |  -16.938233718276 |  0.306474 |  -8.64506 |  -2.823038953046 |
| Jerry Manuel   |        222 | -8.36836788058281 |  0.459961 |   -5.6738 | -2.7894559601943 |
| Buddy Black    |        152 | -4.59854626655579 |  -1.16408 |  -3.43447 | -2.2992731332779 |
| Lee Mazzilli   |        129 | -4.35584957897663 |  -0.19323 |  -4.16262 | -2.1779247894883 |
| Jim Leyland    |        257 | -6.27698922157288 |   -1.6333 |   -2.8878 | -2.0923297405243 |
| Grady Little   |        358 |  -8.0911720469594 |  0.189979 |  -8.29321 | -2.0227930117399 |
| Bob Geren      |        151 | -3.36636139452457 |  -0.20335 |  -3.16301 | -1.6831806972623 |
| Bobby Cox      |        624 | -11.7078827321529 |   3.74093 |  -6.35538 | -1.6725546760218 |
| Clint Hurdle   |        516 |  -11.283863902092 |    4.6587 |  -5.09969 | -1.6119805574417 |
| Larry Bowa     |        251 | -4.51537179946899 |   1.07168 |  -5.19319 | -1.5051239331563 |
| Dusty Baker    |        491 | -8.68119883537292 |   3.29847 |  -5.71592 | -1.4468664725622 |
| Jerry Narron   |        230 | -5.34940385818481 |   4.42873 |  -5.33926 | -1.3373509645462 |
| Carlos Tosca   |        188 | -3.84612214565277 | -0.553967 |  -1.98905 | -1.2820407152176 |
| Buck Showalter |        318 | -4.37028300762177 |      2.84 |  -6.09809 | -1.0925707519054 |
+----------------+------------+-------------------+-----------+-----------+------------------+</pre>
It's not exactly surprising that these guys all managed teams that underperformed, given that that's basically what we're measuring. How much of these underperformances were random ups-and-downs, and how much were they influenced by a poor job by the manager?

For the most part, the guys on this list are bad managers of bad teams. It may be that Wedge, Leyland, Bowa and Cox are actually better managers than appears on this list and that because of our subjective opinions of them, we want to discount this analysis. But it's probably worth some harder thought into it. Cox was a great manager, and he's had a great career; however, he's getting old and may not be able to connect with his players or think as quickly as he used to. I've always thought Wedge was a good manager, but how many times does he have to take a roster that's absolutely loaded with talent and guide them to a terribly disappointing season before maybe it's not random, and is in fact his fault?

I'd like to fill this out with more years worth of data from Retrosheet, to get a better look at the careers of Cox, LaRussa, and Torre, along with some historical managers. I think this is a good start, but would be better if I could look at a manager's year to year performance and see if there are any managers who are consistently above their expected wins (like Guillen and Gardenhire appear to be) rather than relying on one amazing season (like Scioscia).

Thus far it looks like it should be possible to measure the performance of a manager, in such a way that one can be compared to another. I'm not there yet, but this appears to be a (small) step in the right direction.
