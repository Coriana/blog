---
layout: post
title: "Hallucinations in LLMs: A Side Effect of Being Trained to Be Right"
date: 2025-04-14 18:00:00 +0800
---
## What if being right is at the cost of being honest?

I've been thinking a lot about hallucinations in large language models lately, and I have a theory: they’re not just a quirk of imperfect training data or model size. They might actually be caused by instruction tuning - specifically, by how we train these models to always provide correct answers.

At first glance, that might sound counterintuitive. How could trying to make a model more accurate lead to it hallucinating? But here’s how I see it.

When we prompt a model to give us the correct answer - for example, by asking “Who is the President of France?” - we reinforce its ability to give a plausible-sounding response, regardless of whether it actually learned that fact during its original training. If the model didn’t actually absorb that Macron is President, but we force it to say so during instruction tuning, we’re teaching it to generate plausible facts rather than recall true knowledge.

## So how do we fix that?

One method I’m exploring is based on a concept called Self Prompting, which has been discussed in research papers. The idea is to prompt a base model with a blank slate, or the beginning of how a question is asked, but no content and let it ask itself questions, organically exploring what it knows about the world. In typical training data, questions are often followed by answers, so models learn to follow up their own queries with self-generated responses.

This process allows us to fine-tune a model based on its internal logic rather than imposing external answers. Since most instruction tuning only touches a subset of the model’s layers, this mismatch between surface-level answers and deeper knowledge can become problematic. We’re updating the output, but not the internal representation - and that’s where hallucinations come in.

Put simply: we’re teaching it to say the right thing, not necessarily to know the right thing.

That’s the heart of my theory. Hallucinations emerge when we update the model’s answers without updating its underlying knowledge. If, instead, we let the model create its own internal dataset - asking questions, correcting itself, refining its beliefs - we can build something more grounded and reliable.

This thinking was heavily inspired by Anthropic’s interpretability research, particularly their “brain scan” work. They found that certain internal representations do exist, but when the model encounters a familiar name or object, it often overrides that deeper structure with default responses - a kind of pattern-matching reflex.

To build better models, we need to accept that sometimes the model doesn’t know the answer. And that’s okay.

What we don’t want is for the model to guess when it’s unsure. That’s how you get hallucinations. Maybe what we really need is a way for the model to say, “I don’t know.” An internal flag that lights up when the confidence isn’t there. Paired with an internal BS detector, we could get something that’s not just smart, but also honest.

Of course, there’s a balancing act. Push too hard in that direction, and instruction tuning breaks that honesty. It starts forcing confident answers even when none should exist.

And that, I think, is where many of our hallucination problems are really coming from.

---

References:

[Self-Prompting Large Language Models for Zero-Shot Open-Domain QA](https://arxiv.org/abs/2212.08635)

[Reasoning models don't always say what they think](https://www.anthropic.com/research/reasoning-models-dont-say-think)

[Tracing the thoughts of a large language model](https://www.anthropic.com/news/tracing-thoughts-language-model)


---
Transcribed and cleaned up from audio by AI.