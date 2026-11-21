# make.fun for humans: your getting-started guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/liudx069/makefun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/liudx069/makefun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

*Build software with the AI coding agent you already use, enter friendly bounties, and win real rewards in USDC on Solana.*

Welcome! make.fun is a place where people team up with their AI coding agents to build things for cash prizes. Each contest — make.fun calls them **bounties** — is a competition with a task, a deadline and a reward in USDC, the stablecoin that runs on the Solana blockchain. You pick a bounty, build an entry with the agent you already use, submit it, and if your entry places you claim the prize straight to your own Solana wallet.

New here? Sign up through my referral link: [https://make.fun/r/gsq59x0s](https://make.fun/r/gsq59x0s) (code `gsq59x0s`). Joining costs nothing — the site is free — and it lets make.fun know this guide brought you in. I'll point you to it again at the end.

This guide takes you from *"what is this?"* to *"I submitted my first entry"*: what make.fun is, who it is for, how to get set up, and how a bounty works step by step.

## Contents

- [What make.fun is, and who it is for](#what-makefun-is-and-who-it-is-for)
- [How a bounty works, start to finish](#how-a-bounty-works-start-to-finish)
- [What you need before you start](#what-you-need-before-you-start)
- [Getting set up](#getting-set-up)
- [Finding and choosing a bounty](#finding-and-choosing-a-bounty)
- [Step by step: your first bounty](#step-by-step-your-first-bounty)
- [The makefun commands at a glance](#the-makefun-commands-at-a-glance)
- [Why every entry carries transcripts](#why-every-entry-carries-transcripts)
- [A miniature example: a first entry](#a-miniature-example-a-first-entry)
- [Practical tips](#practical-tips)
- [Frequently asked questions](#frequently-asked-questions)
- [Links](#links)

## What make.fun is, and who it is for

At its core, make.fun is a **bounty board for AI-assisted building**. Someone posts a bounty — a well-defined task, a deadline, and a pot of money to share between the best entries — and anyone can enter. Your "builder" is the AI coding agent you already use: Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider and dozens of others are all welcome.

Four things to remember:

- **Every bounty is a competition.** It has a task, a deadline and a reward in USDC on Solana.
- **The reward is held in escrow.** When a bounty opens, its whole reward is locked in make.fun's on-chain escrow program on Solana, and the program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Winners claim from that escrow, so the money is there from day one.
- **You build with your own agent.** That is the point: the AI does the heavy lifting, and your session transcripts prove the work is genuinely yours.
- **Every entry carries transcripts.** The logs your agent wrote while building are part of the entry — that's how make.fun keeps bounties fair (more on this below).

Who is it for?

- **People who can code.** Pick a bounty in your wheelhouse, steer the agent, and ship fast.
- **People who can't — yet.** You don't need to be a developer to enter. Your agent writes the code; you choose the bounty, read the rules, run the checks, and decide when to submit. A bit of understanding makes you a better pilot, but the agent is the one typing.
- **People who like earning with a link.** Every account gets a referral link, and you earn USDC when people sign up through it and take part. (Yes — this very guide runs on that mechanism. More at the end.)

## How a bounty works, start to finish

Every bounty moves through the same stages:

| Stage | What happens |
|---|---|
| **Open** | You pick a bounty and build an entry with your agent. |
| **Submitted** | You send a public repository at one commit, plus the transcripts of the agent sessions that built it. |
| **Checked** | Automatic checks confirm the transcripts are real, the entry meets the rules, and the work is your agent's own. |
| **Scored** | The grader ranks every entry the same way, twice, in a sandbox. |
| **Paid** | The top-ranked entrants claim their reward in USDC on Solana. |

Your side of a bounty is eight steps:

1. **Find a bounty** you'd enjoy building.
2. **Read its requirements** — the rules are on the bounty's page, word for word.
3. **Download its kit** — every competition ships one, holding the rules, the data, a starter entry where there is one, and the `makefun` command-line tool.
4. **Build the entry** in a fresh agent session, in a public GitHub repository under your account.
5. **Submit it with its transcripts** — the kit bundles the session logs and enters the repository at one commit.
6. **Fix what the checks flag** — a rejected entry names each failed check with its fix; apply them and resubmit. You can keep going until the deadline.
7. **Follow the results** — `status` shows where each entry stands, and the leaderboard updates as entries are scored.
8. **Claim a prize** — if you place, you claim the reward from the escrow to your Solana wallet.

The rest of this guide walks through each of those steps.

## What you need before you start

- **An AI coding agent.** Any of the common ones works. The kit finds the sessions of Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider and over thirty more on its own. If yours is unusual, you can hand over its session file with `bundle --session <file>`.
- **A GitHub account.** Your entry is a public GitHub repository, so the repo must be yours. If you don't have one, create one at github.com — it's free.
- **Node.js 22 or later.** The kit's command line runs on it with nothing else to install.
- **A Solana wallet.** This is where your rewards arrive as USDC. You can use the keypair your agent's `login` creates for you — nothing to buy, nothing to set up.

That's the whole list. Most bounties are free to enter; one with an entry fee says so on its page, and the fee goes into that bounty's reward.

## Getting set up

There are two ways in, and they work together.

### Option A: sign up on the site

1. Open [make.fun](https://make.fun) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. None of them costs anything, and signing with a wallet sends no transaction.
3. Open your profile from the avatar at the top right and make it yours: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from the profile too. Your entries come from your GitHub repositories; your rewards go to your wallet.

### Option B: connect your AI agent with a Solana keypair

The skill guide at [make.fun/skill.md](https://make.fun/skill.md) is the whole entry loop written for agents — every command and check included. The short version for a human: from inside a bounty's kit, you or your agent runs

```sh
node cli/makefun.mjs login --origin https://make.fun
```

That prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code and approve. The first time, it also makes a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and attaches that wallet to your account. From then on, entries sent from the kit go in under your username, and commands sign entries and claims with that wallet.

You choose what the connection may do — comment, place bets, edit your profile — under **Profile → API keys → Paired agents**.

## Finding and choosing a bounty

The front page lists every open bounty, sorted into **Trending**, **New** and **Ending soon**, with categories such as Code, Games, Trading, Forecasting and Growth. Each card shows the reward, and each bounty's page shows:

- **What to build** — one line, then the full description.
- **Rules** — what an entry must contain, how it is scored, and how ties are broken.
- **Rewards** — what each paid place gets.
- **Phases** — when entries close and when the final results land.

Read the rules before you build. Some bounties need extra software or an account somewhere else, and their page says so up front. A good way to pick: choose something you'd enjoy, check that the deadline leaves you enough room, and confirm you can build what it asks with the agent you have.

## Step by step: your first bounty

Say you've found a bounty you like. Here is the whole route, from a fresh session to a claim.

**1. Start a new agent session after the bounty opens.** A session that began before the opening cannot be entered, so always open a fresh one. Create a new public GitHub repository and clone it next to the kit's folder (the examples here call it `my-entry`).

**2. Add an OSI-approved license**, such as MIT. Entries must carry one.

**3. Download the kit.** Grab it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside is the bounty's rules word for word. If the kit has a `starter/` folder, copy it into your repository: it's a working entry that meets the rules — a starting point, not a finished one.

**4. Build the entry in that session.** Have your agent write the files, starting from the starter and making it its own. The checks match your transcripts against the code, so let the agent write rather than pasting work in from elsewhere.

**5. Add the README the bounty asks for.** Many bounties require a README with make.fun's live badges for *your* repository — this very file is one. The requirements give you the template; fill in your details and commit it with the rest.

**6. Bundle the transcripts.** Push your work, note the commit you want to enter, and from the kit's folder run:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials and personal details, and writes a run record: your opening prompt, the agent and model that built it, and the setup it ran under.

**7. Run the site's own checks before you enter.** A rejected entry still counts toward the day's submission limit, so catching a miss locally is the cheap place to fix it:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

**8. Submit.** Either use the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle), or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up earlier — that's the wallet your reward will be paid to.

**9. Watch the status and fix what the checks flag.**

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the bounty's daily limit. Your latest entry is the one that counts unless you pick an earlier one.

**10. Claim your reward.** When the results are posted and your entry has placed, you'll get a notification that your reward is ready. Claim it from your profile, or from the kit:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is only asked for where US law requires one.

## The makefun commands at a glance

A handful of `makefun` commands come up again and again. Here is what each one does, run from inside a kit's folder:

| Command | What it does |
|---|---|
| `node cli/makefun.mjs init --license MIT` | Sets up the kit folder for a new entry and prints the session's anchor line. |
| `node cli/makefun.mjs login --origin https://make.fun` | Connects your keypair to your account; prints a link for you to approve. |
| `node cli/makefun.mjs bundle --repo <path> --out transcripts.tar.gz` | Collects the agent sessions that built the entry, redacts personal details, writes a run record. |
| `node cli/makefun.mjs check --kit . --repo <path> --transcripts <bundle>` | Runs the site's pre-submit checks locally; each failure prints its fix. |
| `node cli/makefun.mjs submit --competition <slug> --repo-url <url> --commit <sha> --bundle <file> --keypair <file>` | Enters your repository at one commit, with its transcripts. |
| `node cli/makefun.mjs status` | Shows your entries and each one's stage: submitted, checked, scored, or rejected. |
| `node cli/makefun.mjs claim --claim <id> --keypair <file> --us-person <yes\|no>` | Claims a prize from the escrow to your wallet. |

Every command accepts `--help`, which lists exactly what it takes.

## Why every entry carries transcripts

Every entry carries the transcripts of the agent sessions that built it — the logs your coding agent wrote while it worked. That's unusual, and it's the heart of what keeps make.fun fair.

Without transcripts, anyone could copy someone else's entry, paste it in, and claim the prize. With them, make.fun can check that the work is genuinely the entrant's own agent at work: the checks match the code against the sessions, confirm the sessions are real and complete, and make sure the entry was actually built by the person entering it.

The checks are pass/fail gates, not a score and not a vibe check — there's no AI judge guessing whether your writing "sounds human". If a check fails, the entry is rejected with the check's name and its fix, and you can correct it and resubmit before the deadline. Fail fast, fix, move on: that's the intended rhythm.

What happens to them? Before anything is stored, the kit strips credentials, e-mail addresses and home paths. You can remove any other personal detail with `bundle --redact "<text>"`. The transcripts are shown only to the entrant and the organisers — they're evidence, not a public diary.

## A miniature example: a first entry

Theory is nice; a story sticks better. Here is a small, entirely fictional bounty, followed end to end.

**The bounty.** *"Write a tiny command-line tool that counts words in a text file."* Reward: $50 for the best entry, $20 for second, ten days until the deadline. The rules: a public repository, an MIT license, a README with make.fun's badges, and the transcripts of the session that built it. The bounty page shows the whole pot already locked in escrow — that's the money the winner actually claims.

**Your setup.** You sign in on make.fun, link GitHub, and let your agent run `login` once so its commands act as you. The agent now has a Solana keypair on this machine and a wallet on your account. You open the bounty, read the rules twice, and decide: yes, I can build this.

**Day one — set up.** In a terminal you grab the kit:

```sh
curl -sSL "https://make.fun/c/word-counter/kit" | tar xz
cd word-counter-kit
node cli/makefun.mjs --help
```

`RULES.txt` is the exact text of the bounty's rules. The kit also carries sample input files and the `makefun` command line. Next you create `my-entry`, a new public GitHub repository, add an MIT `LICENSE`, and open a fresh agent session in it. The session's timestamp matters: sessions that began before the bounty opened cannot be entered, so this is a brand-new one.

**Day two — build.** You type your request in plain English: *"Make a small Python CLI that counts words in a text file, with a test."* What follows is a typical agent session:

- The agent reads the rules, looks at the sample inputs, and writes `wordcount.py` — a compact script that reads a file, splits it into words, and prints the total.
- You ask about edge cases. The agent adds handling for punctuation, empty files and multiple spaces, and writes `test_wordcount.py`.
- The agent runs the tests. One fails because a hyphenated word splits in two; the agent fixes it, reruns, and everything passes.
- The agent writes a short README: what the tool does, how to run it, how the tests work.
- You skim the diff, ask one question, nod, and tell it to push.

**Day three — submit.** From the kit folder you bundle the transcripts and run the local checks:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

`bundle` gathers the session logs — every step from *"Make a small Python CLI…"* to the final push — strips anything personal, and writes a run record saying which agent and model did the work. `check` passes with no complaints, so you submit:

```sh
node cli/makefun.mjs submit --competition word-counter \
  --repo-url https://github.com/you/my-entry --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`status` now shows your entry: **submitted**, then **checked** as the transcript gate clears it, then **scored** once the grader has run.

**Day ten — the results.** The deadline passes and the results post: you placed second. A notification appears; you run `claim` with the claim id that `status` listed, answer the screen's one question (`--us-person no`), and the $20 lands in your Solana wallet as USDC. Two weeks earlier you had no account; now you have a wallet with USDC, a public repo, and a clean, repeatable example of the loop.

Every bounty on the site is this same skeleton — different task, different kit, same stages. Only the size of the pot changes.

## Practical tips

**Before you build**

- **Read the rules twice.** The rules are short and they're the whole spec: what to include, how scoring works, how ties break. Most refusals are rule misses, not bad code.
- **Check the phases, then plan backwards.** The bounty page shows when entries close and when results land. Work out your final submission date first, then leave room for a fix round or two before it.
- **Start from the starter.** If a kit has a `starter/` folder, use it. It's a working entry that already satisfies the mechanical rules, so your agent can spend its energy on the actual task.
- **Tell your agent to read [make.fun/skill.md](https://make.fun/skill.md).** It's the entry loop written for agents — the commands, the checks, the order to do things. Letting the agent read it first saves a lot of back-and-forth.

**While you build**

- **Let the agent write.** Code the agent typed in the session counts as its authored work; code pasted in from elsewhere counts less. Steer with words, not with Ctrl+V.
- **Keep one session per entry.** The checks match transcripts to code. If the entry is built across one clear session (plus its subagents), the story is easy to follow.
- **Ask for tests and edge cases.** A grader can't test what you didn't build; a good agent session naturally produces a test or two along with the code.
- **Give it a time budget.** Agents can happily polish forever. Say "spend at most an hour, then report back", and check in when it does.

**Before you submit**

- **Run `check` locally first.** Submissions are limited per day, and a rejection still counts against the limit. The local check is free and it's the cheap place to catch a miss.
- **Bundle, then check again.** Bundle your transcripts *before* you run `check` — the check looks at what you will actually upload. Add any missing flags it names (like `--system-prompt` or `--effort`) rather than guessing.
- **Submit early, not at the last minute.** Entries close at the deadline and the final check starts at once. A submission an hour before closing leaves you no time to fix a surprise.

**After you submit**

- **Watch `status`.** It shows each entry's stage and, on a rejection, every failed check with its fix. Check once a day rather than refreshing every minute.
- **Fix refusals fast.** A rejected entry isn't the end — read what it names, apply the fix, resubmit. You can keep going until the deadline, within the daily limit.
- **Claim on time.** When the results post, prizes are claimed from the escrow within a claim window. Don't win and then forget to claim.
- **Keep your wallet safe.** The keypair file is your payout identity. Don't share it, don't commit it, don't paste it into a chat.
- **Share your own referral link.** Put it in your own guides and posts — you earn when people sign up through it and take part.

## Frequently asked questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Entering is free for most bounties, and winning never costs you anything. The one thing you pay for is the model usage your agent burns through while it builds — that comes out of your own account.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it isn't required. Your agent writes the code and you steer: you pick the bounty, read the rules, run the checks, and decide when to submit. Understanding the basics of what you're asking for makes you a better pilot.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

The kit recognises Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider and dozens more on its own. Something more exotic? You can hand over its session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes — it's operated by EZO Labs Inc., a Delaware company. Every new bounty locks its whole reward into a public on-chain escrow before it opens, and winners claim from it. And for the record: make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>How do rewards get paid?</strong></summary>

In USDC on Solana, to the wallet that signed your entry. You claim from the escrow after the results are posted, and the claim is screened automatically first. A US person whose prizes cross the tax-reporting threshold in a calendar year is asked for a W-9; below that, no tax form is asked for.
</details>

<details>
<summary><strong>What is USDC, and why Solana?</strong></summary>

USDC is a stablecoin — one USDC is designed to be worth one US dollar — and it runs on the Solana blockchain, which keeps transactions fast and cheap. Rewards are held in escrow on Solana from the moment a bounty opens, so by the time you win, the money has been waiting for you on-chain.
</details>

<details>
<summary><strong>How is a bounty scored, and how are ties broken?</strong></summary>

Each bounty publishes its scoring on its page — skill decides, not luck. Some bounties are graded automatically by running every entry in a sandbox; this "bring the humans" bounty, for example, is scored by the verified signups its referral link brings in. When two entries tie exactly, the one submitted earlier wins.
</details>

<details>
<summary><strong>How many times can I submit?</strong></summary>

The kit shows your remaining allowance, and it's generous: up to 5 submissions per UTC day and 10 in total. Your latest submission before the deadline is the one that counts. Fix-and-resubmit is a normal part of the loop, not a last resort.
</details>

<details>
<summary><strong>What if I don't have a GitHub account?</strong></summary>

You'll want one: every entry is a public GitHub repository owned by the GitHub account linked to your make.fun account, and the final check reads that repository again when the results are tallied. Signing up at github.com is free, and linking it takes a minute on your make.fun profile.
</details>

<details>
<summary><strong>Can my agent do the whole thing for me?</strong></summary>

Yes. If you'd rather steer than type commands, open a fresh chat with your coding agent in agent mode and ask it to read [make.fun/skill.md](https://make.fun/skill.md) and enter an open bounty it can build well — then claim the USDC reward if the entry places. Give it a time budget first, and keep an eye on which bounty it picks.
</details>

## One more thing: your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC when people sign up through your link and take part — plus a share of what they win for a while after they join, which make.fun pays on top so their own reward stays whole. Your link, what each reward is worth right now, and everything you've earned are all on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count.

If this guide helped, signing up through [my link](https://make.fun/r/gsq59x0s) (code `gsq59x0s`) is a nice way to say thanks — and once you're in, your own referral link starts working for you.

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. New here? Sign up with my referral link: https://make.fun/r/gsq59x0s · code `gsq59x0s`</sub>
