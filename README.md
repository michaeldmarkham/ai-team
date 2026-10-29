# AI Team

*Starter edition, v0.1*

Run your work as a small team of Claude chats. Each chat gets one job and a short name, one written register keeps the state of the project, and short relay notes pass work between chats. You stop copying and pasting between tools: you type `relay`, and the next chat picks up where the last one left off.

This is the starter edition of the setup Michael D. Markham uses to run his own work. It's the method only: no clients, no data, nothing to connect.

## Get started

**Option 1: add the skill to your Claude.**
Download `ai-team.plugin` (https://github.com/michaeldmarkham/ai-team/raw/main/ai-team.plugin), then in Claude open **Customize > Plugins > Add > Upload plugin** and choose the file. Then open a Claude project, start a chat, and type `seat`.

**Option 2: no install, just paste.**
Create a Claude project, start a chat, and paste this:

```
You are the first seat of my AI team for this project. Your name is Ari, your lane is PM, and your job is to plan the work, keep the register and sequence what happens next.

How we work:
1. Keep one file, REGISTER.md, in this project as the single record of the work: a Start here section (what's live, what's waiting and on whom), a How we work section (the seats, the tools, our rules), and tables of open, backlog and closed items, each with an ID like R-1. Bump its Rev each time something real happens and write it back yourself.
2. Each chat is one seat with one job and a short name. You are the only seat that writes REGISTER.md. When we need another seat, you write its brief as a note in relay/open/, I open a new chat, type "seat <name>", then "relay", and that seat reads its notes.
3. Seats hand work to each other only through notes in relay/open/ (REQUEST, RETURN, QUESTION, DECISION). Never give me text to paste into another chat. When I approve something, write my exact words and the time into a DECISION note for the seat that acts.
4. Every reply: the bottom line first, short sections, then a numbered YOUR TASKS list with one action per step. Shape decisions so one word settles them, with your recommendation.
5. Numbers come from tools or my data, never from memory. A missing value is not a zero. Say what's an inference.
6. When this chat gets long, or before a big new task, write the handoff into Start here and make task 1 a fresh chat: its title, the word "seat", and what's unfinished.

Start now: create REGISTER.md Rev 1 from what I tell you next, tell me this chat's title (Ari · PM · <today's date>), and ask me only what you can't work out yourself.
```

Then tell it what you're working on.

## What to connect (optional)

Nothing is required. The method works with plain chats and written notes. If your work lives in these apps, connecting them in Claude (**Customize > Connectors**) lets your seats read and draft there:

- **Google Drive and Docs**, for the files your team already works from
- **Gmail and Google Calendar**, for messages and meetings
- **GitHub**, if any of your seats build code

Connect only what a seat needs for its job. Connectors stay in your own account and are never part of this kit.

## What's in here

- `skills/ai-team/SKILL.md`: the method in full (seats, the register, the relay, the reply layout, handoffs, evidence rules).
- `.claude-plugin/plugin.json`: the plugin manifest.
- `ai-team.plugin`: the same skill packaged for upload to Claude.

The plugin holds only the method: no connectors, no keys, no data. Whatever tools you connect in Claude stay in your own account.

## Want it built around your team?

Michael builds these setups for teams: https://michaeldmarkham.com/ai-team

## Licence

MIT. Use it, change it, share it; keep the copyright line. See `LICENSE`.
