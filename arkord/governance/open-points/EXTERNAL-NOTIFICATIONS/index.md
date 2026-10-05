---
id: 'EXTERNAL-NOTIFICATIONS'
type: 'hybrid-agile.open-point'
title: 'V1 External Notification Scope'
summary: 'Whether V1 adds email or push notifications or remains limited to notifications within the application.'
status: 'OPEN'
relations:
  relatedTo:
    - 'IN-APP-NOTIFICATIONS'
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# V1 External Notification Scope

## Problem

It is unresolved whether V1 includes email or push notifications or remains limited to notifications within the application.

## Source of Uncertainty

In-application notification visibility is established for V1, while external notification channels are identified only as a possible future evolution.

## Project Impact

The decision affects the V1 notification experience and the expectations placed on users to enter Mainty to see operational events.

## Technical Impact

Including an external channel would introduce channel-specific delivery behavior and dependencies; excluding it leaves the established in-application boundary unchanged.
