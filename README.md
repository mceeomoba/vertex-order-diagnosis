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

## Service status

The generic order-diagnosis service is paused. This repository remains a public reference checklist, not an active paid offer or a request for customer records. No store access, payment action or diagnosis turnaround is offered here.

Do not send credentials, customer records or production logs, and do not put private evidence in GitHub issues. For a live store problem, start with the platform or gateway's official support route.
