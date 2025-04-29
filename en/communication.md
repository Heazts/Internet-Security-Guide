# Secure Communication: Email and Messengers

Our digital communications, whether emails or instant messages, contain personal, professional, and intimate information. Protecting these conversations against interception, surveillance, and unauthorized access is fundamental. This section explores how to choose and use email and messenger services focused on security and privacy.

## Secure and Private Email

Email is an essential communication tool, but the traditional model has significant privacy flaws.

**Problems with Traditional Email (Gmail, Outlook, Yahoo, etc.):**

*   **Lack of Default End-to-End Encryption (E2EE):** Most emails are not end-to-end encrypted. Although the connection to the server might be encrypted (TLS), the email provider (Google, Microsoft) can read the content of your messages. They do this to scan for spam and malware, but also to collect data for targeted advertising (in Gmail's case, for example).
*   **Exposed Metadata:** Even if the content were encrypted, metadata (sender, recipient, subject, date, time, IPs) usually isn't. This metadata reveals who you communicate with and when.
*   **Insecure Storage:** Your emails are stored on the provider's servers, potentially accessible to employees, hackers (in case of a breach), or governments (through legal orders).

**Criteria for Choosing a Secure Email Provider:**

*   **End-to-End Encryption (E2EE):** The provider should offer automatic E2EE for emails between its users and, ideally, easy integration with PGP/GPG for communication with external users.
*   **Zero-Access Encryption (Zero-Knowledge):** The provider should not have access to the encryption keys protecting your stored emails. Only you (with your password) can decrypt them.
*   **Jurisdiction:** Providers based in countries with strong privacy laws (like Switzerland or Germany) are preferable.
*   **Privacy Policy and Data Collection:** Should collect the minimum information necessary to operate the service and have a clear policy on how data is handled.
*   **Open Source:** Open-source client applications (web, mobile, desktop) allow for independent auditing.
*   **Tracking Protection:** The webmail should not include trackers in emails (tracking pixels).
*   **Infrastructure Security:** Good security practices on the provider's servers.

**Recommended Email Providers:**

*   **Proton Mail:**
    *   **Pros:** Based in Switzerland, automatic E2EE between Proton users, zero-access encryption for stored emails, open source (clients), good reputation, offers a free plan.
    *   **Cons:** PGP integration with external users requires a paid plan, some advanced features are paid.
    *   [![Proton Mail](https://img.shields.io/badge/Email-Proton%20Mail-8B5AEB?style=for-the-badge&logo=protonmail&logoColor=white)](https://proton.me/mail)
*   **Tutanota:**
    *   **Pros:** Based in Germany, automatic E2EE between Tutanota users (using AES/RSA, not PGP), zero-access encryption, open source (clients), focused on ease of use, free plan.
    *   **Cons:** Does not support standard PGP (uses its own encryption system for external users via password), fewer features than Proton Mail in some aspects.
    *   [![Tutanota](https://img.shields.io/badge/Email-Tutanota-008174?style=for-the-badge&logo=tutanota&logoColor=white)](https://tutanota.com/)
*   **Mailbox.org:**
    *   **Pros:** Based in Germany, strong focus on privacy and security, easy PGP integration in webmail (client-side encryption), offers a full suite (calendar, contacts, cloud storage), uses green energy.
    *   **Cons:** No free plan (but affordable), interface might seem a bit dated to some.
    *   [![Mailbox.org](https://img.shields.io/badge/Email-Mailbox.org-004488?style=for-the-badge)](https://mailbox.org/)

**PGP/GPG (Pretty Good Privacy / GNU Privacy Guard):**

PGP/GPG is an open and widely used standard for encrypting and digitally signing emails and files. It uses asymmetric encryption.

*   **Concept:** Each user generates a key pair: a **public key** (which can be shared freely) and a **private key** (which must be kept absolutely secret).
    *   To send an encrypted email to someone, you use their *public key*.
    *   To decrypt a received email, you use your *private key*.
    *   To digitally sign an email (prove it was you who sent it and that it wasn't altered), you use your *private key*. The recipient verifies the signature using your *public key*.
*   **How it Works:** PGP encryption protects the *content* of the email, but not the metadata (sender, recipient, subject).
*   **Tools:**
    *   **Desktop Email Clients:**
        *   **Thunderbird:** Popular open-source email client that now has native OpenPGP support (the standard implementation of PGP/GPG). Easy to set up and manage keys.
        *   [![Thunderbird](https://img.shields.io/badge/Email_Client-Thunderbird-0A84FF?style=for-the-badge&logo=thunderbird)](https://www.thunderbird.net/)
    *   **Dedicated Software:**
        *   **Gpg4win (Windows):** Suite including GPG tools and plugins for email clients like Outlook.
        *   **GPG Suite (macOS):** GPG integration with Apple Mail and other system tools.
*   **Key Management:** The biggest challenge with PGP is securely managing private keys and exchanging/verifying public keys (to prevent man-in-the-middle attacks). Use strong passphrases to protect your private key and verify the authenticity of public keys you import (e.g., through alternative communication channels).

**Email Aliases:**

Even when using a secure provider, you might want to hide your primary email address when signing up for different online services. Email aliases help with this.

*   **What they are:** Disposable or forwarding email addresses that redirect messages to your main inbox. You create a unique alias for each site/service.
*   **Benefits:**
    *   **Privacy:** The site doesn't know your real email.
    *   **Spam Control:** If an alias starts receiving spam, you know which service leaked/sold your address and can disable the alias.
    *   **Organization:** Helps filter and organize emails.
*   **Recommended Services:**
    *   **SimpleLogin (now part of Proton):**
        *   **Pros:** Open source, integrates with Proton Mail, allows sending emails *from* the alias, offers custom domains, generous free plan.
        *   **Cons:** Reliance on a centralized service (though self-hosting is possible).
        *   [![SimpleLogin](https://img.shields.io/badge/Alias-SimpleLogin-4C1ED4?style=for-the-badge)](https://simplelogin.io/)
    *   **AnonAddy:**
        *   **Pros:** Open source, similar to SimpleLogin, offers self-hosting, free plan.
        *   **Cons:** Interface might be less polished than SimpleLogin.
        *   [![AnonAddy](https://img.shields.io/badge/Alias-AnonAddy-336DEC?style=for-the-badge)](https://anonaddy.com/)
    *   **DuckDuckGo Email Protection:** Free service providing an `@duck.com` alias and removing trackers from emails before forwarding.

## Secure Messengers

Just like email, many popular messaging apps (like Facebook Messenger, Instagram DMs, SMS) lack adequate security and privacy. Secure messengers use end-to-end encryption (E2EE) to protect your conversations.

**Criteria for Choosing a Secure Messenger:**

*   **E2EE by Default:** End-to-end encryption must be enabled by default for all conversations, not a hidden option (like Telegram's "secret chats").
*   **Strong and Open Encryption Protocol:** The Signal Protocol is considered the current gold standard, being audited and widely adopted. Proprietary or unaudited protocols are a risk.
*   **Minimal Metadata Collection:** The service should collect as little information as possible about who talks to whom, when, and from where (metadata). Ideally, no metadata that can link users.
*   **Open Source:** Client applications should be open source to allow auditing.
*   **Security Audits:** The software should have undergone independent security audits.
*   **No Phone Number Requirement (Ideal):** Linking the account to a phone number can be a privacy risk. Messengers using anonymous IDs are preferable for certain threat models.

**Analysis of Popular Messengers (Security Focus):**

*   **Signal:**
    *   **Pros:** Considered the gold standard. E2EE by default for all conversations (using the Signal Protocol), open source, developed by a non-profit foundation, minimal metadata collection (only last access date and registration date), features like disappearing messages.
    *   **Cons:** Requires a phone number for registration (though they are working on username alternatives).
    *   [![Signal](https://img.shields.io/badge/Messenger-Signal-3A76F0?style=for-the-badge&logo=signal)](https://signal.org/)
*   **Session:**
    *   **Pros:** Signal fork focused on anonymity, does not require a phone number (uses randomly generated IDs), routes messages through a decentralized network (similar to Tor) to hide IPs, E2EE.
    *   **Cons:** Routing network can be slower, development less mature than Signal.
    *   [![Session](https://img.shields.io/badge/Messenger-Session-00A58E?style=for-the-badge)](https://getsession.org/)
*   **Briar:**
    *   **Pros:** Focused on security and resilience, especially for activists and journalists. Does not rely on central servers. Can sync messages directly between devices via Wi-Fi or Bluetooth (useful in scenarios without internet or with network surveillance), or through the Tor network. Does not require a phone number.
    *   **Cons:** Only works on Android, less polished interface, synchronization can be slow.
    *   [![Briar](https://img.shields.io/badge/Messenger-Briar-4CAF50?style=for-the-badge)](https://briarproject.org/)
*   **Element (using the Matrix protocol):**
    *   **Pros:** Based on the open and decentralized Matrix protocol. Allows choosing your own server (or hosting one), offers E2EE (though it needs to be enabled in rooms), interoperability with other networks (via bridges), open source.
    *   **Cons:** E2EE can be complex to manage (device verification), usability might be less intuitive for beginners, performance can vary depending on the server.
    *   [![Element](https://img.shields.io/badge/Messenger-Element-0DBD8B?style=for-the-badge&logo=element)](https://element.io/)

*   **Messengers to Avoid (Privacy/Security Perspective):**
    *   **WhatsApp:** Although it uses the Signal Protocol for E2EE, it belongs to Facebook (Meta), which has a poor privacy track record. Collects a lot of metadata.
    *   **Telegram:** Conversations are *not* E2EE by default (only "secret chats"). Normal and group chats are stored on Telegram's servers and can be accessed by the company. Uses its own encryption protocol (MTProto), which has received criticism from experts.
    *   **Facebook Messenger / Instagram DMs:** No E2EE by default, belong to Meta.
    *   **SMS:** Completely insecure, no encryption, easily interceptable.

**Additional Risks in Messengers:**

*   **Device Security:** Even with E2EE, if your device is compromised (malware, physical access), your messages can be read.
*   **Metadata:** Even if the content is secure, some messengers still collect metadata (Signal collects minimal, WhatsApp collects a lot).
*   **Backups:** Cloud backups (Google Drive, iCloud) are generally *not* E2EE by default (although WhatsApp and Signal are implementing optional E2EE backups). If the backup is not E2EE, it can be a weak point.

By carefully choosing your email providers and messaging apps, prioritizing end-to-end encryption and minimizing data collection, you take an important step towards protecting your digital communications.

