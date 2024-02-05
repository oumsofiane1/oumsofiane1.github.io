---
layout: post
title:  "simplifying software systems"
date:   2024-01-30 19:33:11 -0800
categories: system architecture
youtubeId: IZWJpDHKOkI
---

Think about this scenario, your team inherits a large system, no one understands the business use cases they were built for, you and your team are tasked to simplify.
In this situation it is tempting to equate the simplification process with the reduction of subsystems. Fewer components mean less to manage, less to debug, and less to document. However, this process is not without its risks, key among these is the potential loss of business value. Every element of a software system ideally served a purpose; removing them without considering their contribution can inadvertently strip away functionalities vital to the system's value.

Beyond reducing the lines of code, and subsystems, there are often many aspects that contribute to complexity of software architecture:

## The power of naming

Names that are clear, consistent, descriptive can significantly simplify the understanding and maintenance of a system. Conversely, poor naming conventions can lead to confusion, errors, and a steeper learning curve for new developers.

## Diversity of architecture paradigms

I have seen this in the past, with teams starting initiatives to move from a monolith system to micro services, as the initiative wanes the system ends up somewhere in the middle with parts of it still in the monolith and parts in a whole new infrastructure. While this can be an acceptable in between step, teams should be aware of the added complexity that the interim period introduces.

I have also seen this with parts of a system using lambda architecture and some using micro-services hosted say on Kubernetes, while there are legitimate reasons to use one or the other, these choices will come at the cost of added complexity to be factored in.

## Technology stack multiplicity
 While embracing new technologies is crucial for innovation, it’s important to weigh this against the simplicity of the system. A diverse technology stack can lead to challenges in maintenance, onboarding and training new engineers.


Systems can't all be reduced and simplified, many complex systems are complex due to the complexity of the business needs they fulfill. However as software engineers we should keep striving for taming that complexity as much as we can.
