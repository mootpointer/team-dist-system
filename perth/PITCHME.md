
# Your team as a distributed system

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
So I work for Microsoft as a "CTO in Residence". That's a fancy way to say that I get to spend my time helping out startups in various ways – generally engaging with their technical organisation. One thing I've found from talking to dozens of startups is that no matter what stack they're using: whether it's artisinal hand crafted VMs (which of course I counsel to move on from) or full-disaster kubernetes, there's one thing that concerns them most: people management.

---?image=assets/response_brick-2.png&size=contain

Note:
I've surveying startup CTOs and VPEs and asking them to rank their concerns – what they think about the most. The results are interesting. People management comes out on top, and deployment comes down the bottom. We talk a lot about deployment and operations and resilience, but underlying all of this is the people who are doing it. They underpin our ability to deliver on any of this.

---

aka.ms/startup-concerns

Note:
Now if you happen to be a startup CTO or VPE, or know one can I ask you to head here and fill in the survey. There are three questions and on average it takes people about three miniutes.

---

# Everything I know about teams, 
# I have learned from computers

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Whether you're in a startup, or a big company, most of the _real_ problems you'll face are people problems. Today we're going to take something of a new approach to these people problems and team dynamics. All of this is advice I normally give to startups, but having worked in startups and big companies, I can tell you – this kind of knowledge is useful wherever you are.

---

# Introductions

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Let me tell you a little bit about myself. For years I worked as a developer. I was an individual contributor – I had my time as that young, idealistic developer who railed against management and generally was a problem for my manager — I like to think I’ve matured a bit since then.

I’ve worked in big companies and small companies. Successful startups that ended up getting acquired, and less successful startups that went down in flames.

Somewhere along the way, I found myself running tech for a startup. At first it was just me, then me and a contractor, then all of a sudden I found myself managing a team.  I was out of my depth. I was no longer just able to sit and code. I was no longer only worried about the product, but about the team who were building it.

---

![Bill Lumbergh from Office Space holding a coffee cup](assets/lumbergh.jpg)

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
I had to ask myself, was I going to become this guy? I was no longer equipped, either from years of self-teaching or from any kind of formal education, in how to manage these people. 

I suspect this is not a new story for a lot of people here – maybe not in a startup, but maybe you got promoted in a corporate, or started a new role.

---

# The Peter Principle

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
The Peter Principle was first posited in the 60s and described as "People are promoted to the level of their incompetence". It's a common problem when your only way up in an engineering role is across to management.

There was a study last year which empirically proved the Peter Problem. It showed that in an organisation those people who had a greater level of sales aptitude indicators had lower levels 

---
@snap[north-west]
## The Peter Principle
@snapend


@snap[west span-50]
![graph of sales performance and promotion](assets/sales_promotion.jpeg)
@snapend

@snap[east span-50]
![graph of management indicators and sales performannce](assets/manager_sales.jpeg)
@snapend

@snap[south-west]
@size[18px](Source: voxeu.org/article/promotions-and-peter-principle)
@snapend


@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

@snap[north-west]
## The Peter Principle
@snapend

@snap[midpoint]
![graph of sales performance of actual managers](assets/manager_perf.jpeg)
@snapend

@snap[south-west]
@size[18px](Source: voxeu.org/article/promotions-and-peter-principle)
@snapend


@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# People don't throw stack traces.

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
People don’t throw stack traces or helpful error messages when things are going wrong. They often silently error while performance degrades until they SEGFAULT and leave suddenly.

Technologists on the whole don't have a great reputation for "playing well with others". Often we're given a free pass because we write weird things in weird text editors, but I don't think it's fair to us or the people we work with to allow us to ignore the dynamics of the teams we lead or that we work inside.

So today I thought we'd spend some times getting to know our teams and the dynamics within them using something near and dear to my heart.

---

# Defining Distributed Systems

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
At a conference like this we might already be familiar with distributed systems. The fact is they're all around us. Everything from PWAs to sprawling microservices architectures – we're dealing with the distribution of storage and processing and all its implications.

However, there's a few examples that maybe we don't acknowledge, and I want to take a quick sidebar here, because this one is super cool.

---?image=assets/brain.jpg&size=contain

# Your brain is a distributed system
aka.ms/brain-dist-system

@snap[south-west]
@size[18px](Andreashorn [CC BY-SA 4.0])

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
It turns out you brain is a distributed system as well. The red area in the middle here is the Corpus Callosum. It's the interface between the two hemispheres of the brain. There was a surgery which used to be popular for treating epilepsy, where this link was severed. Turns out that's like a netsplit for your brain, except it's not reverseable and STONITH is not an appropriate course of action. 

The surgery, while not very effective for curing epilepsy did teach us a lot about the brain. Look you came here for teams, not neuroscience, but if you're interested, you can check out a little blog post I've written about your brain being a distributed system here.

---

# Defining Distributed Systems

@ul[]
- Multiple processes
- Inter-process communication
- Disjoint address space
- Collective goal
@ulend

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Borrowing from Sukumar Ghosh in the aptly titled “Distributed Systems”, he defines a distributed system as having four properties.

 - Multiple processes – we have multiple people working on our product.
 - Inter-process communication – we at least hope that the people working on our product talk to each other
 - Disjoint address space – Each person has their own understanding of what they’re working on
 - Collective goal – hopefully we’re all working towards the same thing.

---

# 8 Fallacies of a Distributed System

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
So if we can all agree that at least by this definition your team is indeed a distributed system – even if they’re all in the same office. Are we roughly agreed on that? Okay, let’s test this out by trying out some of what we know about distributed computing on our team.

One of my favourites is the 8 fallacies of distributed computing. It originally came out of Sun Microsystems and describes the false assumptions that programmers inevitably bring to a distributed system. In our case, it’s the false assumptions that we can bring to our teams as we scale them. Hopefully we can learn some things that we can apply to the 

---

## 1. The Network is Reliable

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
On a network you can’t assume that every message sent is received, or within a reasonable time frame.

Similarly with people, not everything you or someone else says will be heard. Not every email you send will be thoroughly read. Some instant messages will get lost in the mass of notifications.

Even with the best teams, our communication is not 100% reliable. This is even more more true when you’re scaling your team. In the midst of the scaling, things get lost. They get missed.

We need to build our teams knowing all of this, and compensating for it. We need to choose the right mediums for the right messages. Sometimes it means we have to be a bit more like TCP – overly chatty, but you know when you've been heard.

---

## 2. Latency is Zero

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
If you've ever waited for a reply to an email, or a reply to an instant message, or even for someone to finish a task then you've experienced working latency.

Sometimes this doesn't matter. Sometimes it means that work gets blocked. Sometimes it means than conflicting work gets done.

It is our responsibility to manage this latency in a distributed system. The same is true in our teams. We have to design things such that the impact of latency is mitigated. We have to have ways of raising up an exception if someone is deadlocked or otherwise in a stuck state.

---

## 3. Bandwidth is infinite

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
There is a limit to how much we can do at once. We're all painfully aware of this fact. Our backlogs and overflowing todo lists are a testament to this fact. However, that's not what we're talking about here.

What we're talking about is that no matter how hard I try, the communication bandwidth between you and I is finite. This is compounded by media. So in a 1-to-1 interaction, I have the best chance of conveying my whole message quickly.

But when we use lower bandwidth media the impact is compounded. With video chat, some of the nuance is lost. If we choose audio only you don't even get my facial expressions. With email and instant message where most of the nuance and context is lost.

Less is communicated and so more is inferred and that can be problematic.

We have to understand the implications of lower bandwidth and made tradeoffs. We're trading convenience for clarity and speed.

---

## 4. ~~The Network is Secure~~ Information is Transmitted Accurately

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
We're going to assume for the moment that all your team are acting with the best intentions. If you can't assume that, then there are some big issues you need to address. For that reason, I've twiddled with this fallacy from the traditional set.

What we can't assume is that we are receiving the intended message of someone's communication. We all come with our own context and assumptions. If you've ever played a game of "Telephone" then you know this to be true.

That means two things – we need to truly rely on the assumption that everyone is trying their best. Otherwise when we miscommunicate (and we *will* miscommunicate) things go downhill fast. The second is that we need to make sure we have communicated what we think we have communicated, and conversely we need to make sure that people have said what we think they have said.

---

## 5. Topology Doesn't Change

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
As our company grows, our structures necessarily must change. The structures which serve us with a team of five will fail us with fifteen and those that work at 15 will fail at 50.

We need to be aware of this and intentional about the way we scale. Suddenly middle management will be required - you will need to scale out into different teams and as you scale that will look different.

---

## 6. There is One Administrator

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
As you scale your topology you're also going to find that there is no longer a single owner for a piece of work or functionality. There are multiple stakeholders and that needs to managed. Consensus building is required to move forward.

Consensus protocols are hard with distributed systems. They're just as hard with humans. A lot of our roles as we lead teams and grow them is not making the decisions, it's helping come together and make decisions together.

---

## 7. Transport Cost is Zero

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
All of this has overheads. Communication has costs. That doesn't mean it's not worthwhile, but it needs to be acknowledged. It should influence the way we structure our teams. We should set people up in groups optimised to balance the cost of communication with having enough people to get the job done.

There's a classic mathematics problem called the handshake problem. If every person in a group were to shake hands with every other person in that group once, how many handshakes need to take place?

For two people, that's one handshake; for three people, three handshakes; four people, six handshakes; ten people, fourty five handshakes; one hundred people? Four thousand, nine hundred and fifty hand shakes. It gets ou of hand pretty quickly. That's because it's an exponential equation.

Communication is worthwhile though. Just because it has cost doesn't make it bad. It just means we need to structure to manage that overhead.

---

## 8. The Network is Homogeneous

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
As you start out, the people involved in a startup are likely quite similar. They will tend to be very mission driven and deeply engaged. As you grow, you are going to have people that are motivated by different things. They will have different ideas. They will have different desires, and their reasons for working for you will be different.

They should have different backgrounds, different perspectives, different communities, different experiences. This should be treated as a feature, not a bug. A more diverse team has, according to research, a higher cumulative IQ than a homogeneous one.

But these differences are going to complicate communication. They are going to lead to misunderstandings. People are going to mess up.

It is worth it though, but it needs to be managed to make it work. Getting this right early – having a heterogenous team earlier and managing it well – is going to make your team better, and it's going to make scaling out better.

---

# CAP Theorem

@ul
 - Consistency
 - Availability
 - Partition Tolerance
@ulend

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
All this thinking got me to one of the first things I learned when starting to dabble with distributed systems: CAP theorem. Now the CAP theorem can get pretty hairy, pretty quickly but I want to do a quick introduction because it's going to help us to understand how we manage our growing teams.

In a distributed system you have three things which you can trade between. It's classic "take two" situation. We trade off between Consistency, Availability and Partition tolerance.

Our systems are then a tradeoff between these three.

The funny thing is there's one option which is a non-starter:

---

## Single Point of Failure

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
In distributed systems, this is not seen as an option. A resilient distributed system must be partition tolerant. That means the loss of a node, or any network operation does not stop the system from functioning.

However, more often than we'd like to admit, we end up constructing teams with single points of failure within them. It might be us as CTO or VPE. It might be a principal engineer. It might be your rockstar developer.

---

## Rearchitect your monolith
@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
If you're relying on a rockstar developer, what you're building is a monolith. Don't build a monolith. It will not scale with you over the long term, and we're in this for the long term right?

---

## Rockstars don't scale.

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Let's put this another way: Rockstars don't scale. They create a single point of failure and ultimately will be a drag on your team. The trick is to transition them from being a rockstar to a team-player. That's not an easy path, and it isn't always going to work, but to scale up, you need to let go of your monolith.

---

## Consistency vs Availability

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
There are two other types of systems described by CAP theorem. CP and AP systems, that prioritise consistency and availability respectively. Now this is kind of a false dichotomy – you don't have to choose all of one and none of the other. It's all about tradeoffs. It's about making the right tradeoffs in the right places.

Maybe in some parts of your team, you want to prioritise availability – that you'll always be able to keep moving forward, even if you develop a little bit of inconsistency (so long as that is eventually resolved). Maybe in other parts, consistency is essential, so you'd rather not move forward without everyone onboard.

---

## Consistency vs Availability

![cosmos](https://anharveypresfiles.blob.core.windows.net/anharvey-presfiles/cosmos.mp4)

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
We have a service in Azure called CosmosDB. It's *super-cool*. It's a globaly replicated document database. It is the embodiment of a distributed system and it even embodies these tradeoffs. You can decide that consistency is critical, so throw more throughput at it and have latency effects, or you can decide that eventual consistency is sufficient for your needs, saving money and having lower latency.

That what we have to do as we grow our teams: make tradeoffs. Decide what is most important and then communicate those priorities to those involved.

---

# How do we scale our teams?

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
So given all that, how do we scale our teams? What are the practical things we have to do?

Much like distributed systems, there are some things that we know we're going to need.

---

## Monitoring

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
We have to monitor the health of our teams. We need to identify fault conditions and remediate quickly. That requires us to have our finger on the pulse. Ask questions of your team and of yourself. Are you making the right tradeoffs? Do your team know where they're going? Can they articulate the what, how and why of what they're doing?

This is where one-on-one meetings with your team members become essential. As you grow, the cadence of them will change, and you will rely more on team-leads and managers, but you should make sure a culture of communication and time dedicated to discussing issues as they arise and working to resolve them exists.

---

## Conflict Resolution

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
 Like any distributed system, we need some way of dealing with conflict. Inconsistent state is inevitable. People have different backgrounds, perspectives, experiences, opinions... They come at things from different directions...

 That means you need to need to manage conflicts. We need to get people on the same page and bring them back there when things get weird. We can't be afraid of conflict – if we run away from it or bury it, it will fester and what might have been a slight divergence becomes a rift which we can never merge.

 A lot of this is about providing a place of psychological safety – where it is okay to be wrong. Where getting there together is more important than being right, more important than being the smartest person in the room. While you as a leader are ultimately responsible you want your team to be able to help bring things back together again.

---

## Communication

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
In order to scale, people need to be able to make good decisions independently. To make good decisions independently we need context. That requires us to communicate as much context as we can.

That means we need to be as transparent as possible about what's going on and why we're doing things. That helps keep everyone on the same page, and it helps people intuit where they should be focusing their effort.

Communication has costs. It will take up your time and energy being transparent rather than attempting to operate in a command-and-control fashion. It will pay off. 

---

## (Redundant) Communication

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
I have two slides on communication. That seems a bit redundant. It is!

Sometimes you can feel like you're repeating yourself, but people miss things. It is better to over-communicate than undercommunicate, and I tell you what I have very rarely seen people actually manage to over-communicate. If you have something you really want your team to hear, and you feel like you've said it too many times – say it once more, just to be sure.

So I'm going to say it once more, just to be sure. Explain the "what", the "how" and most importantly the "why" to your team. Within reason, communicate what it is that is concerning you – the things that are driving you.

Use tools like OKRs and to help your team on track, but always come back to the "why". Then come back again.

---

## Clarity of Roles

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Have you ever found yourself in the kitchen, preparing food for a family dinner? You're there, chopping vegetables. Around you, other family members are working on their part of the dinner. One person making a salad, another seasoning the roast. Another cleaning up some dishes. Everyone working together, and separately.

You finish cutting the carrots, and you look around. Suddenly you find yourself in the way. Suddenly people seem to be constantly running into you. What changed from one moment to the next?

Your role in the kitchen became unclear – your goal in the kitchen became unclear. We map out our actions *in relation to other people's goals*. We anticipate other people's movement and actions based on what we understand their goals to be. If we don't know what they're trying to do, then we don't know how to negotiate our way around them.

---

## Clarity of Roles

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
The same happens in a team. I not only need to understand what I'm doing as an individual and my goals, so that I can be successful, but I also need to understand what others are doing around me and their goals. Otherwise we're going to trip over each other.

Simultaneously, when it's not clear who is leading a particular task, that ambiguity can lead to conflict. Make sure your team is clear.

---

## Re-Iterate Collective Goals

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
Just as important as individual goals and roles are the collective goals of your whole team, and any sub-teams you have within that. It is key to re-iterate these goals, including the reasoning behind them, at every possible opportunity. It is easy – especially for technical teams – to get bogged down in details or individual work. It is our job as leaders to keep everyone's eyes on the collective goals of our teams and company as a whole.

---

## Culture eats strategy for breakfast

@snap[text-right]
- Peter Drucker
@snapend

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
What it all comes down to is the thing that will set your team up to grow successfully is culture. You can do the spotify model or two pizza teams or whatever else is hip these days, but your culture will be the driving force for your success.

Culture is bigger than strategy. Culture will make or break your strategy because in the end, if things go big, they'll scale beyond your individual control. People will have to make decisions and have interactions unmediated by you, and the thing that will mediate them will be the culture you have established.

---

## Culture & Character

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
The best definition I've seen for culture is that is the collective character of a group. Our character seeps out through every pore and so does our culture. We can work on our character, just like we can work on our culture, but our character underlies our action – just as our culture does.

---

## It's about choices

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
When it comes down to it, our culture is not built by having "culture and values" sessions, or a spiffy slide deck (although these can be helpful to communicate some of the ideas). Culture is built through the decisions we make.

To borrow from a friend of mine, Jenny Herald: culture is who we hire. It is who we hire. It is the behaviours we reprimand and those we reward. It is the hard calls we make because they are the right thing to do, even if there is a more expedient way.

---
@snap[north-west]
## Our culture is defined by:
@snapend
@snap[east]
### Who we *hire*,
### who we *fire*,
### behaviours we *reward*,
### and those we *reprimand*.
@snapend

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## Make Good Choices

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
So my advice to you in growing your teams? Build a culture that welcomes a diverse set of people into your team and helps them thrive. Make choices that might be hard at the time but pay off over the long term.

Communicate where you're going, how you're getting there and why you're on the journey at all.

There so many parts to scaling a team, but if you can get these two, you're well on your way.

---

# Thank You

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend
