# Roadmap

**English** · [Français](ROADMAP.fr.md)

What is planned for **Portunia**, **Portunia Gate** and **Portunia Assist**. No dates: the order can change with your feedback.

*Updated: 5 November 2026 · Portunia 0.70 · Portunia Gate 0.30*

## Now

What we are working on.

- **Real-world testing** of the latest features: Remote Desktop file copy, Proxmox VE (creating machines, managing nodes), web interfaces through the Gate, Remote Desktop in vault mode.
- **Signed installer**: no more Windows SmartScreen warning when downloading Portunia and Portunia Assist.
- **Watch a session live** from the Audit player, with a "Cut the session" button (and, optionally, disable the account).
- **Export a session as a video** (MP4) on demand, with subtitles and a watermark; each export is written to the audit log.

## Next

Planned afterwards, in roughly this order.

**Portunia Gate**

- **Access approval**: a rule can require an approver's consent, with a reason, a duration and a ticket number. Requests from Portunia or the web portal.
- **Alerts**: sensitive command, repeated sign-in failures, revealed input, altered log; by email, Microsoft Teams or signed webhook.
- **Single sign-on** (OIDC, SAML) for the Gate and the web portal.
- **Web portal**: passkeys, company logo, copy and paste set per rule.
- **Remote Desktop**: connect through the Gate from the Windows client (mstsc) and Remmina, as well as Portunia.

**Portunia**

- **New storage types** in two-pane file sessions: WebDAV, Windows shares (SMB), Azure Blob, Google Cloud Storage.
- **Resume interrupted transfers** and compare folders by content.
- **Detachable player**: replay a session in a separate window.
- **Remote Desktop**: server certificate remembered on the first connection, like SSH keys.

**Portunia Assist**

- **Invite with a link**, as well as the code read over the phone.
- **Chat, files and clipboard** during assistance.
- **Several monitors** and a **"Request administrator rights"** button (Windows elevation).
- **History** of assistance sessions, on both sides.
- **Android**: control of the device (view only today).

## Later

Under consideration, to be refined.

- **Portunia on macOS and Linux**: the same application, with the same protocols, connection through a Gate and administration.
- **End-to-end encrypted sync** of your sessions between your computers, Windows, macOS or Linux.
- **Sharing sessions and credentials** within a team, with permissions and central deployment.
- **Automatic rotation** of the passwords kept in the Gate's vault.
- **Unattended access** to your own PCs ("My PCs") with Portunia Assist, and your company logo for your customers.
- **Portunia Assist on macOS and Linux.**
- **Third-party extensions** in the catalogue: downloaded, signed and isolated.

## Recently delivered

- **0.70**: Proxmox VE, creating virtual machines and containers, managing nodes (updates, services, log, network, disks).
- **0.69**: Remote Desktop file copy, controlled and logged by the Gate.
- **0.66 to 0.68**: Proxmox VE in the sidebar, with monitoring.
- **0.67**: web interfaces (vCenter, iDRAC, firewalls…) opened through the Gate.
- **0.65**: Remote Desktop in vault mode (the Gate supplies the Windows account), Remote Desktop options (resolution, RD gateway, RemoteApp…).

Details of each version are on the [releases page](https://github.com/jpiperault/Portunia-releases/releases).

## Your feedback

Missing a feature, or would you order things differently? Open an [issue](https://github.com/jpiperault/Portunia-releases/issues): the most shared requests go first.
