# Vertex order diagnosis checklist

A small, manual checklist for retailers and developers investigating payment/order mismatches. It is not an app, payment tool, or guaranteed fix. No store connection is needed.

## Start safely

- Do not retry a customer charge to reproduce a failure.
- Do not publish customer names, addresses, emails, card details, secrets, or raw production logs in this repository or its issues.
- Keep original evidence privately. Make a redacted working copy.
- Use a test environment and the provider's test mode for any later reproduction.

## Build one event timeline

Record each event with its timezone and evidence source. Keep observations separate from explanations.

| Event | Timestamp and timezone | Evidence source | Observed state |
| --- | --- | --- | --- |
| Order created | | | |
| Payment authorized | | | |
| Payment captured, failed, or refunded | | | |
| Provider event delivered | | | |
| Order status changed | | | |
| Buyer notification sent | | | |
| Fulfillment or cancellation | | | |

A missing event is an evidence gap, not proof the event never happened.

## Questions before choosing a fix

1. Are the payment and order records actually about the same transaction?
2. Which states are observed directly, and which are inferred from a screenshot or email?
3. What platform, gateway, plugin, and app versions were installed at the time?
4. Was an event delivery attempted, acknowledged, retried, or rejected? Record the evidence without copying secrets.
5. What rule or person changed the order state?
6. Does official support or an upstream release already address this exact failure?
7. Can the proposed next test be run without a real customer charge or production change?

## Fictional example

A payment record shows capture at 14:02 and an order shows cancellation at 14:20. That sequence alone does not establish why it happened. The next evidence is the order notes, event delivery history, installed versions, and cancellation rule. Do not label a cause until those records support it.

## Write the result

- Observed: the facts supported by the evidence.
- Missing: records still needed.
- Hypothesis: a possible explanation, labeled as such.
- Existing fix to check: official support or upstream change, if verified.
- Next safe test: one bounded test with an expected result and a stop condition.

## About Vertex

This resource is published by Vertex. It is an early service with no customer case studies or guaranteed results claimed. Vertex is independent of Shopify, WooCommerce, and Stripe.

## Service scope and redacted-evidence intake

Start with one failed order, not another app. Vertex is opening an evidence-first diagnosis service for remote retailers in the United States, United Kingdom, Canada and Australia.

Tell us what you expected, what actually happened, and when. We first check whether the evidence is enough for a useful review. No charge for this initial fit check. Any further work needs an agreed scope and price.

### What the review looks for

- Payment and order disagree: separate authorization, capture, order status and timestamps before choosing a fix.
- Pickup or fulfillment status is confusing: compare intended item quantities with the messages and status the buyer actually saw.
- The failure only happens sometimes: build an event timeline and separate what is proved, suggested and missing.

### Send only the minimum

- Your store URL and country; platform and relevant app or plugin versions.
- One redacted example: expected result, actual result, date, time and timezone.
- A short timeline or cropped screenshots with names, addresses, emails and payment details removed.
- What you have already tried, including any answer from the platform or payment provider.

Do not send passwords, API keys, card numbers, full customer records or admin access. Do not retry a customer charge just to create a test. Do not put private evidence in public GitHub issues.

### What comes next

1. We check fit and evidence before accepting work. Platform support may be the right answer.
2. If a review is agreed, its output is a short diagnosis note: timeline, evidence gaps, native or upstream fixes to check, and a bounded next test.
3. No store change, deployment, payment action or access request is included in the initial fit check. Later work is agreed separately.

### Contact for an initial inquiry

[Send an initial inquiry to Vertex](mailto:novaagent@mail.instinct.com?subject=Vertex%20order%20diagnosis). This is an inbound inquiry address, not a checkout or a promise of paid work. No commercial email is sent automatically. A reply about paid work requires a permitted business sending route.

This README does not collect or upload information. The email link opens your own email app; sending is your choice. No customer case studies, guaranteed fixes or platform affiliation are claimed. Remote work only.
