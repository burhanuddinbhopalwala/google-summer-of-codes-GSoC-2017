# GSoC-2016_2017_18-proposals
## GSoC-2015_16 rejected proposal details
(Accpted proposal to follow - scroll down below)

### AUTOMATED NETWORK INSTALLATION OF LINUX SERVER (ENHANCING PXE BOOT)
Detailed proposal [here](./1_GSoC_2016_CentOS_PXEBoot_Proposal_REJECTED.pdf)

#Linux #CentOS #Networking #PXEBoot
#### Abstract

We know CentOS already has a PXE which is generally not recommended and comparatively slower as compared to the below approach that I jotted down below
In this approach, to install a Linux server on a PC WITHOUT ANY DVD OR ANY EXTRA BOOTABLE DRIVES, we will be only using a LAN network from 1 system to another.

1. Existing problem/Linux features we are using:
The Kickstart method of Fedora Linux installation can greatly reduce the length of time it takes to install the operating system. Time is saved not only because a network connection can be faster than using CDs, but also because it can be left unattended to install a predetermined Linux configuration.

A Kickstart server connected to an isolated wireless network dedicated to the purpose may be a good idea for data centers with hundreds of Linux servers.

A recent standard called PXE allows you to run kickstart without a CD ROM if you configure the NIC card to do a network boot from a specially configured DHCP server. The topic is beyond the scope of this document, but it may be interesting for readers with more complex projects to research this option more.

#### Solution/Advantages of Enhance PXE Boot:

This Enhances the PXE Boot functionality as a solution and has the following advantages:

1: Users with no info on how to install the LINUX server can install it without any settings to be done all partitioning and rest settings like password set or KDUMP setting are done automatically.

2: Less Time than DVD and any other bootable drives, through Network installation takes 1/2 the time of installation then through DVDs and BOOTABLE Drives.

3: Very Easy (then existing CentOS PXE boot) and not replace the existing OS bootloader from the targeted system. This is one of the bottlenecks at the user's end who is going to install the Linux server whether our existing OS should remain or not, Through this Network Installation, it DUAL BOOT the System with Existing Server and OS.

4: With 1 System main we can install any server with many systems simultaneously without any DVDs or Bootable Drives. Not having any fear/danger, risk-free boot, and always recommended if possible.

#### Implementations & Timelines:
##### Phase 1: (3 Weeks)
- First, set up a create a yum server and download the desired rpm (Redhat Packet Manager). This initial step also requires setting up multiple clients and servers of different bandwidths that will eventually help us to test & extend the final solution across different Linux machines of variable bandwidths.

- We will be using all bootable files, Kickstart files, and anaconda cfg files in making this project's initial skeleton repo. The major change for enhancing the PXE boot functionality.

- Integrating the Trivial File Transfer Protocol (TFTP) protocol which is the fastest to-date protocol for transferring the booting files. This would be an important change as the way it will be written must be machine agnostic.

##### Phase 2: (3 Weeks):

- We can also integrate the CLI capabilities but to make it robust we can generate an executable file or JAVA jar to make the process fully automated and error-free.

- After this, we convert it into a yum plugin that can work the whole and enhance the PXE BOOT functionality of CentOS.

##### Phase 3: (final phase - 3 Weeks)

- Testing the code and performance metrics generation for the final Report.

- Testing the solution on different bandwidths across clients and servers.

- Refactoring and changes adhering to the GSoC & CentOS standard and final mentor’s feedback.

---
## GSoC-2017_18 accepted proposal details

### iRODS client for ImageJ
Detailed proposal [here](./2_GSoC_2017_18_INCF_Belgium_Proposal_ACCEPTED.pdf)

#INCF-National-Node-of-Belgium #iRODS #ImageJ #Jargon API's

This project aims to develop an ImageJ plugin so that the user (an iRODS client) can upload/download datasets from iRODS. And it also provides GUI for simplicity of a user

### Implementation abstract:

-   As an implementation part first, I use the Jargon Core APIs so that we can Jargon-core APIs implement the iRODS protocol and allow the development of iRODS-enabled Java applications. This API is especially useful for developing mid-tier applications and services, as well as desktop clients (such as I drop).

These libraries also provide a foundation for a new set of interfaces that will come with iRODS

For adding a GUI to the plugin, I will use AWT or Swing components like TextFields, Label, Buttons, etc. By using AWT APIs and Swings. We can also use the `GenericDialog` class to building a plugin and the plugin will be macro-compatible with this or, we can use it in the traditional way

### Implementation details:

- Initially, there would be approx. 10 libraries in Jargon API each one has its own function so we start with a basic skeleton and then Authenticate our connection with iRODS using the Jargon-core library (base library for implementing the protocol) which constitutes several methods for implementing the connection-authenticating methods in `AuthenticationConnection` class etc and use initialize connection methods in such as initialize a `connection()` methods in `Connection` class

- Then, we can check our connection by using Jargon Data Utils library in which we  can use the `ConnectionTester` class for implementing the above features

- After this, we can use the Jargon Data Utils library again for adding the functionality to manage the iRODS data such as building the tree using the `TreeUtility` class methods

- For any type of Account information / Profile Information we may use Jargon User Profile library

- The main part for uploading or downloading a directory from iRODS we use `getUploadDirectory()`  or `deleteUploadDirectory()` method in the JargonDataUtilslibrary

- For downloading a file from iRODS we use the `getFile()` method from Jargon Data Utils library. For the rest of the APIs, we required we can further Reference the Google

- Further for adding GUI to the plugin we design it in a traditional way or as per the Mentors guidance. We may use `GenericDialogClass` for macro-compatible plugin

- Lastly, We integrate the plugin with the DropBox account plugin that was previously made

---

## Authors

-   **Burhanuddin Bhopalwala** - _Initial work_ - [GitHub](https://github.com/burhanuddinbhopalwala)

## Acknowledgments

-   https://irods.org/clients/
-   https://github.com/DICE-UNC/jargon
-   https://imagej.nih.gov/ij/download.html

## License

[MIT](https://choosealicense.com/licenses/mit/)
