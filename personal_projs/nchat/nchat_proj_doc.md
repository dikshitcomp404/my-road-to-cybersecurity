# Building My First Real Project: ncat-chat



## Motivation



It all started with a small annoyance: whenever I wanted to share text between my VM and host system, I didn’t have a neat way to do it. Copy-paste sometimes failed, and I didn’t want to rely on external apps for something so simple.



That sparked the idea — what if I could build a tiny cross-platform chat system that works directly over the network? Nothing fancy, just reliable text transfer between two machines.



---



## First Steps: Playing With ncat



I discovered that **ncat** (from the Nmap suite) supports SSL connections. That meant I could use it for secure text chat between two systems.



So I started with two simple scripts:



* A **host script** that listens on a port.

* A **client script** that connects to it.



On Linux, I made small Bash scripts. On Windows, Batch scripts. The basic loop was:



* If disconnected, reconnect automatically.

* Keep things simple and minimal.



That was my **first working version** — and it already solved my original problem!



---



## Early Roadblocks: Networking Confusion



Of course, things weren’t smooth.



* On Pop!_OS VM, I couldn’t connect — I kept seeing *No route to host*.

* Running `ifconfig`, I realized my VM didn’t even have a proper IP.

* I learned the difference between **NAT** vs **Bridged** network adapters in VirtualBox.

* Switching to bridged mode finally gave my VM a valid LAN IP, and suddenly the client could connect.



This was a **big learning moment**: debugging networking means understanding subnets, routes, and adapters — not just fiddling with commands.



Here I also leaned on **AI guidance**: when I got stuck on networking concepts, I used AI to explain in simpler words what NAT vs Bridged actually meant. It helped me connect theory with practice, but the actual debugging — switching adapters, testing IPs — was my own hands-on effort.



---



## Growing the Project: Cross-Platform Support



I didn’t want this to be Linux-only. So I rewrote the scripts for Windows:



* `nchat-host.bat`

* `nchat-client.bat`



Both worked with `ncat` installed from Nmap.



Sometimes the Batch syntax was tricky (like loops, errorlevels, or timeouts), and instead of browsing endless forums, I asked AI for small snippets. That sped up my learning. I didn’t just copy-paste — I tested, debugged, and understood how the code worked.



By this point, I had a **minimal working cross-platform tool**.



---



## Versioning & Repo Setup



Next step: putting it on **GitHub**.



* I learned how to structure a repo: `linux`, `windows/`, each with host/client scripts and a README.

* Learned about **branches**, `master` vs `main`, and changing defaults.

* Made my **first proper commit history**.



Here, AI helped me when I got confused about Git commands. For example, how to set a default branch or fix a push error. It was like having a senior dev explain the workflow step by step.



---



## Adding Installers



The next challenge: installation should be easy.



On Linux:



* I made a script that creates `~.local/bin`, puts the chat scripts there, and makes sure it’s in `$PATH`.

* This makes it so that the scripts can be run as commands from a terminal in linux enviroments.

This was more difficult than writting the scripts itself. For the installer we can't just say install and it will magically do everything. We have to set up the paths, change the enviroment PATH variable, and for the sake of making it a completely hands free installation, I decided to make it install nmap automatically as well.

Installation in linux is particularly more complex. The installer checks which package handler the linux enviroment uses. Then checks if nmap is installed or not, then finally installs. The rest is simple, to copy the scripts into `~.local/bin`, then changing their mode to executable, `chmod +x ...` 


On Windows:



* I wrote a Batch installer that:



* Checks if Nmapncat is installed (and installs it with `winget` if not).

* Creates a `nchat` folder inside `%USERPROFILE%`.

* Adds it to the PATH environment variable.



This was where I learned a *lot* about:



* PATH management in both OSes.

* Dependency checks.

* How installers improve user experience.



AI was especially helpful here for syntax — things like safely editing PATH in Windows batch, or making sure `$PATH` changes in Linux persisted. I still had to debug with `echo` statements, but AI gave me a clearer starting point.



---



## Future plans for expanding functionality: File Transfer



Text chat is great, but the feature to transfer files in your own network with a self hosted app just as easily as texting here is even better use case for such a project.



* So I plan on extending the scripts to support **file transfer** using other ncatnmap tools.

* This will certainly make the project more general — not just for chat, but also sharing files between machines securely.



---



## What I Learned Along the Way



This project wasn’t just about ncat. It taught me:



* **Networking fundamentals**: IPs, subnets, routes, NAT vs Bridged.

* **Linux internals**: working with `ifconfig`, `nmcli`, `$PATH`, `~.local/bin`.

* **Windows quirks**: batch scripting, registry editing for PATH, winget usage.

* **GitHub essentials**: repos, commits, branches, releases.

* **Installer design**: making software easier to install & use.

* **Documentation & presentation**: writing READMEs, versioning, and even LinkedIn posts.

* **Practical AI use**: instead of wasting hours searching docs, I used AI to clarify concepts, suggest snippets, and debug when stuck — but I always tested, learned, and adapted it myself.



---



## Reflection



What started as a **tiny fix for a VM annoyance** became my **first real end-to-end project**:



* Idea → Scripts → Cross-platform support → Installers → File transfer → Repo publishing → Documentation.



I also use this tool **regularly** — whenever I need to share text between two devices, I don’t need to install or log into a third-party chat app. I just launch `nchat`, and within seconds, I can send messages across. The setup is minimal, the connection is quick, and it’s become part of my daily workflow.



That’s what excites me most: it’s not just a demo — it’s **practical and useful in real scenarios**.



And the best part is that this is only the beginning:



* Once I add **file transfers** and **secure end-to-end connections over the internet**, it will go from a neat LAN utility to a genuinely powerful tool for personal and professional use.



---



## Future Plans



* A more polished **installer version 2.0**.

* VPN-backed remote connections.

* Better error handling & logging.

* Possibly a GUI wrapper for easier use.



---



For me, the biggest win wasn’t just the tool itself, but the **confidence that I can start an idea, face hurdles, and push it through to a usable release — while smartly using every resource available, including AI.**

