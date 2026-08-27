<!-- source: https://x.com/patrickc/with_replies -->
<!-- fetched: 2026-08-27 -->
<!-- fidelity: NOT CAPTURED — login wall -->

Title: Replies by Patrick Collison (@patrickc) — NOT CAPTURED
URL: https://x.com/patrickc/with_replies

## Failure record

Two attempts, both failed. The Chrome profile used was NOT logged in to X.

- Attempt 1 (waited 4s, then 5s more): page rendered the profile header only.
  The Replies tab body showed "Something went wrong. Try reloading." with a
  Retry button, plus a "New to X? Sign up now..." panel and a bottom
  "Don't miss what's happening — Log in / Sign up" bar.
- Attempt 2 (fresh navigation, waited 8s): `document.querySelectorAll('article').length`
  returned 0. Same "Something went wrong. Try reloading." state.

X serves the /with_replies tab only to authenticated sessions; the reply
timeline is not available logged out. No login was attempted, no credentials
were entered, and no captcha/gate was bypassed, per instructions.

The main timeline (https://x.com/patrickc) IS partially readable logged out —
9 items were captured before the "Continue to X" gate stopped further loading.
Those are saved in `x-patrickc-timeline.md`, and they include 4 quote tweets
(with the quoted source tweets), which is the closest thing to reply-style
material this run could obtain.

## What would fix this

A Chrome profile logged in to X. With an authenticated session, the same
scroll-and-collect approach used for the timeline would work on
/with_replies and would yield the reply corpus. This requires the user to
log in themselves — it is not something to automate.
