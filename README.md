# AZ-900 Readiness Coach (Unofficial)

A free study aid for first-time Azure Fundamentals (AZ-900) learners, built for the #1MillionDevs Vibe Coding Hackathon. It combines a **Smart Quiz Builder** with a **Readiness Tracker**.

> **Unofficial.** Not affiliated with or endorsed by Microsoft. All questions are original and based on the public AZ-900 skills outline on Microsoft Learn. No real exam questions and no Microsoft logos are used.

## The problem

Learners practise with questions but don't understand why an answer is right or wrong, and can't tell when they're ready to sit the exam.

## What it does

- **Quiz by domain:** Cloud concepts, Azure architecture and services, Management and governance (30 original questions).
- **Instant feedback:** every answer explains why the right option is right and why the others are wrong, using African examples (M-Pesa traffic spikes, a Nairobi retailer's CapEx vs OpEx).
- **Readiness dashboard:** score per domain, weak-area list, and an overall rating (Not ready yet, Almost ready at 60%+, Ready at 80%+). Unanswered questions count as not yet correct.
- **Review my misses:** replays only the questions you last got wrong.
- **Explain it simpler:** asks Claude to re-explain the concept with a Kenyan everyday analogy.
- **Progress** is saved in the browser (`localStorage`). No account, no backend.

## Prompt design ("Explain it simpler")

The system prompt lives in `index.html` (constant `SYS`). Choices and why:

| Choice | Reason |
| --- | --- |
| Role and audience: tutor for a first-time learner in East Africa | Sets level and tone |
| Hard cap of 70 words, no bullets | Keeps answers readable on a phone |
| One everyday Kenyan analogy | Makes abstract cloud ideas concrete |
| Use only the vetted explanation provided | Grounding rule: the model rephrases, it doesn't add new technical claims, which protects accuracy |

The question, correct answer and vetted explanation are sent with each request. If the AI feature is unavailable, the quiz and dashboard still work.

## Run it

It's a single file. Open `index.html` in a browser, or host it on GitHub Pages (Settings, Pages, deploy from the main branch). The "Explain it simpler" button needs the Claude-powered runtime; on plain static hosting it shows a friendly message and the rest of the app works.

## Built with

Claude (claude.ai) for prompt design, question writing and code. Plain HTML, CSS and JavaScript.

## Roadmap

More questions per domain, a spaced-repetition flashcard mode, a study planner from exam date and weak areas, and question banks for AI-900 and AZ-104.
