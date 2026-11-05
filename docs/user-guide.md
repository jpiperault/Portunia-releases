# User guide

*Portunia 0.71.0 · Portunia Gate 0.31.0 · Updated: 5 November 2026*

> The Portunia Gate administration guide is in [Portunia-Gate-releases](https://github.com/jpiperault/Portunia-Gate-releases/blob/main/docs/administration-guide.md). Version française : [guide d'utilisation](guide-utilisation.md).

Connect to your servers with Portunia, transfer files, work through a Gate, use the web portal, and give or receive remote help. No administration knowledge is needed.

<a id="bienvenue"></a>

## 1\. Which chapter is for you?

Portunia brings your connections together in a single Windows window. This guide is for several kinds of readers; go straight to the part that concerns you.

| You are | Start with |
| --- | --- |
| A user on your own, with your own servers | [Installing](#installer), [First connection](#premiere), then [Sessions](#sessions). |
| An employee whose company has a Gate | [Installing](#installer), then [Connecting through a Gate](#Gate). |
| A user without Portunia, on another computer | [The web portal](#portail). |
| A helper | [Helping someone](#depanner). |
| Someone getting help | [Getting help](#aide). You need nothing else. |

> [!NOTE]
> **Administrators** — Creating accounts, adding servers and setting rights are described in the administration guide.

### Useful words

| Word | Meaning |
| --- | --- |
| Session | A saved connection: address, user name, settings. It opens in a tab. |
| Host | The machine's address: a name (`srv-01.example.com`) or an IP address (`10.0.0.12`). |
| Gate | The company server that all connections go through. It checks who you are and what you are allowed to open. |
| Code | The 6 digits that change every 30 seconds in the authenticator app on your phone. |
| Fingerprint | A machine's digital identity. It lets you check that you are talking to the right server. |
| Extension | In Portunia, each protocol is an extension that can be enabled or disabled. |

<a id="installer"></a>

## 2\. Installing Portunia

1.  Download `Portunia_x.y.z_x64-setup.exe` from [the releases page](https://github.com/jpiperault/Portunia-releases/releases), or from the link your company gave you.
2.  Open the file and choose: **just for me** (no administrator rights, in your Windows profile) or **for all users of this PC** (in Program Files, administrator rights asked). Updates keep this choice; an installation for all users asks for Windows' permission at each update.
3.  If Windows SmartScreen warns you, click "More info", then "Run anyway". The installer does not have a code-signing certificate yet.
4.  Start Portunia. It appears in the Windows language, English or French.

Portunia checks for updates when it starts. A banner offers the new version; nothing is installed without your consent. Your sessions and settings are kept.

### Editions

| Edition | Includes |
| --- | --- |
| **Free** | Connections, terminal, files, tunnels, network tools, locking. |
| **Pro** | Also: monitoring alerts, server dashboard, command on several servers, containers, session recording, S3 storage. |
| **Teams** | Also: administration and audit of a Gate. |

> [!NOTE]
> **Preview** — During this period, every feature is unlocked in every edition.

<a id="premiere"></a>

## 3\. First connection

### The fastest way: quick connect

1.  Press Ctrl+Shift+Q.
2.  Type the address, for example `deploy@10.0.1.12` or `rdp srv-01`.
3.  On the first SSH connection, Portunia shows the server's fingerprint. Accept it if you have checked it or if you are on your own network.
4.  Type the password if the server asks for one.

Nothing is saved. The connection stays in the recent history, and "Save as a session" keeps it for next time.

### For a machine you use often: a session

1.  Ctrl+Shift+N opens "New session".
2.  Choose the protocol, give a name, enter the host and the user.
3.  Save, then double-click the session in the sidebar.

> [!NOTE]
> **Password** — Leave the field empty to be asked at each connection. If it is filled in, it goes to the Windows Credential Manager, never to a plain-text file.

<a id="fenetre"></a>

## 4\. The window at a glance

| Area | Purpose |
| --- | --- |
| Rail (column of icons on the left) | Chooses the panel shown: **Sessions**, **Gates**, **This PC** (local shells). Below: saved commands, shared credentials, recordings, assistance, network tools, import; at the bottom, extensions and settings. Clicking the icon of the open panel collapses the sidebar. |
| Sessions panel | The filter, the chips, **pinned** and **recent** sessions, then your folders; at the bottom, "All sessions in a table". |
| Tabs | One connection per tab. Ctrl+Shift+W closes the active tab. |
| Tab toolbar | Always on one line: the connection's address, then the actions (commands, search, recording, split screen, tunnels, SSH key, edit), the **panels** group (Files, Notes, Server, Containers) and Disconnect. When the window gets narrower, the labels disappear (the name stays as a tooltip), then the rarely used actions move to the **⋯** menu. |
| Right-hand panel | Opened from the panels group; its tabs switch between Files, Notes, Server and Containers, and the cross closes it. In a narrow window, it opens over the terminal. |
| Status bar | The edition and the version. Click it to reach the licence in Settings. |

### The palette: find everything from the keyboard

Ctrl+Shift+O opens a list with your sessions, your local shells and Portunia's actions. Type a few letters, then Enter. If you type an address, Portunia offers to connect to it. It is also the shortest way to Settings, SSH keys or Network tools.

<a id="sessions"></a>

## 5\. Sessions and folders

Put your sessions in nested folders and drag them from one to another. Right-click shows the available actions.

| On | Right-click |
| --- | --- |
| A session | Open, Pin to the top, Edit, Duplicate, Move out of the folder, Delete, Ping, traceroute, ports…, Wake up (Wake-on-LAN, if a MAC address is filled in). |
| A folder | New session here, New subfolder, Rename, Colour…, Run a command on this folder… (Pro), Delete the folder. |

> [!WARNING]
> **Tip** — Give your production folder a red colour. Its sessions get a clearly visible banner, and the command on several servers asks for a stronger confirmation.

### Several sessions at once

-   **Split screen**: up to 4 sessions side by side (toolbar button, or "Show beside the active tab" on a tab).
-   **Multi-input** (Ctrl+Shift+B): what you type goes to every session shown. The button changes to "Multi-input: ON"; check it before typing a command.

### Finding a session among many

-   Ctrl+Shift+K puts the cursor in the filter. Type a few letters of the name, address, folder or a tag: the list becomes flat, with the address and folder under each name. Enter opens the first one, ↓ moves through the list, Esc clears the filter.
-   **Chips** under the filter: Connected, Pinned, a protocol (SSH, RDP…) or one of the most used tags. A second click on the chip removes it.
-   **Pin** (star on hover, or right-click): the session stays at the top of the panel. The last 5 sessions opened appear under **Recent**.
-   The filter also applies to the Gates' servers: a line "N server(s) in the Gates" leads to the Gates panel.
-   **All sessions in a table** (at the bottom of the panel, or from the palette): a tab you can sort by name, address, protocol, folder, tags or last opened, with filters by folder, protocol and tag. Tick several sessions to open them together or run a command on them (Pro). Double-click or Enter opens a session, F2 edits it.

<a id="protocoles"></a>

## 6\. Connecting to each kind of machine

A disabled extension disappears from the menus, but its sessions are kept. To enable one again: palette, then "Extensions".

SFTP and FTP / FTPS are in the **catalogue**, at the bottom of the Extensions page: click "Install" to add them to the "New session" window. If you already had FTP sessions, the extension is installed automatically.

| Protocol | For | To fill in |
| --- | --- | --- |
| **SSH** | Linux servers, network equipment. | Host, user, authentication: private key, password or agent (Pageant, OpenSSH). |
| **Remote Desktop** | Windows. | Host, `DOMAIN\user`, display in a tab or in the Windows client. In a tab, Portunia requires NLA, as Windows does by default: a fake server cannot obtain your password. For a trusted server that does not offer it (xrdp on Linux, old Windows), tick "Accept servers without NLA". |
| **VNC** | Linux, macOS, Raspberry Pi. | Host and port. |
| **Local shell** | PowerShell, Command Prompt, WSL, Git Bash on this PC. | Nothing: **This PC** panel in the rail, or Ctrl+Shift+T for the default shell. "Open as administrator" uses a separate window. |
| **Telnet** | Old equipment. | Host. Telnet is not encrypted: keep it for the local network. |
| **Serial port** | Microcontrollers, switch and router consoles. | COM port, speed. Portunia offers the ports that are present. |
| **SFTP** | Files on a Linux server, without a terminal. | Like SSH: host, user, key, agent or password, jump host. Optional start folders on the server and on this PC. |
| **FTP / FTPS** | File servers. | Host, credentials. Explicit FTPS is the default; implicit FTPS uses port 990. Active mode and Windows-1252 encoding for old servers. |
| **S3 storage** Pro | AWS, MinIO, Scaleway, OVH, Wasabi, R2. | Endpoint, access keys. Uploads up to 5 GB per file. |
| **Web interface** | NAS, router and hypervisor consoles. | The address. The page opens in a window isolated from Portunia. |

### Useful SSH options

| Option | When to use it |
| --- | --- |
| Jump host | The machine can only be reached through another one. Enter an SSH session or `user@host:port`, up to 3 levels. |
| Compatibility with older equipment | An old device refuses the connection. The option allows weak algorithms; enable it only for that device. |
| Show graphical applications (X11) | You start a graphical application on the server. You need an X server on this PC, such as VcXsrv or X410. |
| MAC address | To wake the machine up with Wake-on-LAN. |

<a id="terminal"></a>

## 7\. The terminal

| To | Do |
| --- | --- |
| Copy, paste | Right-click: with a selection it copies, without one it pastes, like PuTTY. Can be changed in Settings. |
| Search the text | Ctrl+Shift+F. |
| Change the text size | Ctrl + mouse wheel. |
| Open a link | Ctrl + click. A simple click selects. |
| Reconnect | "Reconnect" button or Enter. After a network cut or sleep, Portunia reconnects by itself. |

Portunia's shortcuts all start with Ctrl+Shift. Ctrl+W, Ctrl+K and the others are left to the programs in the terminal, such as vim or nano.

Before pasting several lines, Portunia asks for confirmation: a paste can run commands without you pressing Enter. Errors stand out in red, warnings in orange, successes in green and IP addresses in cyan. These rules can be changed in Settings.

<a id="fichiers"></a>

## 8\. Files and transfers

In an SSH session, open the **Files** panel to the right of the terminal. To have only the files, right-click the SSH session, then "Open as files only (SFTP)": its settings (key, jump host) are used as they are.

SFTP, FTP and S3 sessions open in **two panes**: **This PC** on the left, the server on the right, the transfer queue at the bottom.

### Two panes

| Action | How |
| --- | --- |
| Select several files | Ctrl+click, Shift+click, or Ctrl+A in a pane. |
| Upload to the server | Arrow → or F5. Double-clicking a file on this PC does the same. |
| Download to this PC | Arrow ← or F6, into the folder open on the left. Double-clicking a file on the server does the same. |
| File already there | The queue's "If the file exists" rule: ask, replace if newer, replace, skip. "Ask" asks a single question for the whole selection. |
| Follow the transfers | Progress and speed in the queue. "Pause" stops starting the next ones; the cross removes a waiting transfer. |
| Hidden files | "Hidden files" button: files starting with a dot, and Windows hidden files. |

### Compare and synchronise Pro

The **Compare and synchronise** button of the two panes compares the folder open on this PC with the one on the server, subfolders included. The comparison copies nothing: it lists the differences and the reason for each one.

| Setting | Effect |
| --- | --- |
| Direction | **Upload** brings the server up to date, **Download** brings this PC up to date, **Both ways** copies each file to the side where it is older or missing. |
| Compare by | Date and size (recommended), or size only when the clocks are not reliable. |
| Exclude | Patterns separated by spaces: `.git/` for a folder, `*.log` for names, `dist/*.map` for a path. |
| Delete on the server | Upload only, unticked by default: removes from the server what no longer exists on this PC, after confirmation. Nothing is ever deleted on this PC. |

Lines in orange need a decision: same date but different content, or a file on one side and a folder on the other. Choose "Upload", "Download" or "Ignore". A newer file on the destination side is not ticked automatically. "Synchronise" puts the copies in the transfer queue; both panes reload at the end. Copies keep the original's date (in FTP, if the server accepts MFMT; not in S3), so a new comparison sees them as identical.

### Files panel of an SSH session

| Action | How |
| --- | --- |
| Upload | Drop files or folders on the panel, or use "Upload files" and "Upload a folder". |
| Download | Double-click a file, or "Download the whole folder". |
| Rename, delete | F2, Del. |
| Create a folder | "New folder". |
| Edit in place | "Open in my editor". The file opens on your PC and goes back to the server at each save, until "Stop syncing" or the session closes. |

> [!NOTE]
> **Executable files** — For your safety, Portunia refuses to open for editing the types Windows would run, such as `.exe`, `.bat`, `.js` or `.lnk`.

<a id="tunnels"></a>

## 9\. Tunnels

A tunnel carries another connection through an SSH session. Set it up from the tab's **Tunnels** button, or in the session so it opens at each connection.

| Type | Equivalent | Example |
| --- | --- | --- |
| Local port | `ssh -L` | Port 5432 on this PC leads to a database behind the server. |
| SOCKS proxy | `ssh -D` | Your browser goes through the server to reach internal sites. |
| Remote port | `ssh -R` | The server reaches an application running on your PC. |

Ports on your PC only listen on `127.0.0.1`: other machines on the network cannot use them.

<a id="ecran"></a>

## 10\. Remote Desktop and VNC

| Button | Effect |
| --- | --- |
| Ctrl+Alt+Del | Sends the combination to the remote machine. Typed on the keyboard, it would go to your own Windows. |
| Clipboard | VNC: copies the Windows clipboard to the remote screen. In Remote Desktop, copied text goes across by itself in both directions. |
| Upload files 0.69 | Remote Desktop: choose files on this PC (or drop them on the screen), then paste them in the server's Explorer with Ctrl+V. A message tells you when each file has been read. |
| Get the files 0.69 | Appears when files are copied (Ctrl+C) in the server's Explorer: choose a folder on this PC and they are saved there (a name already taken becomes "name (2)"). |
| Fit to window / Real size | Fits the image to the tab, or shows it at its own size with scrolling. |

In Remote Desktop in a tab, the remote desktop adapts to the size of the tab. Choose "Windows client (mstsc)" for full screen, all your monitors, or if a feature is missing in the tab.

Through a Gate, the file buttons only appear if your administrator allows file copy on that server (Gate 0.28 and later); each copied file is logged there with its name, size and SHA-256 fingerprint. Copying and pasting text remains possible in every case.

### Remote Desktop options (Portunia 0.65)

| Option | Tab | Windows client | Detail |
| --- | --- | --- | --- |
| Resolution | Yes | Yes | "Fit the tab or window" (default) or a fixed size (1280 × 720 to 2560 × 1440): the image is then scaled. |
| Colours | Yes | Yes | 32, 24 or 16 bits; 16 bits lightens a slow link. |
| Play the server's sound here | Yes | Yes | Enabled by default. |
| Remote Desktop Gateway | Yes | Yes | Servers reached through an RD gateway (HTTPS, port 443 by default). Without a gateway account, the server's credentials are also used for it. The Windows client asks for the gateway password itself. |
| Share drives, printers | — | Yes | This computer's disks and printers appear in the session. |
| Administration session (console) | — | Yes | Like `mstsc /admin`. |
| RemoteApp | — | Yes | The window of a single program (path on the server, or published `\|\|alias`) instead of the whole desktop. The server must allow that program. |

In VNC, the resolution stays the server's.

<a id="commandes"></a>

## 11\. Commands, notes, credentials

### Saved commands

Ctrl+Shift+P opens your commands. A command applies to one session, one folder or everywhere, and accepts variables such as `{{host}}` and `{{username}}`.

### Notes

Each session has its own notes in Markdown: procedures, contacts, keywords. Checkboxes can be clicked and code blocks can be sent to the terminal.

### Shared credentials

When several SSH, Remote Desktop or VNC sessions use the same account, create a shared credential and choose it in each of them. The day the password changes, you change it only once.

<a id="cles"></a>

## 12\. SSH keys

A key replaces the password and resists attacks much better. Palette, then "SSH keys".

1.  Open a session on the server with your password.
2.  Click the tab's **SSH key** button: "Create an SSH key and install it on this server".
3.  Keep Ed25519 (recommended) and choose a passphrase.
4.  Portunia installs the key, fixes the permissions and switches the session to the key.

> [!WARNING]
> **Public part only** — "Copy the public key" gives the text to hand over. The private key file, without the `.pub` extension, is never shared.

<a id="outils"></a>

## 13\. Network tools and monitoring

| Tool | Use |
| --- | --- |
| Ping, traceroute | Does the machine answer, and which way does the route go? No administrator rights are needed. |
| Port test | Which TCP ports are open: lists and ranges accepted, services recognised. |
| DNS | Resolve a name. |
| Wake-on-LAN | Wake a machine up. |

**Monitoring** checks whether your servers answer (every 30 seconds, minute or 5 minutes). A green or red dot and the latency appear in the tree, with an overview in "Server monitoring". The option "Notify me when a server goes down or comes back" is Pro only.

<a id="pro"></a>

## 14\. Pro features

| Feature | What it brings |
| --- | --- |
| Dashboard | Processor, memory, disks, load, active processes and failed services of a Linux server, read every 5 seconds. "View" opens a service's log. |
| Command on several servers | The same command on chosen sessions or a folder, 8 servers at a time. Results side by side, with a filter for failures. |
| Containers | The server's Docker, Podman and Kubernetes pods: shell, logs, start, stop, restart. |
| Recording | The tab's **Record** button keeps the terminal session. Palette, then "Recordings" to replay it, with speed and navigation. |
| Proxmox VE | Proxmox servers in their own section (see below). |

<a id="proxmox"></a>

### Proxmox VE (Portunia 0.66)

Install the **Proxmox VE** extension from the catalogue (Extensions › Catalogue, Pro plan; Portunia 0.67.1): a **Proxmox** icon appears in the left bar. **+** adds a server: its address (port 8006 by default), then the **certificate fingerprint** to compare with Proxmox's (node › System › Certificates), the user (`root@pam`, `admin@pve`…) and an **API token** (recommended: Datacenter › Permissions › API Tokens, without "Privilege Separation" to keep the user's rights) or a password. The secret stays in the Windows Credential Manager. An account with two-factor authentication needs a token. Several servers or clusters can be added.

A token created with "Privilege Separation" has **no rights** until it is given some, even for `root@pam`: Proxmox then shows the node but no machine, and Portunia shows "No right to see the machines". Give it a permission: Datacenter › Permissions › Add › API Token Permission, path `/`, role `PVEVMAdmin` (or `PVEAuditor` to only look), then **Refresh**.

Proxmox **does not open consoles with an API token** (machines, containers, node shells): the console ticket is tied to a user. With a token, also fill in **Password for consoles** (the user's, e.g. `root@pam`) in the server's form ("…" › Edit); Portunia checks it when saving, keeps it in the Windows Credential Manager and only uses it to open consoles (Portunia 0.70.1). Everything else still goes through the token.

Under each server, its nodes (processor load) then their virtual machines and containers (green dot: running). The state is updated every 30 seconds; the session filter also applies (ID, name, node, tag). A click opens the **console** of a running machine in a tab; right-click gives the rest.

| Where | Actions |
| --- | --- |
| Machine or container (right-click) | Console; start, shut down, reboot, pause and resume (virtual machines), stop (power off, with confirmation); **Snapshots** (take, with memory if the machine is running, roll back, delete); **Backups** (back up now to a storage, mode and compression; list, restore over it, delete); **Clone** (new ID suggested, target node, full or linked copy from a template); **Migrate** to another node, live if it is running; **Resources and settings** (cores, sockets, memory, start with the node, notes, all settings read-only); Tasks; convert to template; delete (by typing its ID). |
| Node (right-click) | **Monitoring** of this node; node shell in a tab; **create a virtual machine** or **a container**; **updates**, **services**, **system log**, **network**, **disks**; storage; tasks; **restart** or **shut down the node** (see below). |
| Server ("…" menu) | **Monitoring**; create a virtual machine or a container (node of your choice); refresh; cluster tasks; storage (space used, content: ISO images, templates, disks, backups); edit; copy the fingerprint; remove from Portunia. |

<a id="proxmox-supervision"></a>

#### Monitoring (Portunia 0.68)

The server's "…" menu (or right-click on a node) › **Monitoring**: a tab read again every 10 seconds while it is open.

-   **Overview**: processor and memory of all nodes, storage used (a shared storage counted once), running machines.
-   **Each node**: gauges (processor, memory, system disk) and charts over the hour, day, week or month (processor and IO wait, memory and swap, network, load average). Hover over a chart to read its values at a point in time.
-   **Storage**: type, content, space used (orange at 75%, red at 90%).
-   **Machines and containers**: processor, memory, disk, network and disk throughput (measured between two readings), uptime; click a column title to sort, a row for its charts.

Node charts need the `Sys.Audit` privilege (the `PVEAuditor` role, for example), machine charts `VM.Audit`.

Each action starts a Proxmox task: Portunia follows it and reports its result. Consoles use the Proxmox VNC console, relayed by Portunia: the **VNC** extension must be enabled. Rights are those of the user or token in Proxmox.

<a id="proxmox-creer"></a>

#### Creating a machine or a container (Portunia 0.70)

| Wizard | What you choose |
| --- | --- |
| **Virtual machine** | Node, ID (the first free one is suggested), name, system (Linux, Windows 11 / Server 2022-2025, Windows 10 / Server 2016-2019, other), **installation ISO** from the storages ("Download an ISO…" has the node fetch one from a web address), cores, memory, CPU type, disk storage and size, network bridge and VLAN tag, QEMU guest agent, start after creation and with the node. |
| **Container** | Node, ID, host name, **template** ("Get templates…" opens the Proxmox catalogue: Debian, Ubuntu, Alpine…), root password and/or SSH keys, cores, memory, swap, disk, unprivileged container and nesting (ticked by default), bridge, VLAN, IPv4 by DHCP or fixed with a gateway, IPv6, DNS server. |

For Windows 11, the machine gets UEFI, Secure Boot and a TPM. Also choose the **VirtIO drivers** ISO (`virtio-win.iso`): the disk and network card are then VirtIO, the fastest. Without it, Windows gets a SATA disk and an Intel E1000 card, which its installer recognises out of the box. Creating needs the `VM.Allocate` and `Datastore.AllocateSpace` privileges (roles `PVEVMAdmin` and `PVEDatastoreUser`, for example).

<a id="proxmox-noeud"></a>

#### Managing a node (Portunia 0.70)

| Node menu | Effect |
| --- | --- |
| Updates | Proxmox and kernel versions, packages to update; "Refresh the list" (apt update); "Upgrade in a shell" opens the node shell and runs `apt dist-upgrade` there, as Proxmox does, where you answer its questions. Proxmox only allows it for `root@pam`. |
| Services | State of the Proxmox services (pveproxy, pvedaemon, corosync, sshd, postfix…): start, stop, restart. A confirmation is asked for those whose stop can cut access to the node. |
| System log | The last 200, 500 or 2000 lines, with a filter. |
| Network | Interfaces, bridges, addresses, gateway, ports, read-only: a network mistake can cut the node off, so changes stay in the Proxmox web interface. |
| Disks | Physical disks: type, model, size, usage (LVM, ZFS…), health and SSD wear; "SMART" shows the attributes. |
| Restart, shut down the node | After typing the node's name. Running machines are shut down first. A node that is shut down is started again on site or through its management card. |

Useful privileges: `Sys.Audit` to read, `Sys.Modify` for services and updates, `Sys.PowerMgmt` to restart or shut down, `Sys.Syslog` for the log (the `Administrator` role on the node, for example).

<a id="verrou"></a>

## 15\. Locking and data

In Settings › Security, "Enable locking" creates a master password of at least 8 characters. Your sessions, notes and fingerprints are then encrypted on disk. Portunia asks for this password at startup and after the chosen idle time. Windows Hello (face, fingerprint, PIN) can replace it day to day.

Ctrl+Shift+L locks immediately. Open sessions keep running in the background.

> [!CAUTION]
> **Forgotten master password** — Nobody can recover it. Without Windows Hello, the encrypted data is lost. Keep a backup ([next chapter](#sauvegarde)).

After 5 failed attempts, Portunia imposes an increasing wait, from 5 seconds to 5 minutes. During the wait, even the right password is refused.

<a id="sauvegarde"></a>

## 16\. Import and backup

Palette, then "Import / export".

| Source | What is imported |
| --- | --- |
| `~/.ssh/config` | Hosts, users, ports, keys, jump hosts and tunnels. |
| PuTTY | Sessions from the Windows registry. |
| mRemoteNG | Exported XML file. |
| Portunia backup | A backup created with "Export…". |

A preview lists what will be imported and flags the sessions that already exist. For a backup, choose a passphrase of at least 8 characters: without it, the file stays in plain text.

> [!NOTE]
> **Passwords** — An import or a backup never contains a password. After restoring on another PC, you will have to type them again.

<a id="reglages"></a>

## 17\. Settings and licence

| Section | What you set there |
| --- | --- |
| Appearance | Language (applied at the next start), light theme, dark theme or as Windows, terminal colours, font, size, cursor (bar, block, underline). |
| Terminal | Right-click, automatic copy of the selection, paste confirmation, highlighting, rendering. |
| Connection | Automatic reconnection after a network cut or sleep. |
| Local shells | Default shell, custom shells, opening at startup. |
| Security | Master password, Windows Hello, locking after inactivity. |
| Monitoring | On or off, frequency, alerts. |
| Updates | Check at startup, "Check now". |
| Licence | Paste the text received by email here. It is checked without an Internet connection. |

An expired licence keeps its features: only the versions released after the expiry are no longer included.

<a id="Gate"></a>

## 18\. Connecting through a Gate

Your administrator gives you the **Gate address**, your **user name**, a **temporary password** and the **certificate fingerprint**. Install an authenticator app on your phone, such as Microsoft Authenticator or Google Authenticator.

### First access

1.  In the **Gates** panel (shield icon in the rail), click "Add a Gate". If it does not appear, enable the Portunia Gate extension in Extensions.
2.  Type the address, for example `gate.example.com`.
3.  **Compare the fingerprint shown with the one your administrator gave you.** If they differ, stop and tell them.
4.  Type your user name and temporary password.
5.  Choose your new password.
6.  Scan the QR code with your app, then type the 6 digits it shows.

Your servers appear in folders under the Gate's name. You only see the ones you are allowed to use, and only on the planned days and hours.

### Every day

-   Click a server: it opens in a tab without asking for a code again. Portunia obtains a single-use authorisation for you.
-   The Gate's line shows your user name and the time left. By default, a connection to the Gate lasts 8 hours.
-   When the time is up, the Gate shows "session expired". Click it to sign in again. The servers stay greyed out meanwhile.
-   If the administrator allows it, tick "Remember my password on this PC". The code is still asked.
-   The Gate's "More actions" button also offers "My sessions" (if the Gate lets you replay yours), "Sign out" and "Remove this Gate".

### Sessions that bypass the Gate

Portunia may point out that some of your personal sessions go directly to servers protected by the Gate. These connections escape the controls and the recording. Delete or keep them according to your company's policy, and from now on open these servers from the Gates section.

### Windows servers

They carry an RDP badge and need the Remote Desktop extension. Your Windows credentials are asked at each opening, except for servers in **vault** mode (Gate 0.29): the Gate then opens the Windows session itself, without you seeing the password. In the web portal, Windows servers in jump mode open too: the Gate relays them, without recording them.

<a id="rdp-natif"></a>

### Windows servers in mstsc or Windows App

If the administrator has opened the Gate's native RDP entry (Gate 0.31, Portunia 0.71), right-click a Windows server › **Open in the Windows client (mstsc)** (on Mac: **Open in Windows App**). Portunia prepares a single-use .rdp file, valid for a few minutes, and opens it: you get the Windows client (several screens, printers, shortcuts) while the Gate keeps its checks and its recording.

-   **Vault**: nothing to type.
-   **Recorded**: Portunia asks for your Windows account; the Gate uses it once to open the session and does not keep it. Leave it empty if the server shows its own sign-in screen.
-   **Jump**: mstsc asks for your Windows credentials, as for a direct connection.

mstsc may warn once about the Gate's certificate: your administrator gives you the fingerprint to compare. If the connection drops, open it again from Portunia (a file is used only once).

### Web interfaces

Administration consoles (vCenter, iDRAC, firewalls…) carry a WEB badge (Gate 0.30, Portunia 0.67, Web interface extension). A click opens the application in a dedicated window, through the Gate; you type your credentials there as usual. The Gate logs the pages you open. In the web portal, it opens in a new tab; only one web interface at a time per browser.

> [!WARNING]
> **Phone lost or changed** — Without the phone, you can no longer generate a code. Ask your administrator to reset your code; you will do the QR code step again at your next sign-in.

<a id="modes"></a>

## 19\. Jump, recorded, vault

Each server has a mode, chosen by the administrator and shown in the list. It decides what you have to type and what is kept.

| Mode | You type | Recorded? |
| --- | --- | --- |
| **Vault** | Nothing: the Gate provides the server account, which you never see. | Yes. |
| **Recorded** | Your credentials for the server, in the terminal or the Windows window. | Yes. |
| **Jump** | Your credentials for the server. The Gate relays end to end. | No. |

> [!NOTE]
> **What is kept** — In vault and recorded modes, what is displayed is recorded and can be replayed by auditors. Keystrokes can be too, depending on the rule, with hidden input protected. Follow your company's policy, as on any work computer.

<a id="portail"></a>

## 20\. The web portal

If your company has enabled it, the portal opens your servers from a browser, without Portunia. You must be in the authorised group and have done the first sign-in: **the first sign-in and a lost code are not handled on the portal.**

1.  Go to the address given by your administrator and wait during the anti-bot check.
2.  Fill in user name, password and code, then "Sign in".
3.  In **My servers**, look for a server and open it in a tab.

| Situation | How it works |
| --- | --- |
| SSH server | A terminal with Copy and Paste buttons. In recorded mode, your credentials are asked in the terminal. |
| Windows server | Windows credentials asked, then Ctrl+Alt+Del and Full screen buttons. They are sent to the server over an encrypted connection: the Gate does not see your password. |
| Files with a Windows server | If your administrator allows it: **Upload files** (or drop them on the desktop), then paste them in Windows with Ctrl+V. To get files back, copy them in Windows (Ctrl+C): they appear in the Files panel, with a Download button. Each copied file is logged by the Gate. Without permission, file copy is blocked; copying and pasting text remains possible. |
| Server in jump mode | Not available on the portal: use Portunia. |
| Inactivity | "Still there?" appears before closing: click Continue. |

> [!WARNING]
> **Shared computer** — Click "Sign out" when you leave and leave no tab open.

<a id="sans-portunia"></a>

## 21\. Without Portunia

The Gate accepts the usual SSH clients, such as OpenSSH, PuTTY or WinSCP. Your code must have been enrolled first. Replace `julien`, `web-01`, `gate` and the port if your administrator gives another one.

```
ssh -p 2222 julien@gate               # menu of allowed servers
ssh -p 2222 julien%web-01@gate        # straight to web-01
ssh -J julien@gate:2222 admin@fw-01   # server in jump mode
sftp -P 2222 julien%web-01@gate       # files (vault, if the rule allows it)
```

<a id="depanner"></a>

## 22\. Helping someone

You need Portunia, the Portunia Gate and Remote assistance extensions enabled, a connection to a Gate whose relay is active, and an account in its group of helpers.

1.  Call the person on the phone.
2.  Click **Remote assistance** (lifebuoy icon in the rail). The window shows the sentence to say, with the address of the page to open.
3.  When the person reads you their 9 digits, type them, then "Connect".
4.  The person sees your name and accepts. Their screen opens in a tab.

They decide whether you only see the screen or can also use the mouse and keyboard. They can stop everything at any time. The link is encrypted end to end from the code.

| Message | What to do |
| --- | --- |
| "Sign in to a Gate first" | Sign in again in the Gates section. |
| "The assistance relay is disabled on your Gate" | Ask an administrator to enable it in Administer › Assistance. |
| "Your account is not in the gate's group of helpers" | Ask to be added to the group, or check that the Gate runs Portunia Gate 0.11 or later. |
| "The Gate has not downloaded Portunia Assistance yet" | The Gate needs Internet access to fetch it: tell the administrator. |

<a id="aide"></a>

## 23\. Getting help

A person you trust is going to help you on your computer, running Windows 10 or 11. Nothing is installed, and nobody sees your screen without your consent.

1.  Go to the page the person tells you and click **Download Portunia Assistance**.
2.  Open the downloaded file. If Windows shows a blue warning, click "More info", then "Run anyway".
3.  A 9-digit code appears. Read it to the person helping you.
4.  Their name appears. Check that it really is them, then accept.
5.  Tick the option that lets them use the mouse and keyboard if they need to act for you. Otherwise, they only see the screen.

During the assistance, a frame surrounds your screen and a banner shows who is watching it. **To stop, click "Stop" or press Esc three times.** Once closed, the program leaves no access behind.

> [!CAUTION]
> **Beware of unexpected calls** — Only read this code to someone you know or whom you called yourself. No legitimate person will call you out of the blue to ask for it. If in doubt, hang up.

<a id="raccourcis"></a>

## 24\. Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| Ctrl+Shift+O | Palette: sessions, shells, actions |
| Ctrl+Shift+K | Search for a session |
| Ctrl+Shift+N | New session |
| Ctrl+Shift+Q | Quick connect |
| Ctrl+Shift+T | Open the default local shell |
| Ctrl+Shift+W | Close the active tab |
| Ctrl+Shift+F | Search in the terminal |
| Ctrl+Shift+B | Multi-input |
| Ctrl+Shift+P | Saved commands |
| Ctrl+Shift+L | Lock Portunia |
| Ctrl + mouse wheel | Terminal text size |
| Ctrl + click | Open a link in the terminal |
| F2 / Del | Rename or delete in the Files panel |

<a id="connexion-rapide"></a>

## 25\. Quick connect forms

They work in the search, the palette and the Quick connect window.

| You type | Portunia opens |
| --- | --- |
| `10.0.0.12` | A connection to this address |
| `ssh deploy@10.0.1.12` | SSH with this user |
| `rdp srv-01` | Remote Desktop |
| `vnc nas:5901` | VNC on port 5901 |
| `https://nas:5001` | Web interface |
| `COM3@9600` | Serial port at 9600 baud |
| `ftps://user@host` | FTPS |

<a id="problemes"></a>

## 26\. Troubleshooting

| Symptom | Likely cause | What to do |
| --- | --- | --- |
| "WARNING: the server key has changed" | The server was reinstalled, or someone is impersonating it. | Do not continue. Check with the person in charge of the server. |
| Cannot connect to an old device | Algorithms too old. | Tick "Compatibility with older equipment" in that session. |
| "No answer from RDP server" | Machine off, Remote Desktop disabled, firewall. | Test port 3389 in Network tools. |
| "RDP engine not found" | Incomplete installation, sometimes because of an antivirus. | Reinstall Portunia or choose the "Windows client" display. |
| A server cannot be found in the Gate's list | No rule allows it for you, or not at this time. | Contact your administrator. |
| Code refused | Phone clock out of sync, or code already used. | Set the time to automatic and wait for the next code. After 5 failures in 10 minutes, you have to wait. |
| "session expired" on the Gate | Connection time is up. | Click the Gate and sign in again. |
| Portal: "Authorisation expired" | The tab waited too long. | Open the server again from the list. |
| Portal: "Access denied by the Gate" | Rule or server not allowed. | Contact your administrator. |
| Portal: "Portal closed" | Portal disabled. | Use Portunia or contact your administrator. |
| Portal: "Windows login or password refused" | Wrong Windows credentials. | Check them and give the domain if needed. |
| Portunia Assistance: does not know which server to use | The file was renamed. | Download it again from the page you were given. |
| Slow terminal or broken display | Graphics driver, Remote Desktop session. | Settings › Terminal rendering: "Never (classic rendering)". |

<a id="faq"></a>

## 27\. Frequently asked questions

| Question | Answer |
| --- | --- |
| Where are my passwords? | In the Windows Credential Manager, not in Portunia's files. |
| Does Portunia send my data anywhere? | Your sessions stay on your PC. The update check queries the release site. |
| Does closing the tab cut the connection? | Yes, and that session's tunnels stop with it. |
| Can I change PC? | Yes: export a backup, restore it, then type your passwords again. Also copy your SSH keys safely. |
| Can the administrator see my Gate passwords? | No. They can give you a new temporary password, but cannot read yours. |
