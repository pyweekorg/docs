---------
The Rules
---------

:revision date: 2020-02-06


The PyWeek challenge:

1. Must be challenging and fun,
2. Entries must be developed during the challenge, and must
   incorporate some theme decided at the start of the challenge,
3. Will hopefully increase the public body of python game tools, code
   and expertise,
4. Will let a lot of people actually finish a game, and
5. May inspire new projects (with ready made teams!)


1. Entry is individual or team-based
------------------------------------

You may either enter as an individual or as a team with as many members as
you like. Individual and team entries will be judged separately and
a winner announced in each category.

All members of a team get to vote (though not for their own team), enter diary
entries and upload files. People may join more than one team.

During the challenge, competitors are encouraged to post diary entries (diaries
are supplied as part of the challenge), and hang out on
`Discord <https://discord.gg/python>`_ (channel ``#pyweek``).

By signing up to the challenge, you are agreeing to abide by
the system :doc:`conditions of use <conditions>`.


2. Entries are to be written "from scratch"
-------------------------------------------

The intent of this rule is to provide a level playing-field for all entrants.
The short version is this: any resources you prepare before the competition
must be made both *available* and *accessible* to all other entrants,
regardless of whether they were created by you or by others. "Available" means
that they must be published in good time, in a place where other entrants might
discover them. "Accessible" means making sure others are not prevented from
using them once aware of them.

1. You may not use code created before the competition except under the
   conditions of clause 2.2 and 2.3. This includes using the code as a point of
   reference.

2. You may use libraries that were created before the competition
   if and only if

   a. they have been published to a public searchable index such as PyPI,
      GitHub, or this handbook for at least 30 days before the competition;
      and,
   b. they are licensed under an `OSI-approved open source license
      <https://opensource.org/licenses>`_, or are public domain; and,
   c. the index page (eg. README/PyPI page) contains, or links to,
      a documentation resource that describes the features of the library and
      contains thorough API documentation; and,
   d. the library does not contain game logic, ie. it is agnostic about
      theme, backstory, character types, game objects, behaviours, and so on,
      and requires customisation with Python code in order to define these
      qualities and behaviours.

3. You may use code posted in blog entries if and only if

   a. The blog entry was published to the Internet at least 30 days before
      the competition; and,
   b. it is specified or implied that the code is free to redistribute,
      eg. that it is public domain; and,
   c. the blog entry contains prose describing the purpose of the code; and,
   d. the code does not contain game logic, under the same definition
      as clause 2.2.d, unless the logic is provided as an example and you
      replace it.

4. You may use AI development tools without restriction.

   AI-powered development tools (such as code completion, code generation,
   refactoring assistants, and debugging aids) are freely permitted during
   the competition. This includes but is not limited to tools like GitHub
   Copilot, ChatGPT, Claude, and other AI coding assistants.

   This policy recognizes that AI has become commoditized with widely
   available open source models, and AI assistance has rapidly become a
   standard part of modern software development. Since the rules do not
   generally restrict development tools (such as IDEs, debuggers, or
   linters), AI tools are treated similarly as productivity aids rather
   than pre-written code resources.


3. The time limit is 1 week
---------------------------

The challenge starts 00:00 UTC Sunday and finishes 7 days later at
00:00UTC Sunday.

Work done on entries before this time would be considered cheating.

Once the time limit is up entrants will have 24 hours to upload their
file(s). This is not extra development time. Failure to upload at the
last minute of that additional 24 hours will be met with zero leniency.
The server will overload if you try. You have been warned.

If your game crashes it's on your head. You should allow time for
testing well before the deadline.


4. Theme is selected by the competitors
---------------------------------------

The theme of the challenge will be determined by a vote in the
week leading up to the challenge.

The theme exists to serve two purposes:

1. Inspire entrants at the start of the challenge, and
2. Discourage cheating.

How entrants interpret the theme (whether it be cosmetically or for deeper
meaning) is completely open.

A shortlist of five themes will be selected by the organisers. These are
drawn at random on the evening before theme voting begins.

In the week leading up to the challenge, all participants get to place a
preference against each of the five themes. The vote preferences are tallied,
according to instant-runoff rules. The winner of that vote is announced
at the point that the challenge begins.

All votes will be recorded for later examination.


5. Entries are judged by peers
------------------------------

Judging of final submissions will be done by your peers, the other souls
brave enough to grind away for 7 days and compete with you (and finish).
Judging is performed by the individual competitors, so every member of a
team entry gets to vote. Competitors are not allowed to vote for any
submissions they are involved with (so people signed up to multiple
teams can vote for none of those teams).

Judges will score each game in three categories:

- Fun
- Innovation
- Production (graphics, sound, polish)

An overall score will be calculated as the average of these scores.

Gold, silver and bronze awards will be given for each of these categories; the
overall score will decide the overall winner of the competition.

If the game did not work for a judge, they may mark the game "Did Not
Work". Their ratings in the categories above will not count towards its
final ratings tally.

Finally, competitors may vote that a submission be disqualified for one
of three reasons:

- Did not follow the theme of the challenge,
- Did not work on the target platform, or
- Entrant cheated.

A submission that gets more than 50% disqualification votes is not
eligible for any prizes, though they'll still appear in the rankings
("do'h, if only I'd followed the rules!")


6. Existing artwork, music and sound effects may be used
--------------------------------------------------------

As with the use of existing codebases, the intention is that all
entrants start with a level playing field in artwork too. This means you
shouldn't develop artwork beforehand that you intend to use during the
challenge *unless* you also make that artwork freely available to all
other entrants.


1. You may not directly include art, sound, music, writing or other data
   created before the competition, except under the conditions of clause 6.2.
   You may however use it as a point of reference, ie. as "concept art".

2. You may inclue graphics, sound and music created before the competition if

   a. They were published to a public website that has existed for least 30
      days before the competition; and,
   b. the work is licensed under an OSI-approved or Creative Commons
      license, or is public domain; and,
   c. you use only the files published. For example, you may not
      publish only PNG files but use source SVG files in your game.

Any diagrams and concept art created during the theme voting week should not
form part of your submission unless clearly marked as concept art.

There should be absolutely no breach of licensing. You can't just
cut-n-paste in artwork from The Simpsons (TM).

The :doc:`resources` page has a list of resources you can use. Also check out
the `PyGame wiki's game resources page <http://www.pygame.org/wiki/resources>`_.


.. _final-submission:

7. Your Final Submission
------------------------

You may upload your final at any time during the challenge. You may even
upload multiple final submissions. Only the last one will actually
be used for judging.

Your entry **must** include all code and data required for running, and
instructions about how to run the entry.

See :doc:`packaging` for some guidelines about how to package your entry.


8. Licensing
------------

1. You retain all copyrights to entries you upload.

2. By uploading an entry you warrant that you have the right to distribute all
   materials in the entry under the terms laid out in this section of the
   rules.

2. By submitting an entry to PyWeek you grant a transferrable, irrevocable
   license to redistribute, copy and run your entry without modification,
   and to distribute unmodified screenshots of the entry, provided no fee is
   charged.

3. You may include license terms in your entry; these will be considered an
   alternative set of terms to those defined by clause 8.2.


9. Target platform
------------------

This is a Python programming challenge. However, you may include code written
in supporting languages (eg. C/C++ or Rust libraries, Javascript/HTML in web
pages, and so on), if that code does not implement "game logic".

Entries must run using the latest version of Python. Entries must not require
end-of-life versions of Python. See `the Python Dev Guide
<https://devguide.python.org/#status-of-python-branches>`_ for which Python
versions are allowed.

Entries should specify requirements in a ``requirements.txt``, or otherwise
must run with the latest released versions of libraries.

If you are the maintainer of a library, we would ask that you make all
efforts to not sabotage existing users of your library. Please be diligent
about backwards compatibility, providing changelogs, and versioning your
releases.

If you add features to your library leading up to the challenge, please take
great care to ensure that other entrants have a reasonable opportunity to
learn about and use these features. This includes updating the documentation
and announcing the feature in a changelog or release announcement.


10. Code of Conduct
-------------------

All PyWeek entrants must abide by the PyWeek :doc:`coc`.
