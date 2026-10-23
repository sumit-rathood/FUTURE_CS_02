# Phishing Email Detection & Awareness Report

**Intern:** Sumit Rathod  
**Assessment date:** 23 October 2026  
**Assessment type:** Static review of two publicly archived, anonymized training samples  
**Overall result:** Both samples are classified as **Phishing**, with different confidence and severity: F-01 is Medium risk / Moderate confidence; F-02 is High risk / High confidence. This is a sample-based learning exercise, not an assessment of the intern's own mailbox or a named organization.

## Executive summary

I reviewed two archived email examples without visiting embedded links or opening, downloading, or running attachments. Both use an unexpected document or voicemail theme to prompt a click or download. The voice-message sample also contains archived authentication results showing SPF failure, no DKIM result, and DMARC failure. The evidence supports a phishing classification for these samples. It does not show that any recipient clicked, entered credentials, or was compromised.

## Scope and method

- **In scope:** two public email files in the autinerd/phishing-mail-examples educational archive.
- **Method:** static review of archived message metadata and visible body text; sender/return-path consistency; message theme and requested action; available SPF/DKIM/DMARC results; visible HTML obfuscation indicators.
- **Out of scope:** live inboxes, recipient identities, visiting links, resolving domains, opening attachments, running scripts, sending messages, credential collection, or testing any live organization.
- **Privacy:** the archive anonymizes sample identities and infrastructure. This report keeps that redaction and does not repeat personal data.

## Findings summary

| ID | Sample | Classification | Risk / confidence | Main evidence |
|---|---|---|---|---|
| F-01 | “New fax message” | Phishing | Medium / Moderate | The archive identifies this as a phishing example; fax/document lure and “Print & Preview” prompt. Sender and Return-Path are anonymized, so original sender alignment cannot be verified. |
| F-02 | “Voice message” | Phishing | High / High | Archived SPF failure and DMARC failure, no DKIM result, unexpected voicemail/pass-key wording, attachment request, and concealed formatting characters in the HTML body. 

## Detailed findings

### F-01 — Unexpected fax/document link

**Risk:** Medium. **Classification:** Phishing (Moderate confidence).  
**What I observed:** The archive identifies this as a phishing example. The archived message presents a fax or shared-document theme and refers to services such as SharePoint/MetroFax. It asks the recipient to click a “Print & Preview” link. The sender and Return-Path are anonymized, so I could not verify their alignment to the claimed service. I did not open the link.

**Why it matters:** A document-themed prompt can persuade a recipient to visit a credential-collection page or another unsafe destination. The archive context and unexpected click prompt support the phishing classification, but anonymized sender details and an uninspected destination limit independent confirmation. No payload or compromise is claimed.

**Recommended response:** Do not click. Verify the fax or file through a known, independently obtained contact method. Report the message to the mail/security team, then remove it using the organization's process. If a link was already opened, contact IT/security promptly.

### F-02 — Fake voicemail and attachment prompt

**Risk:** High. **Classification:** Phishing (High confidence).  
**What I observed:** Archived Authentication-Results record SPF failure, no DKIM result, and DMARC failure. The subject and body use an unexpected voice-message/pass-key exception theme and ask the recipient to download an attachment. The HTML body contains invisible formatting characters inserted into words. The archive sample is anonymized. I did not retrieve or open the attachment.

**Why it matters:** Failed sender authentication reduces confidence that the message came from the claimed sender. An unexpected attachment can carry risk, while concealed text formatting may evade simple keyword checks. This is an indicator-based assessment; the attachment itself was not analyzed.

**Recommended response:** Do not download or open the attachment. Verify the voicemail using the organization's normal phone or messaging service, report the email, and delete/quarantine it under local policy. If opened, contact the response team immediately.

## Classification guide

- **Safe:** Evidence supports a legitimate message and the request is expected; verify unusual requests through a known channel. Neither sample qualifies as Safe.
- **Suspicious:** One or more warning signs exist, but evidence is incomplete. Preserve and escalate for review; do not click while uncertain.
- **Phishing:** Multiple credible indicators support an attempt to mislead the recipient into clicking, downloading, disclosing information, or taking an unsafe action. Both reviewed samples fit this category.

## Prevention checklist

**Do**
- Check the full sender address and whether the sending domain matches the claimed service.
- Treat unexpected invoices, shared files, fax notices, password alerts, and voicemail attachments cautiously.
- Verify requests through a known website, phone number, or internal contact, not details supplied in the message.
- Report suspicious messages using the organization's approved reporting process.
- Ask IT/security to review SPF, DKIM, and DMARC alignment and mail filtering for its own domain.
- Use multifactor authentication and a password manager; report suspected credential entry immediately.

**Don't**
- Click an unexpected sign-in, document-preview, or “listen now” link to find out where it goes.
- Open an unexpected attachment or enable macros/content.
- Trust a display name, logo, urgent tone, or familiar brand by itself.
- Forward a suspicious sample broadly; use the approved reporting channel.

## Limitations

This report reviews only two public training samples. It does not measure phishing prevalence, verify the current behavior of any destination, inspect attachments, or establish compromise. Sample addresses and infrastructure are anonymized in the source archive. High ratings describe likely risk if a recipient acts; they do not claim a live system was exploited.

## Sources

- Future Interns Task 2: https://futureinterns.com/cyber-security-task-2-2026/
- Archived sample F-01: https://github.com/autinerd/phishing-mail-examples/blob/main/new-fax-message/example1/message.eml
- Archived sample F-02: https://github.com/autinerd/phishing-mail-examples/blob/main/voice-message/example1/message.eml
- Archive context and anonymization: https://github.com/autinerd/phishing-mail-examples
- OWASP Web Security Testing Guide: https://github.com/OWASP/www-project-web-security-testing-guide