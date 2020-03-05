# Business plan Liberate Science
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

This business plan is written both as a visioning exercise (future tense) and updated subsequently with what has happened (past tense). This is a living document. Versions of it may be stored at various snapshot dates to allow for evaluation of how the business plan evolves. The document provides a product analysis, a community analysis, and yearly plans.

## Vision

This is the future we'd like to see and what motivates us to do this work. The vision should stay relatively fixed over time, although wording and emphasis may change, and it is used to guide our decision making.

### For science
We want a publication process that empowers researchers to do great science. Science that is accessible to everyone, free for all to participate in. All research can be published, free from publication bias, time-consuming bureaucracy and centralised control. The research process is transparent from the start. Working together and building on each other's work is easy and free from restrictions.

### For work
We provide workers with more agency, energy, money, and time to act on their beliefs. This creates a truly healthy and empowered work environment that is open, democratic and beneficial to workers, without being harmful to others or the planet.

## Mission

This is what we do to work towards our vision. This may change over time, as we discover that there are more effective ways to achieve our goals. The mission, like the vision, acts as a compass, but is more flexible. It is what we live day to day right now, but might not be exactly what we live day to day by next year.

### For science
We build tools that enable researchers to focus on what matters most, their research, while upholding important open science principles by design. We raise awareness to issues arising from the current publication system and build a community interested in actively improving this system.

### For work
While working on our research tools, we live the changes we want to see in the workplace by developing an *open worker co-operative* organisation model and applying it to our own work. We improve the model along the way, learning from our own experiences as an open worker co-op.

Fundamental organisational changes:
- all workers have one vote, electing who manages
- 7-hour workdays or 4-day workweeks 
- uniform base pay for members, variable pay to incentivize unwanted tasks
- direct budgetary profit sharing

## Background

Provenance in projects can be a pain, especially when we collaborate with various people, for large projects, and also for projects of various nature (e.g., research, music production, journalism). Git provides a way to collaborate on large projects with people, but the usability makes it limited to projects of a relatively specific nature. We want to build a tool that makes managing projects and their provenance easy by breaking down large projects into its smaller components. Moreover, by sharing all these components publicly and permissively, we allow us to reduce the redundancy in our work by seeing what our peers are doing. This might help inspire us and facilitate more collaborations. 

Large projects without provenance, shared rarely and if so under restrictive licensing, reduce the creative space of the people working in it and reduce the verifiability of outputs. The products outlined in this document aim to fundamentally alter these dynamics, by ensuring all building blocks are allowed to be reused, and these blocks are communicated continuously, as close as possible to when they are produced.

## Products

Liberate Science produces public digital project management, evaluation, and planning tools for creative, chronological, verifiable processes that require clear provenance of information (e.g., for research, journalism). 

The products are non-rivalrous (i.e., not zero-sum), non-local (i.e., can be consumed anywhere), one off (i.e., not subscription based), and are mostly simple (i.e., no custom products or pricing). The products stack together, building on the previous layers. Other product stacks may be built using the first layer, by other organizations. Green blocks have revenue potential.

![](./assets/product-stack.png)

See also the [dependency chart](https://raw.githubusercontent.com/libscie/business-plan/master/assets/dependency-chart.png) for an overview of relations between our products and external products.

## Product 0: 🍐-to-🍐 commons

The peer-to-peer (aka 🍐-to-🍐) commons framework ([p2pcommons](https://github.com/p2pcommons)) is a set of opinionated, minimum, and flexible specifications to create a commons infrastructure for all chronological, stepwise, creative projects. This forms the basis for our Hypergraph product and is intended for developers both inside and outside the organisation.

The design for this commons infrastructure originated from redesigning scholarly communication (see also [here](https://doi.org/10.3390/publications6020021) and [here](https://doi.org/10.3390/publications7020040)), but can be generalized to any iterative, creative, collaborative process (e.g., journalism, music production, book writing) that values provenance. The main added value is that all steps are chronologically communicated and link and that the commons infrastructure lives on the peer-to-peer protocol Dat.

The specifications aim to formalize both the minimum specifications for a communicable unit on the commons (i.e., a module), plus the storage and indexation on a device (for interoperability purposes). The range of specifications may be extended over time, but the values underlying it are that they provide a stable commons infrastructure upon which to build applications. Software Development Kits that are implemented in accordance with the specifications are provided for application development.

## Product 1: Hypergraph

[Hypergraph](https://github.com/hypergraph-xyz) is our set of publication tools that empowers researchers to do great science. Hypergraph intends to reduce friction in the research process, while promoting modular *as-you-go* publication and ensuring open access and participation, clear provenance and decentralised control. 

Hypergraph (i.e., a [a graph of graphs](https://en.wikipedia.org/wiki/Hypergraph)) will be the first application to utilize the 🍐-to-🍐 commons (Product 0). Hypergraph allows people to start interfacing with this commons in order to consume and produce modules. There will be various instances of the Hypergraph application (command line, desktop, mobile, web). 

These various instances of the Hypergraph application will run on a common development scheme, for example, where `v1.0.0` will provide the same core functionality. That means that if all instances are at the same major version, they have the same functionality. In practice, that’ll mean that the CLI is likely to be the highest version (e.g., v1.0.0), the desktop lagging behind (e.g., v0.9.0) and the mobile application lagging behind that (e.g., v0.4.0). This also makes sense, because the CLI incorporates only the functionality, but the desktop application needs to build a design around it. The mobile application is something that is on the wishlist but may take longer due to porting of the Dat protocol. Given the psychological value of having full versions for people’s perception of stability (and not sticking in beta for forever), we'll be using the semver versioning scheme and operate in the `v0.x.x` space until we implement our feature requirements and get everything stable enough. Subsequently we bump to `v1.0.0`, regardless of where we are (e.g., `v0.6.4` might be bumped to `v1.0.0`).

## Product 2: Hypergraph Vault

Hypergraph Vault is our publication and archival service for Hypergraph that provides researchers with a cheap, central location to have their work stored safely, available forever and findable by others.

The work includes building a database instance to store the contents of the Vault, a Docker container to deploy for server rehosting based on that database, and integrating a payment process into Hypergraph using [Stripe](https://stripe.com/en-de/payments) to add modules to the database. Modules MAY be in the Vault if people choose so, but it is not a necessity; Hypergraph will implement this as a requirement for publication of content modules. The added value is persistent availability and findability (the Vault is immediately searchable in Hypergraph by default). In order to get a module in the centralized Vault, a small fee must be paid; 1EUR (assuming this is proportional to module size and the corresponding running costs).

Product 2 also allows the organization to gain experience in integrating payment infrastructures (e.g., Stripe API, bookkeeping, paying international VAT). This is a simple product and provides a stepping stone towards more complex and larger payments in Product 3; this also serves as a clear counterweight to the Article Processing Charges (APCs) of large publishing houses exceeding hundreds or thousands of dollars (see for example [here](https://peerj.com/preprints/27809/)).

## Product 3: Network analyses

Our network analyses will provide a powerful and more specific alternative to traditional "impact" metrics for scientific publications. By providing answers to specific network-related questions regarding a particular researcher or publication, these results will be better tailored to the enquirer's needs than traditional metrics. We hope this will allow researchers to direct more of their attention to doing great research.

On Hypergraph, most modules will be created as a follow-up to a previous module, creating a(n acyclic) network of consecutive modules. This structure opens up the biggest revenue possibility: Providing Hypergraph users prepared substantive questions to analyse the network on. These analyses can focus on how the network looks at that time point (i.e. evaluative) or how the network might change in the future based on how they proceed with the project (i.e., planning).

![](./assets/dag.png)

Liberate Science produces added value with a range of off-the-shelf substantive questions and their respective indicators, that may be of interest to the user. We provide compute services for when these computations become too complex to reasonably run on user’s personal devices. The complexity may increase due to both the size of the network, the complexity of the indicator to be calculated, or an interaction between the two. Buying the compute service is a convenience product, where the user gets answers to their substantive questions within a more reasonable timeframe (e.g., 4 days instead of 4 years).

The revenue model for these network analyses is progressive, because users can try out all the functionality on their own machine for non-complex computations, providing them with tangible value that may nudge them into asking more complex questions over time. Users are guided along a decision tree to come to their substantive question of interest.    

## Product 4: Custom network analyses

The substantive questions provided in Product 3 will continuously be developed, refined, and extended upon, but there may always be substantive questions that people or organizations want answered and are not part of the off-the-shelf offering. Liberate Science will provide a consulting process to help clients formulate their substantive question of interest, translate that to a (set of) indicators, and provide the computations.

Subsequently, these custom network analyses will feed back into Product 3, becoming available as off-the-shelf analyses. This means that the Product 4 clients are in effect paying for Liberate Science’s product development.

## Community & awareness

## Open worker co-operative

## Risks and other points of attention
Our [vision](#vision) is leading. Therefore, we must evaluate our effectivity by measuring progress towards this vision. Are researchers interested in our products? And do our products, when used, have the intended effect? What assumptions are we making regarding our target user group and how do we check these assumptions? How do we prepare the world for our product, as well as preparing our product for the world?

When doing this, we must not be too invested in the specifics of the great ideas we have and remain aware of our own human biases. We must actively seek out collaboration and empower those interested in our work. We must be ready to admit our own mistakes and pivot when necessary.

As our vision is quite broad, but our resources are limited, we will need to take a step-by-step approach to development. We set a minimum viable product that provides the base value, and start the co-design process with the community we're trying to serve. We  set up our MVPs and subsequent releases to be big learning opportunities. We set milestones to provide clear direction and focus.

To ensure continuity of the project, we need to secure our funding and make sure our organisation isn't too reliant on specific individual workers. Along the way, we will need to verify whether our revenue models are working and will provide sufficient income to continue our work. We will provide public financials for community members to inspect and to keep ourselves accountable towards the community.

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://chjh.nl"><img src="https://avatars0.githubusercontent.com/u/2946344?v=4" width="100px;" alt=""/><br /><sub><b>Chris Hartgerink</b></sub></a><br /><a href="#business-chartgerink" title="Business development">💼</a> <a href="#content-chartgerink" title="Content">🖋</a> <a href="#fundingFinding-chartgerink" title="Funding Finding">🔍</a> <a href="#ideas-chartgerink" title="Ideas, Planning, & Feedback">🤔</a></td>
    <td align="center"><a href="https://github.com/jameslibscie"><img src="https://avatars2.githubusercontent.com/u/59870484?v=4" width="100px;" alt=""/><br /><sub><b>James Lomas</b></sub></a><br /><a href="#content-jameslibscie" title="Content">🖋</a> <a href="#ideas-jameslibscie" title="Ideas, Planning, & Feedback">🤔</a> <a href="#projectManagement-jameslibscie" title="Project Management">📆</a></td>
    <td align="center"><a href="http://dpaez.github.io/"><img src="https://avatars0.githubusercontent.com/u/837500?v=4" width="100px;" alt=""/><br /><sub><b>Diego</b></sub></a><br /><a href="#ideas-dpaez" title="Ideas, Planning, & Feedback">🤔</a></td>
    <td align="center"><a href="http://twitter.com/juliangruber/"><img src="https://avatars2.githubusercontent.com/u/10247?v=4" width="100px;" alt=""/><br /><sub><b>Julian Gruber</b></sub></a><br /><a href="#ideas-juliangruber" title="Ideas, Planning, & Feedback">🤔</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!