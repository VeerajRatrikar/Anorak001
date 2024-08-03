---
title: Crowdstrike Outage Explained
description: >-
 What caused one of the most biggest IT Outage in the history of mankind
author: anorak
date: 2024-07-25 00:35:00 +0530
categories: [ROOT,NEWS,OUTAGE]
tags: [Serious Issue]
pin: false
---
What might be considered the largest IT outage in history was triggered by a botched software update from security vendor CrowdStrike, affecting millions of Windows systems around the world. Insurers estimate the outage will cost U.S. Fortune 500 companies $5.4 billion.

## THE ISSUE:

- The outage occurred July 19, 2024, with millions of Windows systems failing and showing the infamous blue screen of death (BSOD).
- CrowdStrike, the company at the core of the outage, is an endpoint security vendor whose primary technology is the Falcon platform, which helps protect systems against potential threats in a bid to minimize cybersecurity risks.

- In many respects, the outage was a real manifestation of fears that computing users had at the end of the last century with the Y2K bug. With Y2K, the fear was that a bug in software systems would trigger widespread technology failures. 
- While the CrowdStrike failure was not Y2K, it was a software issue that did, in fact, trigger massive disruption on a scale that has not been seen before.

## What caused the outage?

![Crowdstrike Falcon](assets/img/202408/crowdstrike.jpeg){: width="800" height="400" .w-50 .right}

- The outage was not a Microsoft Windows flaw directly, but rather a flaw in CrowdStrike Falcon that triggered the issue.
  
- CrowdStrike Falcon is a cloud-based endpoint protection platform developed by CrowdStrike. It is designed to detect, prevent, and respond to a wide range of cybersecurity threats and attacks.
  
- Falcon hooks into the Microsoft Windows OS as a Windows kernel process. The process has high privileges, giving Falcon the ability to monitor operations in real time across the OS.
  There was a logic flaw in Falcon sensor version 7.11 and above, causing it to crash.
  Due to CrowdStrike Falcon's tight integration into the Microsoft Windows kernel, it resulted in a Windows system crash and BSOD.
  
- The flaw in CrowdStrike Falcon was inside of a sensor configuration update. The sensor is regularly updated -- sometimes multiple times daily -- to provide users with mitigation and threat protection.
  
- The flawed update was contained in a file that CrowdStrike refers to as "channel files," which specifically provide configuration updates for behavioral protections. Channel file 291 is an update that was supposed to help improve how Falcon evaluates named pipe execution on Microsoft Windows. Named pipes are a common type of communication mechanism for interprocess communications on Microsoft Windows.
  
  With channel file 291, CrowdStrike inadvertently introduced a logic error, causing the Falcon sensor to crash and, subsequently, Windows systems in which it was integrated.

- The flaw isn't in all versions of channel file 291. The problematic version is channel file 291 (C-00000291*.sys) with timestamp 2024-07-19 0409 UTC. Channel file 291 timestamped 2024-07-19 0527 UTC or later does not have the logic flaw.
  
- By that time, CrowdStrike had noticed its error and reverted the change. But, for many of its users, that reversion came too late as they had already updated, leading to BSOD and inoperable systems.


## What services were affected?

- Microsoft estimated that approximately 8.5 million Windows devices were directly affected by the CrowdStrike logic error flaw. That's less than 1% of Microsoft's global Windows install base.

But, despite the small percentage of the overall Windows install base, the systems affected were those running critical operations. Services affected include the following.

  1. Healthcare
  2. Airline and Airports
  3. Financial Services
  4. Media and Broadcasting

## Hackers take the advantage of the Outage:
- While the outage was not due to a cyberattack, threat actors have taken advantage of the incident.
  According to a [blog](https://www.crowdstrike.com/blog/falcon-sensor-issue-use-to-target-crowdstrike-customers) post from CrowdStrike, the security vendor has received reports of the following malicious activity:

  - Phishing emails sent to customers posing as CrowdStrike support.
  - Fake phone calls impersonating CrowdStrike staff.
  - Selling scripts claiming to automate recovery from the botched update.
  - Posing as independent researchers saying the outage was due to a cyberattack and offering remediation insights.
  


















