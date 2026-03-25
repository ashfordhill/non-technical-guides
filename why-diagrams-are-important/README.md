# Why Diagrams Are Important

## Adapting to Modern Times

I used to hate diagrams and find them to be of limited value. They take time to make, there's different standards to follow. And when you make one, the audience who views them may show confusion or indifference.

However in the current age of AI, I'm finding that diagrams are more important than ever. My colleagues and I use generative tools to code more and more. Handwritten code and reading code line-by-line will be a thing of the past; in many ways it already is.

As software engineers, we adapt to this by thinking at a higher level. We need to understand the systems we are building from a bird's eye view. This is no longer just the responsibility of a software architect. 

## Communication Is Key 

Have you ever been in a meeting where technical terms, acronyms and passionate soapboxing is going on, and you have no idea what the hell everyone is talking about? Or maybe you *think* you and a colleague are both talking about apples, but after further discussion, you realize they're actually talking about pears!

![](./lost-in-translation.svg)

> A picture is worth 1,000 words!

Diagrams provide a great way to:

- Help verify everyone is on the same page with their understanding.
- Make talking about abstract technical concepts a lot easier.
- Help find potential redundancy or opportunities for more or less abstraction; sometimes seeing all the pieces together helps find smells or room for improvements.

Today, one of my colleagues presented his diagram of a system I have been confused about. He seemed to have a better understanding of what was going on than I did. I'd been nagging him to diagram and he was up for the challenge! It's a system with a lot of [unnecessary] abstraction, plus involved Kubernetes (which uses terms like Deployment, Pods, Service, Node, etc.). So talking about it can be kind of hard, especially for a team with 0 familiarity with Kubernetes. The visuals alone helped us all clarify questions:

![](./same-page.svg)

It was exciting to see how the discussion changed when there were visuals on the page. More questions were spawned and chained into discussion rabbit holes. The meeting ran over time, but the energy levels seemed to remain high and people stayed engaged.

## AI is Pushing Us to be Architects

![](./ai-makes-everything.svg)

Developers used to create solutions by hand, carefully writing each line. But now, we have tools to generate those solutions for us. The generative tools will *always* be faster.

Software engineers now need to move up an abstraction level. The questions are no longer "How will you make the bricks?" or "How many bricks can you make a day?". The questions now are "How will the bricks fit together? How do we verify the integrity of our bricks?".