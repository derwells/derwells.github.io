---
title: "Adaptive Sender for Custom Protocol over UDP"
excerpt: "Created an efficient sender-side program for a custom protocol built over UDP. Simulated restrictions include: payload size, queue size, and processing delay."
collection: projects
share: False
---

This is a capstone project for CS 145 -- an undergraduate networking class.

Given an abstracted receiver, we were tasked with make a sender program for a custom reliable protocol built over UDP. The sender must be able to successfully deliver a given payload in under 120 seconds. Projects that consistently send under 90 seconds are given a bonus.

To simulate real-world congestion, the receiver places static but hidden restrictions on payload size, queue size, and processing delay. Payloads that don't match these restrictions are dropped by the receiver.

Note that sender programs are tested in a *controlled environment*.

## Solution

The sender protocol is a stop-and-wait protocol with a sending window of size 1. It retransmits after a dynamic timeout period.

### Big Idea

The hidden restrictions guarantee that a payload can be sent within a 90-second time-limit. Therefore we can reliably estimate the max payload size $p$ to be:

$p = \big\lceil n_{\text{chars}} \big/ \big(\big\lfloor\frac{90 - d_{\text{rtt}}}{d_{\text{rtt}}}\big\rfloor\big)\big\rceil$

where $n_{\text{chars}}$ is the total number of characters in the given payload and $d_{\text{rtt}}$ is the round-trip-time (payload ack'd).

$n_{\text{chars}}$ is already known given the payload. $d_{\text{rtt}}$ is estimated by sending a packet with a single character. This guarantees that the packet is always ack'd.

### Other quirks

The sender program can recognize whether ack's correspond to a retransmitted packet or not.

## Source code and Documentation

Being a course requirement, source code and documentation will only be *given upon request*.
