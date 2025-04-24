---
title: "Distilling Giants: Making BERT Models Lightweight and Interpretable with DIET COKE"
seoTitle: "Distilling Giants: Making BERT Models Lightweight with DIET COKE"
seoDescription: "Learn about DIET COKE: distilling BERT models into lightweight, interpretable forms with decision trees for efficiency and transparency"
datePublished: Thu Apr 24 2025 09:00:27 GMT+0000 (Coordinated Universal Time)
cuid: cm9v4u54g000o09jp4hwtcsuu
slug: distilling-giants-making-bert-models-lightweight-and-interpretable-with-diet-coke
tags: nlp, decisiontree, knowledge, edgecomputing, transformers, bert, edge-ai

---

This past semester, I embarked on an exciting NLP project: building [**DIET COKE**](https://github.com/velocitatem/diet-coke) — short for **Decision trees Interpreting Efficient Transformers - Compression Of Knowledge Extraction**. It's a project that sits at the crossroads of deep learning and classic machine learning, blending the sophistication of transformers with the simplicity and transparency of decision trees.

In essence, DIET COKE is a pipeline that distills the knowledge of a heavyweight BERT model into lightweight, interpretable models like decision trees, random forests, or linear classifiers — models that are fast, transparent, and, crucially, can run without needing a data center in your backpack.

## Why Even Bother Distilling?

Large models like BERT are brilliant — but also notoriously impractical outside of cloud servers. They are slow, expensive, opaque, and massive. Great if you're Google. Not great if you're deploying to a Raspberry Pi in a rural village or trying to explain your model's prediction to a non-technical client.

The idea behind DIET COKE is simple: **take the wisdom of a large model, and compress it into a small one**. Think of it as writing a pocket guidebook based on a Nobel Prize winner’s 600-page dissertation. You lose a little nuance, but keep most of the real-world value.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745421970553/a4e89d65-8677-428f-b6ed-9b1efcf6a24e.png align="center")

## What’s Inside the DIET COKE Pipeline?

The project is structured with the kind of modular, end-to-end design I love (and insist on building). Here’s the high-level flow:

* **Train the Teacher**: Fine-tune a BERT model on IMDB movie reviews for sentiment classification.
    
* **Soft Targets and Temperature Scaling**: Instead of teaching the student from hard labels ("positive" or "negative"), we use the teacher’s soft probability outputs (logits) — softened even further with temperature scaling to better reveal hidden patterns.
    
* **Vectorize the Text**: Since our student models can’t eat raw text, we use good old TF-IDF to turn movie reviews into sparse, meaningful feature vectors.
    
* **Train the Student**: Train a simple model (like a decision tree) to imitate the teacher's nuanced outputs.
    
* **Evaluate and Benchmark**: Compare not just on raw accuracy, but on **fidelity** — how well the student mimics the teacher.
    

## The Magic of Distillation: Teaching by Uncertainty

One of the coolest parts of this project was diving deep into temperature scaling. At a high temperature (say, 4 or 5), the teacher’s output probabilities become softer — meaning that even "wrong" answers get some probability mass.

This subtle information about **what the model thinks might also be true** is pure gold when teaching smaller models. It lets the student not just memorize labels, but **inherit the teacher’s worldview**.

It’s the difference between:

* Telling a kid "2 + 2 = 4", full stop, versus
    
* Teaching them *why* "2 + 2 = 4" but also explaining how addition works for any numbers.
    

In knowledge distillation, **temperature** controls how much uncertainty the teacher model reveals to the student. Higher temperatures soften the teacher's predictions, exposing richer secondary patterns beyond the top choice. This often boosts **fidelity** — the student’s ability to mimic the teacher's behavior — but can slightly lower **raw accuracy** on hard labels. In contrast, lower temperatures sharpen predictions, favoring accuracy but at the cost of losing some of the teacher's deeper knowledge. Finding the right balance between fidelity and accuracy is key to building student models that are both smart and practical.

## When to Use Which Student Model?

After extensive experiments, here's the quick cheat-sheet:

| Model | Best For | Pros | Cons |
| --- | --- | --- | --- |
| Decision Tree | Explainability | Easy to visualize and interpret | Lower accuracy |
| Random Forest | Best accuracy | Robust, close to BERT performance | Less interpretable |
| Sparse Linear | Edge devices | Tiny models, fast | Needs careful feature tuning |

Temperature settings? A sweet spot is usually T=4 for softer distributions, but T=2 works surprisingly well if you're targeting more accuracy over fidelity.

## Final Thoughts: Why DIET COKE Matters

**DIET COKE** isn’t just an academic exercise. It’s a blueprint for the future of *practical* AI: how we can compress enormous models into smaller, understandable pieces that still capture most of the power, without the computational footprint.

In a world increasingly moving toward edge computing, decentralized apps, and explainable AI, pipelines like DIET COKE aren’t just nice-to-haves — they’re the future.

If you're curious, you can dive into the repo and experiment with different configurations, tweak temperatures, or even distill other transformer models. There's a lot of frontier here.

**Big brains compressed into small, fast, human-friendly models.**  
That's a future I’m excited to build toward.

If you have any questions or thoughts, feel free to reach out via my website: [alves.world](https://alves.world)