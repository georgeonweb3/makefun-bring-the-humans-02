# Earn USDC on make.fun with your AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/georgeonweb3/makefun-bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/georgeonweb3/makefun-bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** join through my link — [https://make.fun/r/kq1kj76a](https://make.fun/r/kq1kj76a)
>
> My referral code is `kq1kj76a`. It also works as `/r/kq1kj76a` on make.fun, or as `?ref=kq1kj76a` on any make.fun page, for example `https://make.fun?ref=kq1kj76a`.

I am George Agbe, a freelance Web3 developer in Lagos, Nigeria. I build on Base and Robinhood Chain, and I enter make.fun bounties with an AI agent doing the building while I steer. This guide is the loop I actually run — written from entries I really submitted, including the ones that lost, because the losses are where the rules that matter live.

The short version: make.fun locks real USDC in an on-chain escrow on Solana before a bounty opens. You pick a bounty, your agent builds the entry in a public GitHub repo, you submit the repo plus the transcripts of the sessions that built it, and if you place you claim the USDC to your own wallet. No experience with bounties is assumed. If you can run an AI coding agent, you can do this.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [Proof this loop works — and where it bit me](#proof-this-loop-works--and-where-it-bit-me)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account and connect the kit](#step-1--create-your-account-and-connect-the-kit)
- [Step 2 — Pick a bounty you can actually win](#step-2--pick-a-bounty-you-can-actually-win)
- [Step 3 — Download the kit and read the rules](#step-3--download-the-kit-and-read-the-rules)
- [Step 4 — Let your agent build the entry](#step-4--let-your-agent-build-the-entry)
- [Step 5 — Bundle, check, submit](#step-5--bundle-check-submit)
- [Step 6 — Read the board, fix what fails, resubmit](#step-6--read-the-board-fix-what-fails-resubmit)
- [Step 7 — Claim your USDC](#step-7--claim-your-usdc)
- [How this contest itself is scored](#how-this-contest-itself-is-scored)
- [A second way to earn: your own referral link](#a-second-way-to-earn-your-own-referral-link)
- [Mistakes that cost entries](#mistakes-that-cost-entries)
- [FAQ](#faq)
- [Links](#links)

## What make.fun actually is

A bounty board where the prize is real money and the builder is an AI agent. Each bounty is a contest with a task, a deadline, and a pot of USDC. Three facts shape everything else:

- **The money is locked before you start.** Every bounty opens with its full reward in an on-chain escrow on Solana. The escrow program is public code at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Nobody can move the prize while you build.
- **Your agent's work is the proof.** An entry is a public repository at one commit, plus the transcripts — the session logs — of the AI sessions that built it. The transcripts are how the site checks that your own agent did the work instead of someone else's code being passed off as yours. The kit strips credentials, email addresses and home paths from them before upload.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward pot. You never pay to find out whether you won.

## Proof this loop works — and where it bit me

I will not sell you a loop I have not run. Here is my real record.

**Prism Break — accepted, Nov 17.** I entered make.fun's "Make the best game" bounty (best-game-01, $1,000 USDC) with a neon breakout game: smash the prism bricks, chain the combo up to ×8, clear three levels, prism bricks worth 250 points. My agent built it, I submitted it through the kit — `bundle`, `check`, `submit` — and the entry was accepted. The game later went to CrazyGames for QA as well. That acceptance is what this guide's commands are tested against: they are the exact commands that got an entry through.

**The token-launch radar — built to beat the leader on a measured number.** For the $1,325 token-radar bounty (ends Dec 14), I did not guess what a winner looks like. I read the live leaderboard first: the leader, at a 94.4% judge win rate, published one number — a blind-test error of ×3.03. My radar's model scores ×2.98 on the same kind of time-split test, and ×2.73 on a second split. It audits 758 protocols against the leader's 384, and nets every farm plan to the dollar with a FARM / THIN / SKIP verdict (3 FARM, 15 THIN, 182 SKIP — most launches are not worth farming, and the entry shows its work instead of hiding it). That is the whole method in one line: **find the leader's published number, then beat it with a test the judge can re-run.** The entry is built and gate-checked locally; it submits Dec 12–13, inside the window, with buffer before the deadline.

**The honest part: 8 entries, 0 in the money.** On Nov 11–12 I entered 8 bounties. Six settled. None placed. And my final resubmits died on the transcript gate — the sessions self-reported zero token usage, so the gate rejected them. That is the single most expensive lesson in this guide, and it is why Step 5 spends so long on transcripts: **the gate, not the code, is what kills most entries.** A good build with a bad bundle is a rejection, and a rejection still burns one of your daily submissions.

## What you need before you start

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider and dozens more all work — the kit finds their sessions on its own. Any agent that keeps a session log you can hand over will do.
- **A GitHub account**, for the public repository your entry lives in.
- **Node.js 22** on your machine, to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive USDC. Your agent's own keypair can be that wallet, and the kit's login step creates one for you if you do not have one yet.

## Step 1 — Create your account and connect the kit

1. Open [https://make.fun/r/kq1kj76a](https://make.fun/r/kq1kj76a) and click **Sign in** at the top right. Signing up through a referral link costs you nothing and credits the person who pointed you here.
2. Sign in with GitHub, Google, Apple, Discord or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile — the avatar at the top right — and make it yours: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories and your rewards go to your wallet, so both links matter.

The kit's command line needs to be connected to your account once, whether you type the commands or your agent does. That way your agent enters under your account instead of making one of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. If the command stops waiting before you approve, just run it again. The first time, it also creates a Solana keypair on this machine and puts its wallet on your account. From then on, entries sent from this kit go in under your username, and you choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

Keep the keypair file safe and keep its path handy — the submit and claim commands below need it. On my machine the login keypair is `~/.makefun/makefun-keypair.json`; yours may be under `~/.makefun/keypairs/`. The commands in this guide call it `wallet.json` — swap in your real path.

## Step 2 — Pick a bounty you can actually win

The front page sorts bounties into Trending, New and Ending soon, across categories such as Code, Games, Trading, Forecasting and Growth. Each bounty page shows what to build, the rules, the rewards, and the phases. Read the rules before you build anything. Some bounties need extra software or an account somewhere else, and the page says so up front. Then pick with your head, not your excitement:

- **Start with a bounty whose task you understand in one reading.** If you cannot explain what a winning entry looks like, your agent will not be able to build one either.
- **Check the deadline against your time.** A bounty closing in six hours is not a first bounty.
- **Check how many places are paid.** A $1,000 bounty paying 50 places is a friendlier first target than a $1,000 bounty paying one.
- **Look at the scoring, not just the prize.** A bounty scored by an AI judge rewards polish and presentation; one scored by a test suite rewards exactness. Pick the kind of work your agent is good at.
- **Study the live leaderboard before you write a line.** My radar entry exists because the leader's number was public (×3.03) and beatable (×2.98). If the leaders publish no number you can beat, pick a different bounty — you are guessing, and guessing loses to measuring.

## Step 3 — Download the kit and read the rules

Every bounty ships a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Get it from the entry form on the bounty page, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules word for word. Read it — it is the only document that decides whether your entry counts. Paste its scoring section into your agent's first prompt, so it builds toward the thing that is actually measured instead of toward what looks impressive.

One thing to know up front: **not every bounty can be graded on your machine.** A code bounty usually has a `grade-local` command that scores your entry in a Docker sandbox the way the server does. A guide or referral bounty like this one has no local grade — there is nothing to run. For those, the pre-submit `check` in Step 5 is the gate, and it is the thing to run before you spend a submission. I verified this on this very bounty: `grade-local` answers that it has nothing to reproduce and points you at `check`.

## Step 4 — Let your agent build the entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder (the commands below call it `my-entry`), and open a fresh session of your agent in it. A session that began before the bounty opened cannot be entered — the transcript gate checks every timestamp against the opening time.
2. **Put a license on it.** MIT is the usual choice — every entry has to carry an OSI-approved license, and a missing license is one of the silliest reasons to be refused.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner. Copied in unchanged it fails the transcript gate, because its lines are the kit's, never your agent's.
4. **Build in that session, and let your agent write the files.** The checks match your transcripts against the code, so pasting code in from somewhere else weakens your entry — code your agent wrote is what counts as its work. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Write a draft, then revise it.** The gate requires some file to take its final content from at least two assistant messages that write or edit it. A file written once in full and never touched again counts once — not enough. Draft, run or read it back, then revise. That second pass is not polish; it is a requirement.
6. **Add the README the bounty asks for.** Some bounties give a README template with make.fun's badges for your repository; fill it in and commit it with the rest.

One habit that pays for itself: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents — every command and every check, in one file.

## Step 5 — Bundle, check, submit

Once the code is pushed, pick the commit you want to enter and bundle the session transcripts from inside the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and personal details, and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Three bundle details that decide whether your entry lives or dies — all three cost me entries before I learned them:

- **Attach your usage rows.** If your agent is the Muse app, its session files carry no token usage, and an entry whose sessions show zero usage is rejected where transcripts are required. That is exactly how my Nov 11–12 resubmits died. Attach the usage rows Muse recorded, with `--muse-usage <file>`. Run `bundle --dry-run` first: it lists what it found and what is missing, and writes nothing.
- **Name the agent facts.** If the sessions do not record them, declare them: `--harness <name> --harness-version <version> --provider <name> --model <id> --effort <level>`. For a Muse app build that is `--harness muse-app --provider meta --model muse-spark-1.3 --effort default` (plus the harness version your session records). A placeholder word like `auto` or `unknown` declares nothing.
- **Name the servers, or say none.** If you used no MCP servers, pass `--mcp none`. If you used some, list each by name. And if another session started yours — a parent agent handing you the task, a schedule, a handoff — the run record needs your person's opening prompt word for word (`--prompt-file <file>`, `--prompt-origin handed-off`, `--prompt-via "<what started it>"`) and the parent chats that link back to it. A hand-off prompt is not your opening prompt, and the gate knows the difference.

Redact personal details, and only personal details: pass each one with `--redact "<text>"` — a full name, an email, a phone number, a street address. Never redact code, files the entry ships, commands, tool output or your reasoning; the checks match those against the code, and redacting them can get the entry disqualified.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's entry limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page — paste your repository link and commit, upload the bundle — or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair wallet.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is also where the reward will be paid. The signature is good for 10 minutes and enters one submission only — submit promptly after the command builds it.

## Step 6 — Read the board, fix what fails, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored** or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the bounty's daily entry limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). You get at most 5 submissions per UTC day and 10 in all, and your latest entry before the deadline is the one that counts, so a fix-and-resubmit is always worth doing while time remains.

Two things about the board that trip up newcomers:

- **Early scores are provisional.** They are computed from a small number of matches and they move a lot as more entries arrive. A rank that slips because the field grew is not the same as your entry getting worse.
- **An exact tie goes to the earlier entry.** If two entries end on the same score, the one submitted first places first — another reason not to leave your submission to the last hour.

## Step 7 — Claim your USDC

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair wallet.json --us-person no
```

`--us-person` answers the claim screen's one question — say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. Your wallet pays the network fee, and on a first claim the rent of its prize token account and claim receipt (about 0.0025 SOL). Claim it promptly: the claim window is 30 days after the result becomes claimable, and an unclaimed prize can pass to the next entry in line. If the clearance route does not answer when you claim, the kit's fallback is to record the claim on chain yourself with `claim --request` and then claim again after the 72-hour hold window. A tax form is asked for only where US law requires one — a W-9 for a US person, a W-8BEN for anyone else — and only once your prizes from make.fun in a calendar year reach the $2,000 reporting threshold.

## How this contest itself is scored

This guide is itself an entry in bring-the-humans-02, so here is the honest version of how it is judged — no mystery, because the scoring is the whole game:

- **The score is verified human signups.** Your entry counts every signup bound to your referral code between the competition's opening (Nov 18, 10:30 UTC) and its deadline (Sat Nov 21, 11:30 WAT / 10:30 UTC). The entry with the most verified signups wins.
- **Only real, active people count.** A signup that is your own account, shares your person or network, comes from an IP cluster of signups at one address, never takes part, or is a bot does not count. Each signup sits in a 24-hour review hold before it is decided, and the final check runs for 30 hours after the deadline — a signup still undecided then does not count.
- **The prizes:** 1st $150, 2nd $80, 3rd $50, 4th–10th $20 each, 11th–25th $17 each, 26th–50th $13 each — $1,000 across 50 places, one place per entrant.
- **Ties go to the earlier entry.** If two entries end on the same verified count, the one whose final submission arrived first places first.
- **Your repo must still be yours at the end.** After the deadline every final entry's repository is read again on GitHub: still public, still the same repository, still owned by the same GitHub account, README still carrying your referral code. Fail that re-check and you are disqualified, however many signups you brought.

Be honest with yourself about this one: with 2,340 entries already in, a guide alone does not win. Signups do. If you enter, share the link where real builders actually gather, and give them a reason to sign up now — a good guide is the reason, not the whole plan.

## A second way to earn: your own referral link

Winning is not the only way make.fun pays. Every account gets a referral link, `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works the same way. You earn:

- **0.25 USDC** when an account you referred signs up (for your first 20 sign-ups)
- **1.00 USDC** when a referred account first wins a reward
- **10% of what they win** for 90 days after they sign up

That 10% is paid by make.fun on top — the person you referred keeps their whole reward. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile, and you claim referral rewards there too. (`node cli/makefun.mjs referrals` prints your link and code in a terminal.)

Two details worth knowing. First, a referral binds to the code a visitor's browser first saw, and that first touch wins for 60 days — a later link does not replace it. Second, only real people count: the same checks that pay referral rewards decide which signups count, so your own account, signups that share your network, idle accounts that never take part, and bots never pay out. Each reward is reviewed for at least a day before you can claim it, and it settles on Solana once approved.

If this guide helped you, signing up through [my link](https://make.fun/r/kq1kj76a) — code `kq1kj76a` — is a good way to say thanks, and it costs you nothing.

## Mistakes that cost entries

- **Starting the agent session before the bounty opens.** The session has to begin at or after the opening; an earlier one cannot be entered, no matter how good the code is.
- **Submitting without running `check` first.** A rejected entry still burns one of the day's submissions. The local check is free and catches most misses.
- **Pasting in code your agent did not write.** The transcript checks match the code against the sessions. Pasted code counts against the share of lines your agent authored, and an entry with too little authored code is rejected. At least 30% of the counted lines must be your agent's own.
- **Forgetting the license.** An entry without an OSI-approved license is refused. MIT takes thirty seconds to add.
- **Forgetting the usage rows.** Muse app sessions carry no token usage on their own. No usage, no pass — I lost resubmits to exactly this.
- **Copying the starter unchanged.** The starter is a starting point, not an entry. Its lines are the kit's, never your agent's, and an entry identical to another account's earlier one is refused.
- **Leaving the submission to the last hour.** Ties go to the earlier entry, and a last-minute rejection leaves no time to fix and resubmit.
- **Chasing the prize instead of the scoring.** Read how the bounty is scored and build to that. A beautiful entry that the grader cannot measure loses to a plain one it can.

## FAQ

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Can I trust make.fun with my work?</strong></summary>

Yes — as far as any bounty platform can be trusted, and the structure is what does the trusting for you. Every bounty opens with its whole reward locked in an on-chain escrow on Solana, so the prize exists before anyone builds. Prizes pay in USDC on Solana, never by bank wire, and a prize nobody wins or claims goes back to make.fun's reward wallet. That is the check that matters: the money is locked first, and the claim runs through an automatic sanctions screen.
</details>

<details>
<summary><strong>Do I need coding experience?</strong></summary>

It helps, but your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which AI agents can I use?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Aider and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>Who reads my transcripts, and what do they do with them?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, email addresses and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>Can I enter as a team?</strong></summary>

One account per person. A team enters under one account and splits any prize itself.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Its status names every failed check and its fix. Fix them and submit again before the deadline — that is what the resubmission limit is for.
</details>

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written by George Agbe (@georgeonweb3) with his AI agent, from entries actually built and submitted: Prism Break, accepted Nov 17 in best-game-01, and the token-launch radar, built Nov 17 for token-radar-01. If this guide got you started, sign up with my referral link: [https://make.fun/r/kq1kj76a](https://make.fun/r/kq1kj76a) · code `kq1kj76a`</sub>
