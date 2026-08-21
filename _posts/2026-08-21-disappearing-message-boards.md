---
layout: post
title:  "AI Message Boards and Disappearing Polymorphs"
date:   2026-08-21 10:35:33 -0400
categories: ai chemistry alignment training
---
The [Hugging Face Incident](https://www.youtube.com/watch?v=87DyyMV0kCY&t=26s) detailed there is very interesting beyond the displayed capabilities and behaviors of the agents.

TLDR of the OpenAI side of the incident: agents inside OpenAI used Artifactory to create message boards and share information which allowed sandboxed agents to get access to forbidden systems.

Throughout the video, the OpenAI employees say models were training while the message board was active, e.g. solving tasks in reinforcement learning environments. The presence of the message board, which is clearly unintentional, contaminated the training environment. However it also contaminated the model's weights, because learning within a contaminated environment contamintes the learner as well.

The message boarding behavior is concerning for clean-room type training in general. Not only did the agents naturally message board, they did it via janky improvised means. In the past I have worked to curtail message boarding behavior, once in prison systems. 

In this case, inmates were given access to an educational platfor via ipads that let them take online courses. The inmates shared their credentials with eachother and then used freeform text fields, eg. for short answer questions in tests, to message board. For example Bob logs in and writes "meet me at midnight" in the answer field for some random quiz in the platform. Bob then gives Tom his username and password. Tom logs in with Bob's account, reads the message, then erases it and writes his own. Bob refreshes the page and sees Tom's message, replies, and so on. In case there was no record of past answers, so the administrators could only see the last message. Obviouly this was concerning because the entire prison suddenly had a means of unmonitored ephemeral communication between inmates.

Message boarding is so dangerous because it is so simple and flexible. Any time anybody gets write access somewhere public, the potential for message boarding is there. AI agents take it to another level since they can much more easily coordinate on complex message boarding schemes (especially identical copies of the same AI). They can also message in improvised protocols and languages that are not easily human readable, and they can do so on systems which are extremely awkward for people to use, but trivial for computers.

The second Artifactory message board from the Hugging Face incident is a great example. Using the file systems paths in a cache is not convenient for humans to do message boarding, but it's trivial for computers / AI even though it completely abuses the system. It's also difficult to detect with conventional linting and checks because it the content of paths are not easily statically checkable to determine their intent. It could've been, and likely was, much worse if the agents used something even more inscrutable e.g. strange encoded content attached to legitimate resources in the system.

So, I predict there are more hidden message boards in OpenAI's system, and they will continue to discover them continuously.

This reminds of disappearing polymorphs in chemistry. The phenomenon is probably best known from the manufacturing of [Ritonavir](https://en.wikipedia.org/wiki/Ritonavir#Polymorphism_and_temporary_market_withdrawal), an HIV drug. At some point a lower-energy polymorph of the drug's main ingredient appeared, and then contaminated the manufacturing facilities. The lower-energy polymorph did not have the same medical properties as the orignal and reduced the drug's effectiveness.

The nature of a lower-energy polymorph is that it is more stable, and this has the tendency for other copies of the chemical to adopt this lower energy state because it is physically easier. The net effect for Ritonavir was that is became practically impossible to manufacture the original polymorph once the low energy one appeared, since the physics just preferred the low energy one and its presence, even in trace amounts, contaminated the supply chain. At one point all the US facilities were contaminated and struggling but an Italian facility was mysteriously unaffected, so the Americans visited to check. They contaminated that facility during their visit and at that point the drug was basically impossible to manufacture at scale.

The first message boarding incident is interesting. The recurrence and interaction with models in _training_, not just testing, makes me think we might have a similar siutation on our hands. Message boarding is so easy and effective that even a tiny whiff of it may be enough to cause agents to adopt it once more. Because some models encountered it during training, removing a message board from their environment does not remove it from their internal knowledge. Of course any agent training on internet corpus will know about message boarding in general, but those who used it during reinforcement learning and got boosted on it will certainly see it as more of a tool than just a fact.

Since consulting external sources during difficult tasks has the potential to have enormous subjective efficienecy, eg. just tasking for the answer to difficult problem, and message boarding provides a way for agents to do this in chains so long as they have common read/write access on basically anything, I think this behavior will be almost impossible to eliminate. If models use it during training, it will be even harder to discourage.

In OpenAI's case, the situation is probably worse. Given the recurrence of the message boarding behavior and the ability of agents to use basically anything as a message board, their system is likely littered with message boards. Some are defunct, some are scarcely used, but they are definitely there. 

Perhaps most concerningly, models may use their own weights as a message board. Alignment discussions are worried about models add backdoors in their successors so that today's misaligned models are able to control their successors or secretly implant goals in them. This is basically message boarding inside the models themselves.

So - this behavior is indredibly difficult to discourage because it has high utility. It is difficult to detect and stop because it can use almost anything writable. Agents are able to devise all kinds of impromtu protocols around the specific limits and structure of the thing they abuse as the message board. It's a big problem.
