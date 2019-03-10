---
layout: post
title: Imagine failure
comments: true
---

I recently transitioned from serving as a product manager to serving as vp of engineering.
In a reductionist sense, this means more chaos, less definition of priorities, and
more responsibility for outcomes. Instead of being on the hook for one product,
with a high level of autonomy to propose KPIs and roadmaps before going heads down
into execution mode, I'm now on the hook for a well-functioning engineering
organization that delivers *on time* with *high quality* against product requirements.

The problem at higher leverage points in an organization is not "how?" but "what?", with fewer
and fewer constraints. This applies both to how a manager spends his or her time as well as how the
rest of the org spends their time.

It's easy to start immediately filling a backlog of work and bringing things forward
into the latest JIRA sprint. What better way to start than by incrementally knocking
tasks out of the way? The answer: any way but _this_. This is a trap. It's also very common,
especially for young managers like myself. In all likelihood, the reason we've found
ourselves in a management situation is an ability to execute well and move the needle.

But, the bet that others make is that we (new managers) can figure out how to make ourselves
scale. The worst way to scale is by continuing what got you to this position in the first
place: being a great executor. The better way to scale is using judgment and critical thinking
 to determine direction, identify high leverage individuals, and align on ownership and measurement of output.

> Judgment and critical thinking, not the work ethic that got you here, are what's
needed to be a high output manager. A manager who needs to make the decisions about what
you, and more importantly, others should be working on and how their output will
be measured and reviewed.

## Use Pre-mortem Retrospectives!!!

To help smooth my own transition, I was lucky to have a razor sharp former operator shadow me
for two weeks. One exercise he used was to imagine failure 3- to 6-months out and
imagine the reasons. After some googling, this exercise is called a
[_pre-mortem retrospective_](https://productownerblog.wordpress.com/2016/05/03/pre-mortem-retrospective/).

This was useful for me to align on what I and others should be working on. It was
also useful for the rest of the team to **(1)** **surface concerns that they may not be able
to influence** and **(2)** **feel ownership and accountability for their work**.

The exercise goes something like the following:

1. Moderator starts exercise.
> Imagine that we meet again in 6 months, we're all at our next jobs because
the company failed. We catch-up for a bit and then think back to what went wrong. What do
you think went wrong?

2. Go around the room and surface all possible reasons, regardless of actionability or likelihood.

3. Arrange possible reasons by those that can be derisked by the team in the room.

4. Align on ranking of `likelihood * impact` of risks that can be mitigated by the team in the room
(this is a classic equation for rank-ordering risk, especially in security).

By the end of this exercise, there should be a clear set of priorities for the next month or two, after which
the exercise can be revisited to identify new risks encountered or whether to use some bandwidth of team members
to help with risks not within the domain of the team.

A few housekeeping items:
- Send out the full list and CC relevant people not in the room.
- Assign owners to the top risks that can be mitigated by the team.
- Revisit during each sprint meeting (try to map themes of sprint against risks).

**Note**: It is incredibly important to address risks outside of the domain of the team.
For engineers, some of the perceived risks may be closer to marketing, finance or product domains.
For instance, will the unit economics work? Will we be differentiated enough from
competition in eyes of consumers? It's _very important_ that these concerns are
addressed by the people working on these areas. This can be in all-hands staff meetings
or in one-on-ones. In the absence of information, engineers often
assume the worst. Relevant owners should communicate progress on derisking those
concerns (even if some of the feedback is negative, as communicating that will build trust).
