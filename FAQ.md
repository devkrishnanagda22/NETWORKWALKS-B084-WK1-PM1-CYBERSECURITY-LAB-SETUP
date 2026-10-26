# 🛡️ Frequently Asked Questions (FAQ)
## Networkwalks — VirtualBox Cybersecurity Lab Setup

**Project:** WK1-PM1 — Cybersecurity Lab Setup  
**Platform:** Oracle VirtualBox  
**Guest Operating System:** Kali Linux  
**Purpose:** Cybersecurity learning, networking practice, and authorized security testing

---

## 📑 Table of Contents

1. General Questions
2. VirtualBox Installation
3. RAM, CPU, and System Resources
4. Display Resolution and Graphics
5. Kali Linux Installation
6. Network Configuration
7. Internet Connectivity Troubleshooting
8. Shared Clipboard and Shared Folders
9. Snapshots and Recovery
10. Performance Optimization
11. Common Errors and Troubleshooting
12. Cybersecurity Lab Safety
13. Verification Checklist
14. Useful Resources

---

# 1. General Questions

### Q1. What is the purpose of this cybersecurity lab?

**Answer:**

The purpose of this lab is to prepare a virtual environment for learning cybersecurity and practicing authorized security testing.

The environment uses Oracle VirtualBox to run Kali Linux without replacing the computer's primary operating system.

The lab setup includes virtual machine configuration, networking, internet connectivity testing, and snapshot creation.

### Q2. Do I need to replace Windows with Kali Linux?

**Answer:**

No. You can keep Windows as your primary operating system and run Kali Linux inside Oracle VirtualBox.

This approach allows you to use Windows for everyday tasks while using Kali Linux for cybersecurity learning.

### Q3. What is a virtual machine?

**Answer:**

A virtual machine (VM) is a software-based computer that runs inside a physical computer.

It has virtual hardware resources, including CPU, RAM, storage, and network adapters.

Virtual machines are useful for creating isolated environments for software testing, development, and cybersecurity practice.

### Q4. Why use VirtualBox instead of installing Kali Linux directly?

**Answer:**

Running Kali Linux in VirtualBox offers several advantages:

- You can keep your existing operating system.
- You can adjust virtual hardware resources.
- You can create snapshots before making significant changes.
- You can experiment with networking configurations.
- You can maintain a dedicated environment for cybersecurity tools.

However, a virtual machine is not automatically a complete security boundary. Its configuration and the activities performed inside it still matter.

### Q5. Is Kali Linux required for cybersecurity?

**Answer:**

No. Kali Linux is a popular Linux distribution containing tools used in penetration testing and security research, but it is not mandatory for every cybersecurity role.

Many tasks can also be performed using Windows, other Linux distributions, cloud laboratories, or dedicated testing environments.

### Q6. Is this lab suitable for beginners?

**Answer:**

Yes. This lab can help beginners understand virtual machines, Linux, network configuration, connectivity testing, and recovery points before progressing to more advanced security exercises.

---

# 2. VirtualBox Installation

### Q7. What software is required for this lab?

**Answer:**

The primary software components are:

1. Oracle VirtualBox
2. A compatible Kali Linux installation image or virtual machine image
3. Sufficient free disk space and system memory

Additional components may be needed for features such as automatic display resizing and shared clipboard functionality.

Always obtain software from its official source.

### Q8. Where can I download VirtualBox?

**Answer:**

Download VirtualBox from the official website:

https://www.virtualbox.org/wiki/Downloads

Choose a version compatible with your host operating system.

### Q9. Where can I download Kali Linux?

**Answer:**

Use the official Kali Linux website:

https://www.kali.org/get-kali/

Choose an installation image or prebuilt virtual machine image compatible with your setup.

Verify the downloaded file using the verification instructions provided by Kali Linux.

### Q10. What should I check before installing VirtualBox?

**Answer:**

Before installation, check:

- Your host operating system is supported.
- Your computer has sufficient RAM.
- Adequate disk space is available.
- Hardware virtualization is supported and available.
- You have permission to install software on the computer.

If this is a managed work or college computer, consult the administrator before changing system settings.

### Q11. What is hardware virtualization?

**Answer:**

Hardware virtualization is a processor feature that helps virtualization software run virtual machines efficiently.

Depending on your computer, it may be described as Intel VT-x or AMD-V.

If VirtualBox reports that hardware virtualization is unavailable, check your computer's firmware settings and the applicable VirtualBox troubleshooting documentation.

Do not change firmware settings unless you understand the implications for your system.

---

# 3. RAM, CPU, and System Resources

### Q12. How much RAM should I allocate to Kali Linux?

**Answer:**

The appropriate allocation depends on your computer's total memory and workload.

| Total Host RAM | Possible Starting Allocation for Kali |
|---|---|
| 4 GB | A lightweight configuration; performance may be limited |
| 8 GB | 2–4 GB |
| 16 GB | 4–8 GB |
| 32 GB or more | Choose according to workload and other running applications |

These are general starting points, not mandatory settings for this assignment.

Leave sufficient memory for Windows and other applications. If the host begins using excessive swap space or becomes unresponsive, reduce the VM allocation or close unnecessary applications.

### Q13. Can I allocate all my RAM to the virtual machine?

**Answer:**

No, this is generally not recommended.

Windows and its background processes also need memory. Allocating too much RAM to Kali Linux can make the host slow or unstable.

Choose an allocation that allows both systems to operate comfortably.

### Q14. How many virtual CPUs should I allocate?

**Answer:**

For basic Linux and networking exercises, two virtual CPUs can be a reasonable starting point if your computer supports it.

More demanding workloads may benefit from additional CPU resources.

Avoid assigning all available processor resources to the VM. The host operating system still needs CPU time.

### Q15. Can I increase RAM and CPU after creating the virtual machine?

**Answer:**

Yes. In general, you can change the VM's memory and processor allocation through its settings.

1. Shut down Kali Linux completely.
2. Open VirtualBox Manager.
3. Select the Kali Linux virtual machine.
4. Open **Settings → System**.
5. Adjust the available memory and processor settings.
6. Save the changes and start the VM.

The exact interface may differ between VirtualBox versions.

### Q16. How much disk space does Kali Linux require?

**Answer:**

The required space depends on the installation method, desktop environment, applications, and future updates.

Plan for the operating system, installed packages, downloaded files, and snapshots. A dynamically allocated virtual disk may grow as data is written, but it still consumes space on the host.

Check the official Kali Linux installation requirements before creating your VM.

### Q17. What is the difference between allocated disk size and actual disk usage?

**Answer:**

A dynamically allocated virtual disk can have a maximum capacity larger than the space it currently occupies on the host.

For example, a virtual disk configured with a maximum capacity of 80 GB does not necessarily occupy 80 GB immediately.

Its actual size generally increases as data is stored, subject to the virtual disk format and configuration.

---

# 4. Display Resolution and Graphics

### Q18. Why is my Kali Linux screen resolution too small?

**Answer:**

A small display can result from the VM's initial display configuration, missing Guest Additions, or unsupported automatic resizing.

Try the following:

1. Start Kali Linux.
2. Resize the VirtualBox window.
3. Open the **View** menu.
4. Check the available virtual display resizing options.
5. If resizing does not work, investigate Guest Additions.

Do not assume the problem requires reinstalling Kali Linux.

### Q19. How can I change the screen resolution?

**Answer:**

First, try the VirtualBox display controls.

If the display does not resize automatically:

1. Check whether Guest Additions are installed and functioning.
2. Check the display settings available in Kali Linux.
3. Select a supported resolution appropriate for your monitor.
4. Restart the graphical session if necessary.

The exact steps depend on the Kali Linux desktop environment and VirtualBox version.

### Q20. What are VirtualBox Guest Additions?

**Answer:**

Guest Additions are additional components that can improve integration between the guest operating system and VirtualBox.

Depending on the operating system and configuration, they can support features such as:

- Automatic display resizing.
- Improved mouse integration.
- Shared clipboard functionality.
- Shared folders.
- Other guest integration features.

They are not the same thing as the VirtualBox Extension Pack.

Official documentation:

https://docs.oracle.com/en/virtualization/virtualbox/7.2/user/guestadditions.html

### Q21. Should I enable 3D Acceleration?

**Answer:**

Not necessarily. **3D Acceleration is optional for basic cybersecurity lab tasks.**

It may improve graphics performance for supported workloads, but it can also cause display problems on some host systems or configurations.

To check the setting:

1. Shut down the VM completely.
2. Open VirtualBox Manager.
3. Select your Kali Linux VM.
4. Open **Settings → Display → Screen**.
5. Locate **Enable 3D Acceleration**, if available.
6. Enable it only if appropriate for your setup.
7. Start Kali Linux and test the display.

If graphical glitches, freezes, or startup problems appear, disable the setting and test again.

Do not claim 3D Acceleration was enabled in your completed lab unless you have verified it.

### Q22. How much video memory should I allocate?

**Answer:**

The appropriate amount depends on the display resolution, monitor configuration, graphics features, and VirtualBox version.

For a basic desktop, start with a reasonable supported setting and increase it only if a specific display requirement calls for it.

More video memory does not automatically make every virtual machine faster.

### Q23. How can I enter or exit full-screen mode?

**Answer:**

1. Start the Kali Linux VM.
2. Open VirtualBox's **View** menu.
3. Select **Full-screen Mode**.

Use the shortcut shown in your VirtualBox version to return to windowed mode.

If the desktop does not fill the screen correctly, investigate automatic display resizing and Guest Additions.

---

# 5. Kali Linux Installation

### Q24. What is the difference between an ISO image and a prebuilt VM?

**Answer:**

An ISO image is commonly used to install an operating system into a newly created virtual machine.

A prebuilt virtual machine image is already configured for use with a supported virtualization platform.

The setup process differs depending on which option you choose.

Follow the instructions for the specific Kali Linux download you obtained.

### Q25. Why is Kali Linux not booting?

**Answer:**

Possible causes include:

- Incorrect boot media.
- Incorrect boot order.
- An incompatible image.
- Insufficient memory or storage.
- Virtual machine configuration problems.

Check the error displayed by VirtualBox before changing settings. Confirm that the downloaded image matches the intended installation method.

### Q26. What should I do after the first successful boot?

**Answer:**

After Kali Linux starts:

1. Confirm that the desktop loads correctly.
2. Check the network configuration.
3. Test internet connectivity if required.
4. Verify that the available storage is sufficient.
5. Install updates according to your lab requirements.
6. Create a snapshot after reaching a known-good state.

Follow the assignment instructions if they specify a particular order.

### Q27. Should I update Kali Linux immediately?

**Answer:**

Updates can provide security fixes and software improvements, but consider your lab requirements first.

If the assignment depends on a particular version or configuration, document the existing state before making significant changes.

Ensure that the VM has sufficient disk space and a working network connection before starting a large update.

---

# 6. Network Configuration

### Q28. What is a virtual network adapter?

**Answer:**

A virtual network adapter is the network interface presented to a virtual machine.

VirtualBox can connect it to different network modes, each providing different connectivity and isolation characteristics.

The appropriate mode depends on whether the VM needs internet access, communication with other VMs, or access to a physical network.

### Q29. What is NAT networking?

**Answer:**

Network Address Translation (NAT) allows a virtual machine to access external networks through a translated network connection.

The guest typically does not appear as an independently addressable device on the physical network in the same way it would under a bridged configuration.

NAT configurations can be useful for basic internet access.

### Q30. What is a NAT Network?

**Answer:**

A NAT Network is a VirtualBox networking mode that allows connected virtual machines to communicate with one another while also supporting outbound network access.

It differs from the individual NAT mode available for a VM's network adapter.

Use the mode required by your assignment rather than switching modes without a reason.

### Q31. What network configuration is documented for this lab?

**Answer:**

The supplied lab instructions identify these values:

| Setting | Documented Value |
|---|---|
| VirtualBox network mode | NAT Network |
| Network subnet | `10.0.0.0/24` |
| Intended Kali Linux IP address | `10.0.0.2/24` |

These values describe the documented lab configuration. Verify the actual network settings on your VM before applying them.

### Q32. What does `10.0.0.0/24` mean?

**Answer:**

It is an IPv4 network expressed in CIDR notation.

The `/24` prefix corresponds to the subnet mask `255.255.255.0`.

In this subnet, `10.0.0.0` identifies the network, while `10.0.0.255` is the broadcast address.

Do not assign either of those addresses to a regular host in this subnet.

### Q33. How do I check my Kali Linux IP address?

**Answer:**

Open a terminal and run:

```bash
ip addr
```

To view the routing table, run:

```bash
ip route
```

These commands help you inspect the configured interfaces and routes.

Compare the results with the network settings required by your lab.

### Q34. How can I test whether Kali Linux has internet access?

**Answer:**

Start by testing connectivity to a known external IP address:

```bash
ping -c 4 1.1.1.1
```

Then test DNS resolution:

```bash
getent hosts kali.org
```

Interpret the results carefully:

- If the IP test succeeds but name resolution fails, investigate DNS.
- If both fail, check the network adapter, routing, and host connectivity.
- If ping fails, remember that some networks block ICMP traffic; a failed ping alone does not prove that all internet access is unavailable.

### Q35. Can I change from NAT Network to Bridged Adapter?

**Answer:**

Only if the lab requires it or you understand why the change is needed.

Bridged networking can make the VM appear as another device on the physical network. This may expose services to other devices on that network.

For a controlled lab, use the network mode specified by the assignment unless there is a clear reason to change it.

---

# 7. Internet Connectivity Troubleshooting

### Q36. Why does Kali Linux have no internet connection?

**Answer:**

Check the following in order:

1. Confirm that the host computer has internet access.
2. Verify that the VM's network adapter is enabled.
3. Confirm the correct VirtualBox network mode.
4. Check the Kali Linux IP address.
5. Inspect the routing table.
6. Test IP connectivity.
7. Test DNS resolution.

Avoid changing multiple network settings simultaneously because doing so can make the original problem harder to identify.

### Q37. What should I check if Kali Linux has an IP address but cannot reach the internet?

**Answer:**

An assigned IP address does not guarantee a working route to the internet.

Inspect the routing table:

```bash
ip route
```

Check whether the expected default route exists. Also verify the VirtualBox network configuration and whether the host has internet access.

Do not assume a specific gateway address without checking the actual NAT Network configuration.

### Q38. What if IP connectivity works but websites do not resolve?

**Answer:**

This can indicate a DNS resolution issue.

Test name resolution:

```bash
getent hosts kali.org
```

Inspect the active DNS configuration and the settings supplied by your network environment.

Avoid replacing DNS settings unnecessarily if the problem is actually caused by routing or a disconnected adapter.

### Q39. How can I inspect the active network connection?

**Answer:**

Run:

```bash
nmcli connection show --active
```

To inspect network devices, run:

```bash
nmcli device status
```

These commands help identify active connections and the status of network interfaces managed by NetworkManager.

The connection name may differ from the examples shown in tutorials.

### Q40. Can restarting the network connection fix connectivity problems?

**Answer:**

Sometimes. If the connection is managed by NetworkManager, you can inspect its status before restarting it.

For example:

```bash
nmcli connection show
```

Identify the appropriate connection name before attempting to disconnect or reconnect it.

Do not blindly copy a command that assumes a connection is named `Wired connection 1`; your system may use a different name.

---

# 8. Shared Clipboard and Shared Folders

### Q41. How do I enable copy and paste between Windows and Kali Linux?

**Answer:**

1. Shut down the VM if the setting cannot be changed while it is running.
2. Open **VirtualBox → Settings → General → Advanced**.
3. Locate **Shared Clipboard**.
4. Choose **Bidirectional** if you need copying in both directions.
5. Start Kali Linux and test the feature.

Guest Additions and compatible guest integration components may be required.

### Q42. What is Drag and Drop in VirtualBox?

**Answer:**

Drag and Drop allows supported file-transfer operations between the host and guest operating systems.

Its availability depends on the VirtualBox version, guest integration components, and configuration.

If it does not work, verify the relevant setting and Guest Additions status rather than assuming the VM is corrupted.

### Q43. What is a shared folder?

**Answer:**

A shared folder provides access to a directory on the host operating system from the guest operating system.

It can simplify file transfer between Windows and Kali Linux.

However, sharing folders also gives the guest access to the shared content according to the configured permissions. Avoid sharing sensitive directories unnecessarily.

### Q44. How do I configure a shared folder?

**Answer:**

1. Create or select a directory on Windows.
2. Shut down the VM if required.
3. Open the VM's settings in VirtualBox.
4. Navigate to **Shared Folders**.
5. Add the directory and choose a share name.
6. Configure the options required by your lab.
7. Start Kali Linux and verify access.

Guest Additions may be required.

The supplied lab material references `/downloads` as the intended shared-folder location. Confirm the actual configuration before assuming that the folder is already mounted there.

### Q45. Why can I not access a shared folder?

**Answer:**

Possible causes include:

- The shared folder was not configured correctly.
- The guest integration components are missing.
- The folder is not mounted.
- Permissions prevent access.
- The configured share name differs from the expected name.

Inspect the VirtualBox shared-folder settings and the guest operating system before changing permissions.

---

# 9. Snapshots and Recovery

### Q46. What is a VirtualBox snapshot?

**Answer:**

A snapshot records a point-in-time state of a virtual machine.

Depending on the snapshot configuration, it can preserve the VM's virtual disk state and selected machine state. It can be useful when experimenting with software or network settings.

A snapshot is not a substitute for an independent backup.

### Q47. Why should I create a snapshot after completing the initial setup?

**Answer:**

A snapshot provides a convenient recovery point after you have confirmed that the VM is working as expected.

For this lab, a useful checkpoint is the state in which:

- Kali Linux starts successfully.
- The intended network configuration is present.
- Internet connectivity has been tested.
- The basic environment is ready for further work.

### Q48. How do I create a snapshot?

**Answer:**

1. Start or shut down the VM according to your intended snapshot state.
2. Open VirtualBox Manager.
3. Select the Kali Linux VM.
4. Open the **Snapshots** interface.
5. Choose the option to take a snapshot.
6. Enter a descriptive name and optional description.
7. Confirm the operation.

The exact controls may differ by VirtualBox version.

### Q49. What should I name my snapshot?

**Answer:**

Choose a name that describes the state of the VM.

Examples:

- `Initial Kali Installation`
- `Network Configuration Complete`
- `Internet Connectivity Verified`
- `Clean Lab Environment`

Descriptive names make it easier to identify the correct recovery point later.

### Q50. Can I restore a snapshot if a configuration change breaks Kali Linux?

**Answer:**

Yes, if an appropriate snapshot exists.

Review the available snapshots and select the correct recovery point before restoring it.

**Important:** Restoring a snapshot can discard changes made after that snapshot. Back up any important files before reverting.

### Q51. Do snapshots consume disk space?

**Answer:**

Yes. Snapshots can consume additional storage as the VM's virtual disk changes over time.

The amount depends on the virtual disk contents, the number of snapshots, and the changes made after each snapshot.

Monitor the host's free disk space and remove obsolete snapshots only after confirming they are no longer needed.

---

# 10. Performance Optimization

### Q52. Why is Kali Linux running slowly?

**Answer:**

Common causes include:

- Insufficient RAM.
- Limited CPU resources.
- Heavy applications running on Windows.
- Low host disk space.
- Slow storage.
- Graphics configuration issues.
- Background updates or intensive processes.

Start by identifying the resource under pressure rather than increasing every VM setting.

### Q53. How can I make Kali Linux faster?

**Answer:**

Try these steps:

1. Close unnecessary applications on the host.
2. Check available RAM.
3. Review the VM's processor allocation.
4. Check free disk space.
5. Avoid running unnecessary applications inside Kali Linux.
6. Investigate display integration if the graphical desktop is slow.
7. Use a lighter desktop environment if appropriate for your needs.

Increasing RAM or enabling 3D acceleration is not guaranteed to solve every performance problem.

### Q54. Why does Windows become slow when Kali Linux is running?

**Answer:**

The host and guest share physical hardware resources.

If Kali Linux uses too much RAM, CPU time, or disk activity, Windows may become slow.

Reduce the VM allocation if necessary and close resource-intensive applications on both systems.

### Q55. Does enabling 3D Acceleration always improve performance?

**Answer:**

No. The benefit depends on the workload, graphics drivers, host hardware, and VirtualBox configuration.

If your primary activities involve command-line tools, network inspection, and basic Linux administration, 3D acceleration may provide little benefit.

Test the setting and keep it enabled only if it works reliably for your environment.

---

# 11. Common Errors and Troubleshooting

### Q56. VirtualBox says that the VM is inaccessible. What should I do?

**Answer:**

Check the error details and confirm that the VM's configuration and virtual disk files are still available.

Avoid deleting configuration files or creating a replacement VM before determining the cause.

If the VM is stored on an external drive, verify that the drive is connected and accessible.

### Q57. What should I do if the virtual machine freezes?

**Answer:**

Wait briefly to determine whether the VM is performing a resource-intensive task.

If it remains unresponsive, check host resource usage and the VM's status.

Before forcing the VM to close, consider whether unsaved work may be lost. After restarting, inspect logs and resource settings if the problem repeats.

### Q58. Why does the VM show a black screen?

**Answer:**

Possible causes include a startup issue, graphics configuration, or an unsuccessful guest boot.

Check whether the VM is still running, inspect any error messages, and verify its display settings.

If the problem started after changing 3D acceleration or display settings, revert that change and test again.

### Q59. Why is my virtual disk full?

**Answer:**

The guest operating system may have accumulated package caches, downloads, logs, or other files.

Check disk usage inside Kali Linux:

```bash
df -h
```

To inspect directory sizes, use:

```bash
du -sh ~/Downloads
```

Delete only files you understand and no longer need. Also check free space on the Windows host because the virtual disk depends on host storage.

### Q60. Should I reinstall Kali Linux whenever something goes wrong?

**Answer:**

No. Reinstallation should not be the first troubleshooting step.

First identify whether the problem concerns networking, display settings, storage, permissions, or another specific component.

If the VM has a known-good snapshot, restoring it may be more efficient than rebuilding the entire environment.

---

# 12. Cybersecurity Lab Safety

### Q61. Can I use this VM for penetration testing?

**Answer:**

You can use Kali Linux to learn and perform authorized security testing.

Only test systems that you own or for which you have explicit permission. Follow the applicable scope, rules of engagement, and testing restrictions.

### Q62. Does a virtual machine make all testing safe?

**Answer:**

No. Virtualization can help separate environments, but it does not make every action harmless.

Network adapters, shared folders, clipboard integration, and other host-guest features can create connections between systems.

Understand the VM's network configuration and avoid performing destructive testing against systems outside your authorized environment.

### Q63. Should I expose Kali Linux services to the internet?

**Answer:**

Not unless there is a specific, authorized requirement and you understand the risks.

Keep unnecessary services disabled and avoid configuring port forwarding or bridged networking without a clear purpose.

For beginner exercises, use the network configuration specified by the lab.

### Q64. Can I store passwords and sensitive information in shared folders?

**Answer:**

Avoid placing sensitive information in shared folders unless necessary and appropriately protected.

A shared folder intentionally connects the host and guest environments. Review its permissions and access requirements before storing important data there.

### Q65. Is it safe to download tools from any website?

**Answer:**

No. Prefer official project repositories and trusted software sources.

Check the authenticity of downloaded files when verification information is available. Do not execute unknown scripts or binaries simply because they are recommended in an online tutorial.

---

# 13. Verification Checklist

Use this checklist to review the lab after setup.

| No. | Verification Item | Status |
|---|---|---|
| 1 | VirtualBox installed | Verify |
| 2 | Kali Linux VM created or imported | Verify |
| 3 | Kali Linux boots successfully | Verify |
| 4 | VM memory and processor settings reviewed | Verify |
| 5 | Display resolution checked | Verify |
| 6 | 3D Acceleration reviewed if needed | Verify |
| 7 | Required NAT Network configured | Verify |
| 8 | Kali Linux IP address checked | Verify |
| 9 | Internet connectivity tested | Verify |
| 10 | DNS resolution tested | Verify |
| 11 | Shared clipboard configured if required | Verify |
| 12 | Shared folder configured if required | Verify |
| 13 | Known-good snapshot created | Verify |
| 14 | Screenshots captured for documentation | Verify |
| 15 | README and FAQ updated | Verify |

Mark an item complete only after you have confirmed it on your own system.

---

# 14. Useful Resources

### Oracle VirtualBox

- Downloads: https://www.virtualbox.org/wiki/Downloads
- Documentation: https://www.virtualbox.org/wiki/Documentation
- Guest Additions: https://docs.oracle.com/en/virtualization/virtualbox/7.2/user/guestadditions.html

### Kali Linux

- Official downloads: https://www.kali.org/get-kali/
- Official documentation: https://www.kali.org/docs/

### Project Documentation

- **GitHub Repository:** https://github.com/devkrishnanagda22/NETWORKWALKS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP
- **Video Demonstration:** https://www.youtube.com/watch?v=1r2KePtM3P8

---

## Final Note

This FAQ is intended to help users understand and troubleshoot a VirtualBox-based Kali Linux cybersecurity lab.

Hardware recommendations are general guidance and may need to be adjusted for individual computers. Follow the official assignment instructions whenever they specify different requirements.

**Practice responsibly. Test only systems you own or are explicitly authorized to assess.**
