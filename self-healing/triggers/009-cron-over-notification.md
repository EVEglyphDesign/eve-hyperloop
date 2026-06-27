# Trigger 009 — Cron-agent over-notification

## Signal

A background cron agent self-reports sending a notification when its
own threshold evaluation says no material triggers fired.

## Patterns that fire this class

- Cron escalation message naming the false positive
- Cron tracking files showing thresholds NOT met but notification sent
- User receives an in-app alert that contradicts the body's own metrics

## Root cause

Background cron agent's notification logic decoupled from its
threshold evaluation. The agent reasons about evidence and then
triggers the notification path on a softer rule than the spec.

## Repair

See `../repairs/009-cron-over-notification.md`.
