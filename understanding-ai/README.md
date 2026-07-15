# Understanding AI

> **Disclaimer**: This writing was mostly birthed by Fable 5 after I gave it a draft of thoughts I had while reading *The Infinity Machine* by Sebastian Mallaby. After some back and forth, I think it did a fantastic job. 

- [Understanding AI](#understanding-ai)
  - [Move 37](#move-37)
  - [Deep Learning vs. Reinforcement Learning](#deep-learning-vs-reinforcement-learning)
  - [Then Came the Chatbots](#then-came-the-chatbots)
  - [Safety? What of it?](#safety-what-of-it)
  - [The Smart-Sounding Idiots](#the-smart-sounding-idiots)
  - [For Today, Automate the Toil, Not the Engineer](#for-today-automate-the-toil-not-the-engineer)
  - [References](#references)

## Move 37

In March 2016, DeepMind's AlphaGo played Lee Sedol, an 18-time world champion, in a five-game match in Seoul. Something like **280 million people watched**. In game two, on the 37th move, AlphaGo placed a stone on the fifth line in a position that made professional commentators think the operator had misclicked. Lee Sedol got up and left the room. Fan Hui, the European champion who had already lost to the machine in private, said later:

> "It's not a human move. I've never seen a human play this move. So beautiful."

AlphaGo's own internal model estimated that a human professional had a 1-in-10,000 chance of playing that move. This wasn't a computer calculating faster than a human; chess engines had been doing that since Deep Blue beat Kasparov in 1997. It was a machine producing something we'd have to call creativity if a person did it, in a domain humans had studied intensely for 2,500 years.

Lee Sedol won exactly one game — game four, off a move so improbable it earned its own nickname, "God's touch." He retired from professional Go three years later, saying that AI "cannot be defeated." 

The people who built AlphaGo could not tell you why Move 37 was good. They built a thing that surprised them.

## Deep Learning and Reinforcement Learning

AlphaGo was not just reinforcement learning, and it wasn't just fed expert games either. It was three things stacked together: deep neural networks trained on ~30 million positions from human expert games (supervised deep learning), then improved by playing millions of games against itself (reinforcement learning), wrapped around a Monte Carlo tree search that let it efficiently look far ahead at future move possibilities (Silver et al., *Nature*, 2016).

Deep learning is pattern recognition: show a network a mountain of labeled data and it learns to map inputs to outputs. Reinforcement learning is different. There are no labels — just an agent, an environment, and a reward signal. The agent tries things, gets rewarded or punished, and learns a policy.

A year after beating Lee Sedol, DeepMind released AlphaGo Zero (Silver et al., *Nature*, 2017). This time, **it used no human data at all**. Blank slate, just the rules and self-play. It beat the version that beat Lee Sedol 100 games to 0. All of our accumulated Go knowledge — centuries of professional study, the proverbs, the joseki — turned out to be a handicap. The machine did better starting from nothing.

## Then Came the Chatbots

LLMs like GPT come from a different lineage: the transformer architecture (Vaswani et al., "Attention Is All You Need," 2017 — a Google paper, which Google then sat on while OpenAI ran with it). The recipe is simple to describe and strange that it works at all: train an enormous network to predict the next word on most of the internet, then use reinforcement learning from human feedback (Ouyang et al., 2022) so it behaves like a helpful assistant instead of a raw autocomplete.

ChatGPT launched in November 2022. It was not a research breakthrough. The underlying model had existed for months. It was a product — a chat window on top of GPT-3.5 — and it reached **100 million users in two months**. That product decision is what set off the current gold rush: the buzzword promotions, the "AI/ML Engineer" jobs, all of it. Mallaby documents how this played out inside DeepMind. Hassabis had deliberately kept comparable technology on a leash, and suddenly his employer was in a code-red panic to ship, because **a startup had decided the public beta *was* the safety test**.

That's the difference between Altman and Hassabis. Hassabis founded DeepMind in 2010 with the mission "solve intelligence, and then use that to solve everything else." When Google acquired the company in 2014, Hassabis made an ethics-and-safety review a condition of the sale. Mallaby describes him as haunted by Oppenheimer: he wants to be in the room precisely because **he believes the technology is dangerous enough that it matters who builds it**. Altman's talent is distribution and capital. He took a nonprofit founded explicitly to counterbalance DeepMind, restructured it around a capped-profit entity, partnered with Microsoft, and shipped. 

## Safety? What of it?

In May 2023, the Center for AI Safety published a one-sentence statement:

> "Mitigating the risk of extinction from AI should be a global priority alongside other societal-scale risks such as pandemics and nuclear war."

It was signed by Hassabis, Altman, Anthropic's Dario Amodei, and Geoffrey Hinton. Hinton is worth pausing on, because his fingerprints are on everything else in this writeup. In 1986 he co-authored the paper that popularized backpropagation (Rumelhart, Hinton & Williams, *Nature*, 1986) — the algorithm for training neural networks that AlphaGo, GPT, and AlphaFold all depend on. Hinton then spent decades defending neural networks through the years when most of the field considered them a dead end. In 2012, he and two of his students built AlexNet, the image-recognition system whose landslide win at that year's ImageNet competition convinced everyone else the approach worked and set off the modern deep learning boom. One of those students, Ilya Sutskever, went on to co-found OpenAI and serve as its chief scientist. Hinton isn't just a commentator; he is arguably the person most responsible for the current era. In 2023 he quit Google so he could speak freely about the technology, which **he now compares to raising a tiger cub**. He won the 2024 Nobel Prize in Physics for his foundational work and spent his acceptance press conference talking about its dangers.

The people closest to the technology are on the record saying it belongs in the same risk category as nuclear war. And then they all keep racing, because the game theory is merciless: if you slow down, the other lab doesn't, and you'd rather the careful people be in front. Mallaby is honest about this trap. The inventors believe they control the technology; often **the technology controls them.**

Meanwhile, the concrete near-term risk isn't a sci-fi robot uprising. It's biology. In 2022, researchers at Collaborations Pharmaceuticals inverted their drug-discovery model — the kind of tool that normally screens *out* toxicity — and it generated 40,000 candidate toxic molecules in under six hours, including VX analogues and novel compounds predicted to be worse (Urbina et al., *Nature Machine Intelligence*, 2022). The same capability that won Hassabis a Nobel Prize for AlphaFold — machine understanding of biology — lowers the barrier for the worst people on Earth. COVID-19 killed millions and rewired the global economy without being engineered to do either. Both Anthropic and OpenAI now publicly acknowledge that their frontier models are approaching thresholds where they meaningfully help with bioweapons development, which is why those models ship with extra safeguards. 

## The Smart-Sounding Idiots

The people who built the real breakthroughs spent decades on them. Hinton defended neural networks through **thirty years of ridicule**. Hassabis did a neuroscience PhD after his computer science degree because he believed you couldn't build intelligence without understanding it. The "AI experts" at most companies have spent, generously, a weekend with a framework that wraps an API that calls a model they couldn't explain even at the level of this essay. And the same shallow pattern — reward the confident vocabulary, skip the understanding — is how we're governing the technology, too. Congress asks CEOs to grade their own homework. Companies cut their safety teams when quarterly pressure hits. Society is doing to AI oversight exactly what many companies do to their org charts: promoting whoever sounds smartest in the meeting.

## For Today, Automate the Toil, Not the Engineer

Look at everything that AI is genuinely great at, and notice what the wins have in common: **the given task is well-scoped**. Go has fixed rules and a win condition. Protein folding has a measurable answer. Next-word prediction has a built-in training signal. Give a model a small, clearly defined task — write this function, port this file, add tests for this module — and it's remarkably good. Hand it something ambiguous and open-ended, and you get confident output aimed at the wrong target.

Decomposition is exactly what software organizations are bad at. Teams routinely fail to break high-volume, high-scope work into small, independently verifiable pieces — that's why estimates blow up, why epics roll over quarter after quarter, why the "simple migration" is on its third rewrite. Breaking ambiguous work into well-scoped pieces is the hard part of engineering, **it's a human skill**, and it's the bottleneck. If your team can't write a ticket precise enough for a new hire to execute without 3 clarifying meetings, it can't write one an AI can execute either. If you can't do an ambiguous task yourself, you're unlikely to automate it with AI.

So the opportunity isn't to automate the software engineer. It's to point the tools at the mountain of well-scoped work every team is drowning in and never gets to: the tech debt backlog, dependency upgrades, migrations, test coverage, flaky tests, documentation that lags the code, the deploy process everyone complains about. That work is precisely shaped for what the technology does well, and clearing it is what actually makes teams faster. The companies trying to replace engineers with AI have it backwards — they're handing the most ambiguous work to the tool that most needs ambiguity removed.

## OMG Will I Still Have a Job?!

This division of labor isn't a temporary limitation that the next model release will erase. Notice *how* models get better at coding: reinforcement learning against verifiable objectives — the code compiles or it doesn't, the tests pass or they don't. That's the AlphaGo recipe, and it works well because the reward signal is simple, fast and cheap. Go hands you a win/loss verdict in minutes; that's what made a million games of self-play possible. The outer loop of software has no such signal. "Was this the right system to build?" takes months, real users, and real money to answer, and the answer is noisy — plenty of well-built software fails for reasons that have nothing to do with the engineering. You can't run a million rollouts of shipping the wrong architecture and checking how the company feels in Q3. Ambiguity is also, at minimum, **an information problem** rather than an intelligence one: the missing requirements live in a stakeholder's head, in an unwritten org constraint, in what the customer meant but didn't say. No amount of training gives a model information it was never given. So expect the well-scoped frontier to keep expanding — and expect the job to keep shifting toward the part machines structurally can't do: deciding what to build, and cutting it into pieces that have verifiable answers.

## References

- Mallaby, S. *[The Infinity Machine: Demis Hassabis, DeepMind, and the Quest for Superintelligence](https://www.penguinrandomhouse.com/books/752231/the-infinity-machine-by-sebastian-mallaby/)* (Penguin Press, 2026)
- Rumelhart, D., Hinton, G. & Williams, R. ["Learning representations by back-propagating errors,"](https://www.nature.com/articles/323533a0) *Nature* 323 (1986) — backpropagation
- Krizhevsky, A., Sutskever, I. & Hinton, G. ["ImageNet Classification with Deep Convolutional Neural Networks,"](https://proceedings.neurips.cc/paper/2012/hash/c399862d3b9d6b76c8436e924a68c45b-Abstract.html) NeurIPS (2012) — AlexNet
- Silver, D. et al. ["Mastering the game of Go with deep neural networks and tree search,"](https://www.nature.com/articles/nature16961) *Nature* 529 (2016)
- Silver, D. et al. ["Mastering the game of Go without human knowledge,"](https://www.nature.com/articles/nature24270) *Nature* 550 (2017) — AlphaGo Zero
- Vaswani, A. et al. ["Attention Is All You Need,"](https://arxiv.org/abs/1706.03762) NeurIPS (2017)
- Ouyang, L. et al. ["Training language models to follow instructions with human feedback"](https://arxiv.org/abs/2203.02155) (2022) — RLHF/InstructGPT
- Urbina, F. et al. ["Dual use of artificial-intelligence-powered drug discovery,"](https://www.nature.com/articles/s42256-022-00465-9) *Nature Machine Intelligence* 4 (2022)
- Center for AI Safety, ["Statement on AI Risk"](https://www.safe.ai/work/statement-on-ai-risk) (May 2023)
- Jumper, J. et al. ["Highly accurate protein structure prediction with AlphaFold,"](https://www.nature.com/articles/s41586-021-03819-2) *Nature* 596 (2021)
- Moravec, H. *[Mind Children](https://www.hup.harvard.edu/books/9780674576186)* (Harvard University Press, 1988)

