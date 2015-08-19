# Large Scale Open Source Development Models
### A Comparative Analysis

<!--
abstract:
Managing an open source project with a small handful of developers is easy. But what happens when your project grows in popularity and you need to scale out your development model and tooling? Many projects have successfully made this leap with very different development models and tooling, so what is right for you? This talk will cover the development models of large projects such as the Linux Kernel, Apache Software Foundation, Debian and OpenStack, what worked, what didn't and what other projects can learn.

-->



<small>By Joe Gordon</small>

<!--


## About Me

* OpenStack Developer at HP
* Hacking on OpenStack for 4 years
* contact information
    * jogo on freenode
    *  [github.com/jogo](https://github.com/jogo)

-->

---

## Why

* Saw OpenStack grow from around 60 developers to over 2,100 developers
* Unusual development model
* But how do other projects solve the same problems?

---

# Why is Picking the Right Development Model Important?

---

## Accelerating Growth

* Time till 100 contributors
  * Linux: 1991 - 2 years
    * Linux 2.0 had 190 contributors in 1996  in credits
  * OpenStack: 2010 - 1 year
  * Docker: 2013 - several months
    * over 300 contributors in its first year
* 200 contributors per month
    * Linux: 1991 - June 2004 (13 years)
    * Debian: 1993 - March 2007 (14 years)
    * OpenStack: 2010 - October 2012 (2 years)


===

## Accelerating Growth

<small>Linux, Debian, Docker, OpenStack (clockwise from top left) <br/>
source: [openhub](https://www.openhub.net)</small><br/>
<img height=250 src="images/linux-contributors-per-month.png">
<img height=250 src="images/debian-contributors-per-month.png">
<img height=250 src="images/openstack-contributors-per-month.png">
<img height=250 src="images/docker-contributors-per-month.png">


---

## Open Source is Big Business

* Open source is the new standard bodies
* Balancing corporate interests

<img  src="images/linux-sponsors.png">
<small>Linux foundation Gold and Platinum Members</small>

---

## Picking the Right Development Model

### Conway's Law

>  organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations

<!--

At this point we should have painted a picture explaining that Large scale open source projects are:

* are big business and on the rise
* individual project are growing faster and faster

And picking the right development model (and governance, but governance is outside the scope of this presentation)  can make or break a project

-->

---

# Development Models

## Projects Covered

* Linux Kernel
* Apache Software Foundation
* Debian
* OpenStack
* Docker

<!--
All of them are building very different things. Differing degrees of cohesiveness in product.
-->

---

# [Linux Kernel](https://www.kernel.org/doc/Documentation/development-process/2.Process)

<img height=600 src="images/tux.png">
===

# [Linux Kernel](https://www.kernel.org/doc/Documentation/development-process/2.Process)

* Time based release
* 100-150 subsystem maintainers
    * Chain of trust
    * Decentralized review process
* Rolling development model

===

### Culture

* Chain of trust
* About the individual
* Value frankness over politeness
* Corporate friendly
* No single company controls
* Not much automated pre commit testing
    * Failing testing is very bad for author


---

# [Apache Software Foundation](https://www.apache.org/foundation/how-it-works.html)

<img  src="images/apache-feather.png">

===

# [Apache Software Foundation](https://www.apache.org/foundation/how-it-works.html)


* ASF is more of a governance umbrella and culture
* Separate projects
    * 4,400+ committers
    * 150+ top level projects
* flat (ish) trust model
* 'Review then commit' vs. 'commit then review'



    In order to reduce friction and allow for diversity to emerge, rather than forcing
    a monoculture from the top ... each project is delegated authority over development
    of its software, and is given a great deal of latitude in designing its own technical
    charter and its own governing rules.


===

### Culture

* Lazy consensus
* Focus is on the team
    * All decisions are team based
* Focus is on contributors not companies
* No monoculture

>   Within the ASF we worry about any community which centers around a few individuals who are working virtually uncontested.

---

# Debian


<img height=600  src="images/debian-logo.svg">

<!--
StevenK:

    I think the maintainers are both the biggest strength and greatest weakness of
    Debian.  Working together, we pull off some amazing things for a distribution of our size.
    And then you get the morons who don't want to update their packages, don't accept
    NMUs, and don't reply to bug reports.
    There is no centralized code review, or for lack of a better word,
    forced CI - the onus is on the maintainers rather than automated systems to ensure
    quality

-->

===

# Debian

* When its ready, not time based. Notoriously slow
* Package Maintainers: No review, trust maintainers more


<!--

FTP Master approved new package
Note:  Any Debian Developer can push a new version of a package but can cause trouble with the maintainer.

-->

<img height=450  src="images/debian-package-lifecycle.png">

===

### Culture

* Rotating leadership (elections)
* Do-ocracy: *An individual Developer may make any technical or nontechnical decision with regard to their own work*
* Open development
* Independent not 'profit-driven':  *no imposed decisions by who has money, infrastructure, people*
* *no benevolent dictator, no oligarchy*
* It is all about the individual (although individual's can form groups)
* Territorial

---


# OpenStack

<img  src="images/openstack-logo.png">


===

# OpenStack

* continuous delivery + stable releases
  * No rolling development
  <!-- freeze development on master before a release -->
* Break down into services and build teams around each service
    * 5,000 commits per month from 500 contributors
* Strong centralized review process (two core reviews per patch)
* Automated testing to reduce reviewer burden
* Having trouble with scaling the team responsible for a single repository
    *  Can't get past 15 or so members on a core team



===

<img  src="images/openstack-graph.png">

<!--
At first OpenStack was an 'integrated release' of several projects. But coordinating a single integrated release became harder as OpenStack grew. Moving to model of more loosely integrated components that have a less integrated release cycle.

Starting to evolve

-->

===

### Culture

* Group over individual
* Egalitarian
* Elections
* Welcoming to new contributors
* Corporate friendly
* Not controlled by single company
* Lazy consensus
* Decentralized design
* Uniform tooling/process across projects


===

### Culture

#### [OpenStack's 4 Opens](https://wiki.openstack.org/wiki/Open)

* Open *Source*, not open core
* Open *Design*
* Open *Development*
* Open *Community*
    * Lazy consensus
    * technical governance is a meritocracy
    * put everything in the public


===

### Factors Limiting Growth

* Cross project issues
* Team size
* Single vision

---

# [Docker](https://github.com/docker/docker/blob/master/MAINTAINERS)

<small>'Github' development model</small><br/>
<img  src="images/docker-logo.png">

===

# [Docker](https://github.com/docker/docker/blob/master/MAINTAINERS)

* Release every 2 months from stable branch (master isn't frozen)
* Scaling
    * split into multiple repos
    * Maintainers / subsystem maintainers
    * 35+ maintainers in Docker


    1) They share responsibility in the project's success.
    2) They have made a long-term, recurring time investment to improve the project.
    3) They spend that time doing whatever needs to be done, not necessarily what
    is the most interesting or fun."

    This "cellular division" is the primary mechanism for scaling maintenance of the
    project as it grows.

===

### BDFL

    Ideally, the BDFL role is like the Queen of England: awesome crown, but not
    an actual operational role day-to-day. The real job of a BDFL is to NEVER GO AWAY.
    ... the BDFL will always be there, preserving the philosophy and principles of the
    project, and keeping ultimate authority over its fate. This gives us great
    flexibility in experimenting with various governance models, knowing that we can
    always press the "reset" button without fear of fragmentation or deadlock. See the
    US congress for a counter-example.

    BDFL daily routine:

    * Is the project governance stuck in a deadlock or irreversibly fragmented?
        * If yes: refactor the project governance
    * Are there issues or conflicts escalated by core?
        * If yes: resolve them
    * Go back to polishing that crown.


===

### Culture

* Embraces the BDFL
* Open source
* Open design
* Docker the company dominates
    * Most of the maintainers are docker employees
* Automated testing
* *Be Nice* and *Encourage diversity and participation*

---

# Things to Consider for your own project

There is no one size fits all solution

---

## What Does *Open*  Even Mean?

<!-- What type of open source project will this be -->

* Open *Source*
* Open *Core*
* Open *Design*
* Open *Development*
* Open *Community*

---

## Tooling Considerations

* Bug tracking
* Review process
* Testing
* Barrier to entry for new contributors
  * DCO Developer vs. CLA
    * Developer Certificate of Origin
    * Contributor Licensing Agreement
  * Overall workflow

---
## Development Model Components
* Communication
* Team scaling model
    * chain of trust model
    * flat trust model
    * maintainers
* Release cadence
    * Stabilization periods
    * Rolling development
    * CI/CD
* Number of artifacts
* Decision making process -- Consensus model
* **Project culture**

---

## Problems Specific to Open Source

* BDFL
* Vision
* Managing competing interests
* Corporate
* Consensus model
* Trust and Ownership
    * Team vs individual
    * First come first serve?
    * How do you fire someone?

---

# Thank You
### Questions?
Slides can be found at [jogo.github.io](https://jogo.github.io)

Powered by [reveal.js](https://github.com/hakimel/reveal.js)

---


<!--
for next time.

* Add more conclusions, less time on each project. More comparisons.
    * How I would describe each project in a nutshell
    * Then go into comparisons on main points
* Conclusions
    * Individual vs group
    * Corporate
    * All projects are consensus driven, just different models
    * A few different 'trust' models
        * How pre commit automated testing impacts things
    * How they attract new developers
    * Core vs maintainer, vs committer etc.

-->
