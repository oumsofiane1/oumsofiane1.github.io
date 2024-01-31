---
layout: post
title:  "simplifying software systems"
date:   2024-01-30 19:33:11 -0800
categories: system architecture
youtubeId: IZWJpDHKOkI
---

Think about this situation, a software engineering team inherits a large system, the business use cases where these systems are used aren't all fleshed out, you and your team are tasked to simplify.
Commonly, in this situation it is tempting to equate the simplification process with the reduction of nodes within a system. At first glance, this seems logical; fewer nodes typically mean fewer subsystems to consider, leading to a seemingly simpler structure. However, this perspective can be misleading. While it's true that deprecating outdated code paths and removing subsystems lacking in business value is a good starting point, it's crucial to maintain the equilibrium between simplification and the value that the software delivers.

Fewer components mean there's less to manage, less to debug, and less to document. However, this process is not without its risks. Key among these is the potential loss of business value. Every element of a software system ideally serves a purpose; removing them without considering their contribution can inadvertently strip away functionalities vital to the system's value. Simplification shouldn't be done at the expense of business value.

Beyond reducing the lines of code, and subsystems, there are often many aspects that contribute to complexity of software architecture:
## The power of naming

Names that are clear, consistent, descriptive can significantly simplify the understanding and maintenance of a system. Conversely, poor naming conventions can lead to confusion, errors, and a steeper learning curve for new developers joining the project.

## Diversity of architecture paradigms

I have seen this in the past, with teams starting initiatives to move from a monolith system to micro services, as the initiative wanes the system ends up somewhere in the middle with parts of it still in the monolith and parts in a whole new infrastructure. While this can be an acceptable step in between, teams should be aware of the added complexity that the interim period introduces.
I have also seen this with parts of a system using lambda architecture and some using micro-services hosted say on Kubernetes, while there are legitimate reasons to use one or the other, these choices will come at the cost of added complexity to be factored in.

## Technology stack multiplicity
 While embracing new technologies is crucial for innovation, it’s important to weigh this against the simplicity of the system. A diverse technology stack can lead to challenges in maintenance, onboarding and training new engineers.
