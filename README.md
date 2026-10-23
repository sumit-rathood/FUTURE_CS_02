# Task 2: Phishing Email Analysis

**Assessment date:** 23 October 2026  
**Assessment type:** Static review of two archived, anonymized training messages

## Deliverables

- [Assessment report](Report.pdf)
- [Markdown report](Report.md)
- [Sample analysis evidence](evidence/sample-analysis.md)

## Scope and method

Two message samples from the public autinerd/phishing-mail-examples archive were reviewed. The assessment covered visible message content, sender fields, authentication results where recorded, and indicators in the HTML body. Embedded links were not opened. Attachments were not downloaded or opened. No live mailbox, recipient, or mail server was tested.

## Findings

| ID | Classification | Risk | Confidence |
|---|---|---|---|
| F-01 | Phishing | Medium | Moderate |
| F-02 | Phishing | High | High |

F-01 uses an unexpected fax and document-preview prompt. The archived sender fields use a reserved example domain, so the original sender identity cannot be verified. F-02 includes failed SPF and DMARC results, no DKIM signature, an unexpected attachment prompt, and concealed formatting characters in the message body.

## Evidence and sources

The evidence log records the reviewed indicators and source locations. Sample text is summarized rather than republished in full.

- [F-01 source message](https://github.com/autinerd/phishing-mail-examples/blob/main/new-fax-message/example1/message.eml)
- [F-02 source message](https://github.com/autinerd/phishing-mail-examples/blob/main/voice-message/example1/message.eml)
- [Archive context](https://github.com/autinerd/phishing-mail-examples)

## Canva report

Editable report design: [Open in Canva](https://www.canva.com/d/MXSMO60yJAcFews)

