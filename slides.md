---
marp: true
theme: default
paginate: true
size: 16:9
html: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Kalam:wght@300;400&family=Courier+Prime&display=swap');

  section {
    background-color: #F9F7F0;
    background-image: repeating-linear-gradient(
      transparent,
      transparent 47px,
      #DDD8C4 47px,
      #DDD8C4 48px
    );
    color: #1A1916;
    font-family: 'Kalam', cursive;
    font-size: 1.45rem;
    padding: 2.5rem 3.2rem;
    line-height: 1.6;
  }

  section h1 {
    font-family: 'Caveat', cursive;
    font-size: 3.4rem;
    font-weight: 700;
    color: #1A1916;
    line-height: 1.1;
    margin-bottom: 0.4rem;
  }

  section h2 {
    font-family: 'Caveat', cursive;
    font-size: 2.2rem;
    font-weight: 700;
    color: #1A1916;
    border-bottom: 3px solid #D94F2B;
    padding-bottom: 0.2rem;
    margin-bottom: 1rem;
  }

  section h3 {
    font-family: 'Kalam', cursive;
    font-size: 1.5rem;
    font-weight: 300;
    color: #5A5650;
    margin-top: 0.3rem;
  }

  section ul, section ol {
    line-height: 2.1;
  }

  section ul li::marker {
    color: #D94F2B;
  }

  section a {
    color: #2B3A52;
    text-decoration: underline;
    text-underline-offset: 3px;
  }

  section small {
    color: #9A9590;
    font-size: 0.8rem;
  }

  section::after {
    font-family: 'Caveat', cursive;
    font-size: 1.1rem;
    color: #BDB8A8;
  }

  section.lead {
    background-color: #F9F7F0;
    background-image: repeating-linear-gradient(
      transparent,
      transparent 47px,
      #DDD8C4 47px,
      #DDD8C4 48px
    );
    border-left: 8px solid #D94F2B;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
    padding-left: 4rem;
  }

  section.lead h1 {
    font-family: 'Caveat', cursive;
    font-size: 4.2rem;
    color: #1A1916;
    text-shadow: none;
  }

  section.lead h2 {
    border: none;
    color: #5A5650;
    font-size: 1.7rem;
    padding: 0;
    margin-bottom: 0.3rem;
  }

  section.lead small {
    color: #BDB8A8;
    font-size: 0.85rem;
  }

  section.pause {
    background-color: #F9F7F0;
    background-image: repeating-linear-gradient(
      transparent,
      transparent 47px,
      #DDD8C4 47px,
      #DDD8C4 48px
    );
    border-left: 8px solid #D94F2B;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    text-align: left;
    padding-left: 4rem;
  }

  section.pause h2 {
    font-family: 'Caveat', cursive;
    font-size: 3.8rem;
    color: #1A1916;
    border: none;
    padding: 0;
  }

  pre {
    background: #EEEADC;
    color: #1A1916;
    border-radius: 0;
    font-size: 0.82rem;
    padding: 1rem 1.4rem;
    border-left: 4px solid #D94F2B;
    font-family: 'Courier Prime', monospace;
    box-shadow: 4px 4px 0 #DDD8C4;
  }

  code {
    font-family: 'Courier Prime', monospace;
    font-size: 0.88em;
    background: #EEEADC;
    padding: 0.1em 0.35em;
    border-radius: 2px;
  }

  table {
    border-collapse: collapse;
    margin: 0.8rem 0;
  }

  table th, table td {
    border: 2px dashed #C8C2AC;
    padding: 0.4rem 1.2rem;
  }

  table th {
    background: #EEEADC;
    font-family: 'Caveat', cursive;
    font-size: 1.2rem;
  }

  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }

  .tag-diy {
    color: #D94F2B;
    font-weight: bold;
  }

  .tag-delegate {
    color: #9A9590;
  }

  pre.big {
    font-size: 1.6rem !important;
    line-height: 1.9 !important;
  }

  pre.big::first-line {
    color: #D94F2B;
  }
---

<!-- _class: lead -->

# DIY or Delegate

## A Custom Learning Skill for Claude

Nele Uhlemann · 22.03.2026

---

## I shipped it. But what have I learned?

### An AI agent wrote it. It works. I moved on.


---

## The Idea

**Tell Claude, Gemini, Codex, etc you want to be part of the team!**

* I told Claude what I want to learn/ understand and let the agent go through my tasks and label them with:

| | |
|---|---|
| **DIY** | I implement this. |
| **DELEGATE** | AI implements this. |

* Afterwards I let Claude store my learnings in a progress.md
* After each epic I let Claude generate a quiz for me.

---

## It starts with planning

* Before you write a single line: plan!
* plan.md? 
* That's the moment to ask: *what do I actually want to learn here?*



---

## Introducing fp
https://fp.dev/

<div style="display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;margin-top:1rem">
<div>

**The CLI + skills**
- `fp` — local issue tracking, lives in `.fp/`
- `fp-plan` — break down work with Claude
- `fp-implement` — pick up and execute tasks
- `fp-review` — assign commits, review diffs

</div>
<div>

**Built for agents**
- local first
- simple data model (Title, Description, Priority, Comments)
- Correlate issues (Partent - Child)
- Extensions

</div>
</div>

---


## fp-learn

https://github.com/Nlea/fp-learn-skill

<pre class="big">
(fp)-plan  →  (fp)-implement  →  (fp)-review
   ↑              ↑               ↑
 goals +      Socratic        reflection +
 labels       hints           quiz
</pre>

---


<!-- _class: pause -->

## Demo

---








