# Reflection

 * Course: AWK day 1
 * Teaching date: 2024-01-22
 * Teacher: Richel
 * Group size: around 20

I scheduled 3 days of preparation, which I know is enough time
to prepare properly.
I did assume that (1) modifying existing course material 
would be easy, and (2) existing AWK material would suit my needs.
It would take 1.5 days before the social aspect
of modifying course material was settled. Then, it would take
0.5 days before I discovered that the two AWK resourced would not suit my needs.
Due to this, I added another day of preparation in the weekend,
which would result in 2 days of effective preparation and 0 days of rest.
I did, however, feel confident I would be able to finish enough 
course material on time in a good enough state, which worked out well.
In then end, on the course day, I started at 4:30 in the morning, 
I had half an hour of time left. It had worked out! Question was:
would I be fit enough for proper teaching (spoiler: yes)?

At 9:15 sharp I started the lesson. 
I put my lesson plan on screen and followed it
the first part:

> Ask to turn on cameras

About half of the learners quickly did so.

> Present 'Who is Richel'

I find this quite dull, yet I do think I should follow the literature
and do so. Also, it does help to quickly show that I think lectures
are ineffective.

I did not ask if there were questions afterwards. 

 * [ ] I think I should as for questions after presenting about myself, 
   as it allows the learner to (1) get comfortable asking questions,
   (2) get to know me a little better (building rapport is one of the goals of the 
   presentation)
   
> Repeat to turn on cameras

About three fourths of the learners were visible at this point

> Poll: Who knows what grep is?

I used the Zoom 'Reaction' tool to make all learners
show 'Yes' or 'No'. I repeated the question two or three times ('Who knows what grep is?'),
showing 'Yes' while saying 'Yes, I know what grep is' and showing 'No' 
while saying 'No, I have no idea what grep is'. I asked the last learners
to pick a Yes/No and counted.

All learners knew what grep is.

> Poll: Who knows what sed is?

Same procedure.

Half of the learners knew what sed is.

> Poll: Who knows what C is?

One in four learners knew what sed is.

> Give overview of course

I showed the overviews of both morning and afternoon session. 

 * [ ] I feel that 'morning' and 'afternoon' are misnomers, 
   as I do not care about the exact time of teaching content.
   There was a learner that explicitly asked for this after lunch:
   'Should we continue with our exercises, or move to the afternoon
   exercises?'.
   I will change this to 'schedule', 'basic AWK' and 'AWK and friends'
   instead.

It was time to start the first teaching cycle:

> Ask to associate on 'AWK is'

The learners had a good idea that AWK is an interpreted language to work on text.

After this, I showed the exercise first, asked for questions,
then discussed the exercise procedure. There again, I asked for questions.
It was at 9:45, hence after half an hour in, that the learners started on
the first exercise. I do wonder: could I have been quicker? Should I have
taken this time to get the learners ready? I do feel I should,
yet I have no idea what to remove.

The learners were assigned to Zoom breakout rooms.
The learners that had two login (e.g. one login to share a computer and one
login for camera and microphone) stayed to help realize I should put
both alter egos in one room, after which I did.

With the learners gone, I discussed with the helper 
How I hope they will behave in breakout rooms.
We discussed this fruitfully.
The helpers went into the breakout rooms and would come back later to report.

Everything worked as planned:
the learners worked fruitfully in group rooms,
came back when done, helped in other rooms when asked,
and breakout rooms were closed ruthlessly at the moment when most learners were done.
I asked multiple learners about how the exercise workflow feels and works
out and there was only positive reactions. Sure, I realize that there is
a bias for being positive here :-)

At 15:55, I called back the learners. I repeated what we did and
showed what we did not discuss. I told them that the day after
Jonas will teach them. I thanked them and we all left the Zoom room.

## Discussion Pavlin

Me and Pavlin were discussing the pros and cons of having learners
teaching. One problem with having learners teach is that
they can teach misinformation.

I have been searching the literature:

 * Question: is peer teaching a good thing?
   [Bene & Bergus, 2014] show a study where they compare
   learning with learning and teaching, 
   which has an Effect Size of 2.1 [Gregory et al, 2011]. This is a
   a massive effect size (e.g. homework has 0.29).
 * Checking [Wikipedai's Computer-supported collaborative learning's teacher roles](https://en.wikipedia.org/wiki/Computer-supported_collaborative_learning#Teacher_roles)
   find that CSCL has an effect size of 0.51, which would be 47 on the 150 item
   list by John Hattie

I asked ChatGPT about the relevant of peer teaching and learners teaching
misinformation. ChatGPT cited some literature and claimed that it is
a feature that needs to be in mind, but I could not pry a number out of it.
One of the most important ways to counter it, however, is providing
feedback. As I do provide feedback, I feel unworried to let learners teach.

## Reflections during Day 2

During Day 2, I feel that the learners did not seem to be 
ready to solve the problem, as they had not learned:
- Multiple files
- `FRN`
- For loops using a counter
- 2D associative arrays
- the `split` functions
- `next`

An open question is (1) (again) did the teaching cover too little
topics, (2) should the exercise be simplified?

My feeling is that the exercise should be simplified, because
- the exercise does not make AWK shine, instead this is where Tidyverse/pandas shine instead
- the exercise has too many biological terms, instead a more general
  research should be done
- the data files in the exercise are big: it is unimportant to have 4GBs
  of data, instead settle for files that are 1 MB max

Or, alternatively, the second day should start
with teaching the things that the learners will need.

## References

- [Bene & Bergus, 2014] Bene, Kristen L., and George Bergus. "When learners become teachers." Fam Med 46.10 (2014): 783-7.
- [Gregory et al, 2011]Gregory, Alexander, et al. "Both preparing to teach and teaching positively impact learning outcomes for peer teachers." Medical teacher 33.8 (2011): e417-e422.
