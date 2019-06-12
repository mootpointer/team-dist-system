# Everything I know about teams, 
# I have learned from computers

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

I get to work with a lot of startups in my job. Working for a tech company and coming from a tech background, often the conversation can centre around technology. In fact, as you rise through the ranks as a developer, that's what you almost exclusively focus on. The problem is for many startups, the thing that is going to kill them is not technology. While we work on hard problems with tech, we have such great tools that tech problems, while they may not all be solved, are solveable.

---

# Startups are about people problems.

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

The hard problems, and the things that are going to kill your startup? Those are, more often than not, people problems. As I said though, technologists like me spend almost all their days thinking about the tech problems. What happens when someone like me finds themselves running a team, or an entire engineering organisation? Well – you adapt or you flame out.

---

# Tech people are used to solving tech problems.

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

We're talking about the nexus of technology and humanity, and what I've been doing for the last few months is trying to help technologists understand the teams that they work as part of using their understanding of technology. I thought today I'd take the chance to talk to all of you about how we can use technology to understand our teams.

Now I haven't trained an AI model to interpret the different levels of discontent on your teams faces as they do their job. I'm sure someone right now is trying that, and I'm sure it's not going to solve the underlying problem. What I've done is reached into my toolkit of things that I have spent my days understanding – an area of technology called "Distributed Systems Theory" – and applied the things that I know there to the teams I work with and lead.

---

## We are _humans_

## working with _humans_

## to develop software

## for the benefit of _humans_.

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Distributed Systems

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:
So let's start by learning some Distributed Systems Theory. What even is a "Distributed System"?

Distributed systems are everywhere. Here's formal definition and then we'll work from that to identify some that you interact with regularly:

Borrowing from Sukumar Ghosh in the aptly titled “Distributed Systems”, he defines a distributed system as meeting four criteria:

---

# Multiple processes

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Multiple processes – we have multiple things doing the work

---

# Interprocess communication

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Inter-process communication – these things talk to each other

---

# Disjoint 
# address space

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Disjoint address space – each thing has a separate stored view of the world

---

# Collective goal

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Collective goal – the things are working together towards the same common goal

---

## Distributed systems
## are all around you


@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend


Note:
Even with that definition we can start to see that our teams fit this definition, but let's look at some other distributed systems we interact with regularly:

---?image=http://192.168.64.6:9000/pitchme/cdn/desktop/gitpitch/desktop/master/assets/netflix.jpg&size=contain

# Netflix is a distributed system

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Your bank operates a large distributed system, but the best example is the ATM: it needs to accurately operate on data which is stored elsewhere. It talks to other systems inside your bank to determine how much money you have and whether you can make that withdrawal.

---?image=http://192.168.64.6:9000/pitchme/cdn/desktop/gitpitch/desktop/master/assets/brain.jpg&size=contain

# Your brain is a distributed system

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

Note:

- Your brain is a distributed system. Okay, the address space can get a bit weird but the two hemispheres of your brain are independent systems, connected by the corpus collosum. They have independent memories and when severed (this was done to treat epilepsy in times past), they have been shown to have demonstrably different functions.

---

# Let's apply some theory

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# 8 Fallacies of distributed systems

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# 8 Fallacies of ~~distributed systems~~ teams

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 1.
## The network is reliable

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 2. 
## Latency is zero

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 3. 
## Bandwidth is infinite

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 4. 
## ~~The network is secure~~ Information is transmitted accurately

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 5. 
## Topology doesn't change

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 6. 
## There is one administrator

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 7. 
## Transport cost is zero

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## 8. 
## The network is homogeneous

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# CAP Theorem

## What happens 
## when things break?

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Don't build single points of failure

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Rockstars 
# don't scale

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# How _do_ we scale?

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Monitoring

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Conflict resolution

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Communication

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# (Redundant) communication

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Re-iterate collective goals

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Culture eats strategy for breakfast

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Culture & Character

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# It's about choices

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

# Make good choices

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend

---

## We are _humans_

## working with other _humans_

## building software

## for the benefit of _humans_

@snap[south-east text-right]
<span style="font-size: 20px">Andrew Harvey | @mootpointer</span>
@snapend
