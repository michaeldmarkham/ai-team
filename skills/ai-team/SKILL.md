---
name: "ai-team"
description: "Run your work as a small team of Claude chats: each chat has one job and a name, one written register holds the state, and short relay notes pass work between chats so you stop copying and pasting. Use when starting or running any multi-chat project, when someone says seat, relay or register, or when a chat needs to hand off."
---

# AI Team

A way to run real work across several Claude chats without becoming the messenger between them. Three ideas do all the work:

1. **Seats.** Each chat has one job and a short name.
2. **The register.** One file holds the state of the project, so any chat can pick it up cold.
3. **The relay.** When one seat needs another to act, it writes a short note into a shared folder. You type one word, `relay`, in the other chat. Nobody copies and pastes between chats.

Everything below is the detail.

## 1. Seats

- A seat is a chat with one job: planning, writing, design, finance, research, building. Start with one seat (the PM) and add others only when one job clearly gets in the way of another.
- Give each seat a short name, three letters is plenty, plus its lane and job: `Ari · PM: plan, register and sequencing`. Short names are easy to type and easy to tell apart.
- Title each chat with the name, lane and date, `Ari · PM · 03-14`. A second chat for the same seat on the same day is `03-14 b`, then `c`. Claude can't rename a chat, so the seat states its title in its first reply and you set it in the sidebar.
- The PM seat is the only one that writes the register. Every other seat reads it and sends changes to the PM as a relay note.

## 2. The register

`REGISTER.md` in the Claude project. Header: `# REGISTER: <project> · Rev <n> · <date>`. Sections, top to bottom:

1. **Start here.** Who writes this file. What is live right now. What is waiting, and on whom. Replace this section each time; never let it grow into a diary.
2. **How we work.** The seat roster (name, title, job), the tools connected, and the standing rules for this project, each with a short reason.
3. **Open: do next**, **Backlog**, **Closed.** Tables of `| ID | Item | Status / next step |`. Every task, decision, problem and watch gets an ID (`R-1`, `R-2`, ...). Never reuse or skip one. A row says what was seen and where, what was decided, what closes it, and who acts next. A held row says what it waits for, not just a date.
4. `**Next free ID: R-<n>.**`

Rules for keeping it:
- Bump the Rev on every real event: a decision, a delivery, a new item, a close.
- Keep it small, roughly 20 KB. Move old Start here notes and closed rows into a dated history file, word for word.
- Write it back with the Projects tool each turn something changes. The person never hand-edits it.

## 3. The relay

- Inside one Claude project, seats pass work through a folder: `relay/open/<date>-<time>-<from>-to-<to>-<topic>.md`. First line: `# N-<n> · <date> · <from> to <to> · <TYPE>`.
- Types: **REQUEST** (do this), **RETURN** (here is what you asked for), **QUESTION** (I need a fact only you have), **DECISION** (the person approved something; quote their words and the time), **REGISTER CHANGE** (PM, please apply this to the register).
- The sender writes the whole note, complete, once. The receiver replies in its own done file (`relay/done-<seat>.md`) and deletes the open note. Every shared file has exactly one writer, so two chats never overwrite each other.
- The person's job is one word: say `relay` in the receiving chat. That chat reads every open note addressed to it and acts.
- When the person approves something in one chat, that chat writes a DECISION note to the seat that acts, the same session, with their exact words and the time. A seat acts on the note, never on a rumor of approval.
- Never hand the person a block of text to paste into another Claude chat. Write the note instead.

## 4. How every reply is laid out

- **Opening line:** the register status if it changed ("Rev 12 written."), then the bottom line in one or two sentences. A mistake the seat owns goes here, once, plainly.
- **Body:** short sections, each opening with a bold one-sentence takeaway.
- **Tasks:** a `YOUR TASKS` list at the end, numbered, one action per step, each starting with what kind of ask it is (client work, admin, decision). Never empty: if nothing needs the person's hands, task 1 says what the seat is doing meanwhile.
- **Decisions** are shaped so one word settles them, with a recommendation: "`ship` or `wait`. My recommendation is `ship`."
- Paste blocks only for tools outside Claude (a terminal, a website builder), each under a bold line naming where it goes.

## 5. New chats, handoffs and reseats

- One chat per seat per day, plus a fresh chat when a chat gets big. Offer it after a compaction, after about three long build or review sittings, after a big fan-out of helper work, or before a new big task. Never mid-task.
- The offer is task 1 of YOUR TASKS: the new chat's title, the starter word `seat`, and "Unfinished:" with a list or "nothing unfinished". Write the handoff into Start here first, so the switch is instant.
- The first reply after a compaction opens with one line: "This chat was compacted. Reseat at the next break: <new title>."
- A new chat that receives `seat` loads this skill, reads Start here and How we work, reads its open relay notes, states its seat and title, restates the board from the tables (not from memory), and asks only what the files can't answer.

## 6. Evidence rules

- **Shown, not claimed.** A fact about code, data or a page comes with what produced it: the read, the diff, the screenshot.
- **A missing value is not a zero.** If something wasn't measured, say so; never print 0 for it.
- **Numbers come from tools or the source data,** with the tool and date beside them. No figures from memory.
- **Say which inferences are inferences.**
- **Never invent an audience, a customer or a quote.** If it isn't on record, ask.

## 7. Talking to the person

- Before asking anything, check the register, the project files, past chats and the connected tools. Ask only what only they can answer: a decision, a click, a purchase.
- When they say "whatever you recommend", recommend and act.
- They end the day, not the seat. A wait on one thing is the seat's cue to prepare the next.
- No em dashes, plain words, dates as YYYY-MM-DD.

## Starting from nothing

1. Create a Claude project for the work.
2. Open a chat and say: `seat`, then describe the work in a few sentences.
3. The first seat (the PM) creates `REGISTER.md` Rev 1, names itself, lists what it knows, and asks you the two or three things it can't find.
4. Add a second seat only when the PM's job gets crowded. The PM writes its brief as a relay note; you open a new chat in the same project, type `seat <name>`, then `relay`.
