# Task 2 evidence log: archived phishing samples

**Review date:** 23 October 2026  
**Method:** Static review of archived message text and headers. No embedded destination was opened and no attachment was retrieved or opened.

## F-01 — Fax and document-preview message

**Source:** https://github.com/autinerd/phishing-mail-examples/blob/main/new-fax-message/example1/message.eml

**Observed evidence**

- The archived message presents a fax/document theme and prompts the recipient to use “Print & Preview”.
- The displayed From and Return-Path values use attacker.example.com, a reserved example domain in the archived sample. The placeholder values match each other in the sample; they do not establish the original sender's identity or alignment.
- The body claims that a fax is available and requests a click. The destination was not inspected.
- The source archive identifies the message as a phishing example.

**Assessment**

- Classification: Phishing
- Risk: Medium
- Confidence: Moderate

Confidence is limited because the sender infrastructure and destination are represented by placeholders or were not examined. The evidence does not establish credential theft, payload delivery, or recipient compromise.

## F-02 — Voicemail and attachment message

**Source:** https://github.com/autinerd/phishing-mail-examples/blob/main/voice-message/example1/message.eml

**Observed evidence**

- Archived Authentication-Results records SPF failure, no DKIM signature, and DMARC failure.
- The sample uses a voicemail/pass-key theme and asks the recipient to download an attachment.
- The sender and recipient fields use target.example.com; the sender IP is 192.0.2.1. These are placeholder values in the archived sample.
- The HTML body contains the entity &#8288; between characters in words. This entity represents an invisible word-joiner character.
- The attachment was not retrieved or inspected.

**Assessment**

- Classification: Phishing
- Risk: High
- Confidence: High

Multiple independent indicators support the classification. The attachment contents, live sending infrastructure, and recipient impact were not established.

## Evidence handling and limits

The archive describes its samples as anonymized educational examples. This log records only indicators needed to support the assessment; it does not reproduce full message bodies, contact-like values, or active destinations. The assessment concerns the archived samples only and does not assess any live organization.