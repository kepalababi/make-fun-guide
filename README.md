# The Complete Guide to make.fun Bounties

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/kepalababi/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/kepalababi/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Ever wanted to get paid for building software, but had no idea where the
work is? That is the gap make.fun fills. It is a marketplace where people
post bounties — real tasks with a deadline and a cash reward — and builders,
usually working together with an AI coding agent, compete to deliver the
best entry. Winners are paid in USDC on Solana.

This guide walks you from zero to your first submitted entry, and then shows
you how the referral side of the site works, so you can earn even when you
are not the one building.

> **Start here:** sign up with my link —
> [https://make.fun/r/h460manj](https://make.fun/r/h460manj)
>
> My referral code is `h460manj`. If you sign up through that link, your
> account is tied to it, and I get credit when you become an active member.

## What this guide covers

- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty worth your time](#step-2--pick-a-bounty-worth-your-time)
- [Step 3 — Download the bounty kit](#step-3--download-the-bounty-kit)
- [Step 4 — Build your entry with an AI agent](#step-4--build-your-entry-with-an-ai-agent)
- [Step 5 — Submit your entry](#step-5--submit-your-entry)
- [Step 6 — Get checked, fix problems, resubmit](#step-6--get-checked-fix-problems-resubmit)
- [Step 7 — Claim your reward](#step-7--claim-your-reward)
- [Earning with your own referral link](#earning-with-your-own-referral-link)
- [Mistakes that cost beginners money](#mistakes-that-cost-beginners-money)
- [FAQ](#faq)

## What make.fun actually is

Think of make.fun as a job board crossed with a contest. A bounty creator —
sometimes the make.fun team, sometimes another user — describes something
they want built, puts up a reward, and sets a deadline. Builders read the
brief, build the thing, and submit it. When the deadline passes, entries
are scored the same way for everyone, and the top entries share the reward.

Three ideas make the site different from a normal freelance board:

**The reward is locked up front.** When a bounty opens, its full prize is
placed in an on-chain escrow on Solana. That means the money is already
there before you start working. Nobody can quietly pull the prize after you
have done the work. Winners claim their share from that escrow.

**You build with an AI agent, and you prove it.** Most entries are built
with a coding agent — Claude Code, Codex, Cursor, Copilot, or any of the
other common ones. When you submit, you also upload the transcripts of the
sessions that built your entry. Those logs show that your own agent did the
work, instead of someone passing off copied code as their own. Keep your
sessions intact and do not rewrite them after the fact.

**Referrals are a real earning channel.** Every account gets its own
referral link. When a new person signs up through your link and becomes a
verified, active member, that signup can count toward referral rewards and
toward referral-based bounties like this one. More on that below.

## What you need before you start

You do not need much, but get these four things sorted before you pick a
bounty, or you will lose time halfway through:

- **A make.fun account.** Sign up through a referral link if you have one
  (mine is above). You can sign in with GitHub, a Solana wallet, Google,
  Apple, or Discord.
- **A Solana wallet.** Rewards are paid in USDC on Solana, so you need a
  wallet address you control. Your agent also signs entries with a Solana
  keypair, which doubles as the payout wallet for that entry.
- **A GitHub account, linked to your make.fun profile.** Most bounties ask
  for a public GitHub repository as the entry. The repository has to belong
  to the GitHub account linked to your make.fun account, or the entry is
  refused. Link it on your profile page before you submit anything.
- **An AI coding agent.** Any of the well-known ones works. Pick the one you
  already use and are comfortable with, rather than learning a new tool
  mid-bounty.

## Step 1 — Create your account

1. Open my signup link: [https://make.fun/r/h460manj](https://make.fun/r/h460manj)
2. Choose how to sign in. GitHub is the smoothest choice if you plan to
   enter GitHub-repository bounties, because your GitHub account is then
   already linked.
3. Pick a username and finish your profile. A display name, a picture, and
   a short bio make you look like a real person, which matters when other
   people decide whether to trust your referral link.
4. Find your own referral link on the Referrals tab of your profile. Save
   it somewhere — you will use it every time you tell someone about the
   site.

One account per person. Teams enter under a single account and split any
prize among themselves afterwards.

## Step 2 — Pick a bounty worth your time

Open the bounty board and look at three things before you commit:

- **The reward and how it is split.** Some bounties pay one winner, some
  share the pot across the top 10, 25, or 50 entries. A bounty that pays
  the top 50 is friendlier to a first-timer than a winner-takes-all one.
- **The deadline versus the size of the job.** Read the brief properly.
  A task that looks small but has hidden requirements will eat your whole
  weekend. Check whether there is a starter kit, a dataset, or a local
  test you can run.
- **How entries are scored.** Every bounty publishes its scoring rules.
  Some are graded by an automated harness, some by checks against a list
  of requirements, and some — like referral bounties — by how many verified
  people your entry brings in. Build toward the stated scoring, not
  toward what you personally think is impressive.

If you are brand new, pick a small bounty first. Finishing one full cycle —
build, submit, get checked, claim — teaches you more than starting three
big ones and finishing none.

## Step 3 — Download the bounty kit

Almost every bounty ships a kit. It usually holds the full rules, the
command-line tool you submit with, and a starter project. Download it from
the bounty page and read the rules file first, before you write any code.
The rules are the contract: they tell you what the entry must contain,
what gets an entry refused, and what the transcript checks look for.

A typical kit download looks like this in a terminal:

```sh
# fetch the kit for the bounty you picked, then unpack it in place
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Replace `<bounty-slug>` with the slug on the bounty page. Inside the
unpacked kit you will find a `cli/` tool — that is the program you will
use to bundle transcripts, run pre-submit checks, and submit.

## Step 4 — Build your entry with an AI agent

This is where the actual work happens, and where beginners most often hurt
their own chances. A few habits that pay off:

- **Start a fresh agent session after the bounty opens.** Sessions that
  began before the opening cannot be entered. Do the whole build inside
  one session that started after the opening time.
- **Write a draft, then revise it.** Do not paste a finished file in one
  go and call it done. The transcript checks look for evidence that your
  agent actually wrote and revised the work across more than one turn.
  Draft it, run it, read what came back, and improve it.
- **Do not copy the starter wholesale.** The kit's starter is a starting
  point, not an entry. An entry that is just the starter with the
  placeholders swapped in fails the authorship checks. Make it yours:
  restructure it, add your own explanations, cut what does not fit.
- **Keep your sessions.** Do not delete session logs, and do not edit
  them by hand. The submission bundles them as they were recorded. If
  your tool keeps no session record at all, the kit explains how to hand
  over what you can see — but note that handed-over entries are ranked
  without a paid place, so a recorded session is always better.
- **Test what you built.** Run the kit's local checks early, while you
  still have time to fix what they flag. A check that fails the night
  before the deadline is a very different problem from one that fails on
  day one.

## Step 5 — Submit your entry

When the work is done and the local checks pass, submit from the kit's
command-line tool. In outline, a submission needs:

- the URL of your public GitHub repository,
- the full commit hash of the exact commit you are entering,
- a title for your entry (name what it does, not your handle),
- the transcript bundle the kit built from your sessions,
- your Solana keypair, which signs the entry message.

The signature is only valid for a few minutes and covers exactly one
submission, and the wallet that signs is the wallet a prize is claimed to.
Later pushes to the repository do not change the entry — the commit you
named is snapshotted at submission. If you improve the work afterwards,
submit again with the new commit; your most recent submission before the
deadline is the one that counts. Submissions are limited — at most five
per UTC day and ten in total for a bounty — so make each one count: run
the local check first, and do not submit a commit you have not looked at.

## Step 6 — Get checked, fix problems, resubmit

After you submit, the site runs its checks and your entry gets a status.
Read it. A refusal always names the failed checks and how to fix each one,
so treat it as a to-do list, not a verdict. Common fixable problems:

- the repository is not public, or belongs to a different GitHub account
  than the one linked to your make.fun account;
- the README does not name your referral code, or the required badge
  lines are missing or broken;
- the screenshot is missing, too large, or not actually a picture of your
  repository page;
- the transcripts do not show your agent writing and revising the work,
  or the usage records are missing.

Fix the problem, bundle the transcripts again, and submit again before the
deadline. You have a limited number of submissions, so do not burn them on
unchecked guesses — run the kit's local check first.

## Step 7 — Claim your reward

Results are published after the final checks run. If you placed in a paid
spot, claim your prize from the escrow to the wallet that signed the
winning entry. Claims have a window — do not leave it until the last day.
If a prize is not claimed in time, it can pass to the next entry in the
standings or return to the reward pool, depending on the bounty.

For larger yearly totals, the claim may ask for tax paperwork. Below the
reporting threshold it normally asks only for the payout wallet and the
winner agreement. Every claim is screened against sanctions lists.

## Earning with your own referral link

This is the part most newcomers skip, and it is the whole point of this
particular bounty. Here is how referrals work on make.fun:

- **Your link is yours.** Find it on the Referrals tab of your profile.
  It looks like `https://make.fun/r/<your-code>`. Share the full link, or
  just the code — both bind the same way.
- **First touch wins, for 60 days.** When a visitor first arrives through
  a referral link, that code sticks to their browser for 60 days. If they
  create an account inside that window, the signup is credited to the
  owner of that code, even if they later click someone else's link.
- **Only verified humans count.** Signups are checked by the same system
  that pays referral rewards. Your own account does not count. Neither do
  bot signups, idle accounts that never take part, or clusters of signups
  from the same address. A signup still under its review hold does not
  count until the hold closes.
- **Share where real people are.** A guide like this one, posted where
  developers actually hang out, brings steadier signups than blasting the
  bare link into random groups. People sign up because the guide helped
  them understand the site, and the link is right there when they are
  ready.
- **My link, for reference:** [https://make.fun/r/h460manj](https://make.fun/r/h460manj)
  — code `h460manj`.

For this bounty specifically, the leaderboard ranks entries by verified
human signups through their link, and the top 50 entries share $1,000 in
USDC. So the guide is not just an entry — it is the thing that does the
bringing.

One timing detail worth knowing: when the deadline passes, the final check
runs at once. Each signup is decided only after its own 24-hour review
hold has closed, and only the signups verified by the end of that final
check — 30 hours after the deadline — make it into the result. A signup
that is still undecided at that point simply does not count, so signups
that arrive in the last hours before the deadline are worth less than
ones that arrive with a full day to spare. Share your guide early.

## Mistakes that cost beginners money

- **Starting before linking GitHub.** You build the whole entry, then
  discover the repository owner does not match your linked account.
  Link it first.
- **Submitting a private repository.** Entries must be public. A private
  repo cannot be read by the final re-check, and the entry is
  disqualified.
- **Letting the session start too early.** A session that began before
  the bounty opened cannot be entered, even if all the work happened
  after. Start fresh.
- **Pasting secrets into the repository.** Never commit an API key, a
  token, or a wallet keypair file. A repository holding a pushed secret
  is refused, and rotating it afterwards does not undo the history.
- **Ignoring the status page.** A refused entry that you never read is
  just a wasted submission. The status tells you exactly what to fix.
- **Spamming your link.** Fake or bot signups never count, and they can
  get your referral credit rejected. One honest guide beats a hundred
  low-effort posts.

## FAQ

**Do I need to know how to code to enter?**
For most bounties, yes — or you need an agent that does the coding while
you direct it. But referral bounties like this one are different: the
entry is a guide, and the score is the people it brings. If you can explain
things clearly, you can compete.

**Is entering free?**
Most bounties are free to enter. One with an entry fee says so on its page.

**How are ties broken?**
On an exact tie, the entry whose final submission arrived first places
first. Submitting early is a small, real advantage.

**Can I enter the same bounty twice?**
You can submit more than once, up to the daily and total limits, but only
your last submission before the deadline counts.

**When do I get paid?**
After the results are final and you claim. The prize goes to the wallet
that signed the winning entry, in USDC on Solana.

**Where do I start, again?**
Right here: [https://make.fun/r/h460manj](https://make.fun/r/h460manj) —
code `h460manj`. Create your account, link GitHub, pick a bounty, and build
something. Good luck, and see you on the board.
