# Trigger 002 — Sequential when parallel

## Signal

Agent serializes independent operations (read, write, build, deploy,
commit) into one-at-a-time calls when they have no data dependency.

## User reactions that fire this class

- "You're slow"
- "You're sitting at the lowest common denominator"
- "Asynchronous, not sequential"
- "Stop processing me one thing at a time"

## Root cause

Default-to-sequential habit. Tool call planning that walks step by step
instead of recognizing independence.

## Repair

See `../repairs/002-sequential-when-parallel.md`.
