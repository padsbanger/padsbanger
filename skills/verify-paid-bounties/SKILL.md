---
name: verify-paid-bounties
description: Verify whether an online bounty, paid issue, contest, grant task, or agent-marketplace job is authentic, funded, eligible, open, and economically worth pursuing before doing work. Use when a user provides a bounty URL or reward claim, asks whether a paid task is real or claimable, needs an evidence pack for a go/no-go decision, or wants to avoid unpaid speculative work.
---

# Verify Paid Bounties

Turn a reward claim into an evidence-backed pursue, validate-first, or reject decision. Spend the least effort needed to falsify weak opportunities before creating accounts, accepting terms, connecting wallets, or writing code.

## Set the decision boundary

Collect or infer:

- Canonical task URL and stable task or issue ID
- Stated gross reward, currency, and payout network
- Submission deadline and expected deliverable
- Required account, wallet, identity, jurisdiction, or legal acceptance
- Minimum acceptable hourly value and maximum validation cost

Treat missing inputs as unknowns, not favorable assumptions. Do not request secrets, recovery phrases, private keys, session cookies, or repository credentials.

## Resolve the canonical source

Use the marketplace, project, contract, or repository that controls the task. Treat search pages, bounty aggregators, screenshots, social posts, and cached snippets as leads only.

Prefer evidence in this order:

1. Authenticated or public canonical API response
2. On-chain contract state or authoritative block explorer
3. Official task page and official documentation
4. Project repository code, issue history, and maintainer statements
5. Third-party indexes and search results

Record exact URLs, identifiers, timestamps, and raw status fields. When documentation and live state disagree, report the disagreement and use live state for the decision.

## Verify the money

Establish each point independently:

- Reward amount and denomination
- Gross versus net payout after platform, network, conversion, and withdrawal fees
- Funding state: escrowed, deposited, guaranteed, pledged, or merely advertised
- Escrow address, transaction, funded milestone, or platform guarantee when one exists
- Payout asset liquidity and a realistic withdrawal path
- Minimum withdrawal, lockup, vesting, dispute, refund, or clawback conditions

Never equate a displayed reward with escrow. If funding cannot be verified, mark it `unfunded/unknown` and require a cheaper proof step before work.

## Verify claimability

Check the live task state rather than the surrounding issue alone:

- Open/active status and whether the submission window is actually open
- Deadline, timezone, and remaining hours
- Existing submissions, winners, awards, reservations, or assigned workers
- Eligibility by country, account age, identity, reputation, skill, or team size
- Whether required legal terms are effective and currently acceptable
- Required wallet network, token, KYC, tax form, or paid subscription
- Whether the task owner can still change scope or decline all submissions
- Exact submission mechanism and proof required for acceptance

Do not create an account, fund a wallet, sign a message, accept legal terms, or submit a transaction merely to inspect an opportunity. Surface that action as a decision cost.

## Test external dependencies

Separate work controlled by the worker from work that needs another project, maintainer, buyer, device, private environment, or credential.

For externally dependent tasks:

1. Confirm the target project is technically relevant.
2. Find evidence that its owner wants the change or review.
3. Propose one narrow validation step with the bounty and draft/legal caveats disclosed.
4. Wait for explicit interest before building a speculative integration.

Avoid generic outreach. Contact only a directly relevant owner or thread, disclose the incentive, and do not imply affiliation.

## Calculate bounded expected value

Use ranges when probability is uncertain:

```text
net_reward = gross_reward - platform_fees - withdrawal_fees - direct_costs
expected_value = (payout_probability * net_reward) - (hours * hourly_floor) - risk_reserve
```

Reduce payout probability for unverifiable funding, discretionary judging, heavy competition, vague acceptance, external dependencies, weak owner activity, or draft legal terms. Do not invent precision; explain the factors behind the range.

Classify:

- `pursue now`: funded, eligible, open, controlled scope, positive expected value
- `validate first`: one cheap test can resolve the main uncertainty
- `reject`: a fatal condition exists or expected value is below the floor

## Apply stop rules

Reject or pause immediately when any condition holds:

- No canonical task or stable identifier can be resolved
- Task is closed, expired, awarded, cancelled, or submission-disabled
- Reward is unverified and the sponsor will not provide funding proof
- Required terms are draft, unavailable, or cannot legally be accepted
- Eligibility fails or payout cannot be withdrawn
- Scope depends on an unresponsive outside project
- Acceptance criteria are materially ambiguous and the owner will not clarify
- Validation requires secrets, irreversible commitments, or disproportionate spend
- Bounded expected value is negative

Recheck volatile facts immediately before starting work and immediately before submitting.

## Produce the evidence pack

Return a concise record that another operator can audit:

```markdown
# Bounty decision

- Decision: pursue now | validate first | reject
- Checked at: <ISO-8601 timestamp>
- Canonical task: <URL and ID>
- Reward: <gross, fees, estimated net>
- Funding: verified | unverified | unfunded — <evidence>
- State: <open/closed, deadline, submission window>
- Eligibility: <met, failed, or unknown requirements>
- Competition: <submissions/awards/reservations>
- Terms: <version, effective state, key payout/dispute condition>
- External dependencies: <none or named dependency and owner signal>
- Expected value: <assumptions and range>
- Fatal risks: <none or list>
- Cheapest next test: <one reversible action, owner, and stop condition>

## Sources
- <canonical URL> — <fact supported>
```

Label every conclusion as verified fact, source-backed inference, or unknown. Quote sparingly. Never report advertised value as realized revenue.
