# Aegis

**Communicate without collecting personal data.**

Aegis is a privacy-first lead communication product for the GDPR era.

Today, capturing a lead usually means asking for a name, email, or phone number just to start a conversation. That immediately creates collection, storage, security, consent, and compliance obligations.

Aegis changes the model. The customer receives a digital communication identity and uses it to message or call the business — without revealing a name, phone number, or email.

A customer visits a lead page and scans a QR code. A unique identity is created and installed in a compatible app such as Arnacon. From that moment, the business and the customer can communicate on that identity.

No phone number. No email. No name. No personal data required.

Lead generation becomes “give us permission to communicate with you,” not “give us your personal data so we can contact you.”

This repository is an index. The product lives in the four repositories below.

## Repositories

| Repository | Role |
| --- | --- |
| [Elead](https://github.com/cellact/Elead) | Studio website. Example lead page (allot a line, show the QR) and the provider console (domain, identities, inbox). |
| [elead-backend-gcp](https://github.com/cellact/elead-backend-gcp) | Cloud backend. Issues identities, serves QR payloads, verifies activation proofs, and routes a lead to the studio inbox. |
| [Elead-HTML](https://github.com/cellact/Elead-HTML) | In-app UI loaded by Arnacon. End-user chat (`elead`) and service-provider inbox (`sp-elead`), plus install, chat, and calls. |
| [swarm-gcp-vm](https://github.com/cellact/swarm-gcp-vm) | Swarm parts. Bee node on a GCE VM, plus startup and laptop-to-VM copy so the backend can reach Swarm. |

## How a lead flows

1. **Studio (`Elead`)** — the customer opens the lead page and asks for a private line. The provider console manages the domain and inbox.
2. **Backend (`elead-backend-gcp`)** — creates the identity and QR, later verifies the activation proof, and tells the lead app which inbox to write to.
3. **In-app HTML (`Elead-HTML`)** — Arnacon opens the install page, then chat (and calls) on that identity. The lead never gives a name, phone, or email.

Messaging and calls run through Arnacon. Swarm storage runs on `swarm-gcp-vm`. These repos own the Elead product on top of it.