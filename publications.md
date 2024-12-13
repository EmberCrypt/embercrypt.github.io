---
layout: publications
title: EmberCrypt
subTitle: "Publications"
description: Published articles
pubs:
 - name: Disabling censorship on SPC5606B chips
   link: /assets/pubs/Disabling_censorship_on_SPC5606B_chips.pdf
   ref: Van den Herrewegen, J., Adam, F. (2024). Disabling censorship on SPC5606B chips.
   abstract: "We propose an attack to disable the protection mechanism on a censored NXP SPC5606B, configured to use the public password, which is the recommended secure configuration according to the datasheet. The on-chip bootloader requires a password (depending on the security setting either public or private) to download a secondary bootloader. On a censored chip, a flash memory read returns the same 16 byte block at address 0. Building on previous attacks on this chip (in the private password configuration), we uncover several anomalies when exposed to Voltage - and Electromagnetic Fault Injection (V-FI & EMFI), ultimately leading to the uncensoring of the device and giving us full read/write access to its flash memory. We establish a power consumption side channel to observe the boot process. We uncover various anomalies of the chip when exposed to faults, among which 1. the censorship mechanism which returns 16 byte blocks other than the starting block 2. the chip allows download with the private password but remains censored. Zooming in on this, we find the offset that completely disables censorship, giving us full access to the flash memory of the device. We confirmed this attack both on an empty test chip we control, as well as a real life Nissan Electronic Control Unit. To the best of our knowledge, this is the first published attack on this chip in the public password configuration. Finally, we discuss the plausible causes of the anomalous behavior and revisit the use and limits of fully automated approaches to fault injection"


 - name: Automotive Firmware Analysis and Extraction Techniques
   link: /assets/pubs/Automotive_Firmware_Extraction_Analysis.pdf
   ref: Van den Herrewegen, J. (2021). PhD Thesis. University of Birmingham, UK.
   abstract: "An intricate network of embedded devices, called Electronic Control Units (ECUs), is
responsible for the functionality of a modern vehicle. Every module processes a myriad
of information and forwards it on to other nodes on the network, typically an automotive
bus such as the Controller Area Network (CAN). Analysing embedded device software,
and automotive in particular, brings many challenges.
The analyst must, especially in the notoriously secretive automotive industry, first lift
the ECU firmware from the hardware, which typically prevents unauthorised access. In
this thesis, we address this problem in two ways: (i) We detail and bypass the access
control mechanism used in diagnostic protocols in ECU firmware. Using existing diagnos-
tic functionality, we present a generic technique to download code to RAM and execute
it, without requiring physical access to the ECU. We propose a generic firmware readout
framework on top of this, which only requires access to the CAN bus. (ii) We analyse
various embedded bootloaders and combine dynamic analysis with low-level hardware
fault attacks, resulting in several fault-injection attacks which bypass on-chip readout
protection.
We then apply these firmware extraction techniques to acquire immobiliser firmware
by two different manufacturers, from which we reverse engineer the DST80 cipher and
present it in full detail here. Furthermore, we point out flaws in the key generation
procedure, also recovered from the ECU firmware, leading to a full key recovery based on
publicly readable transponder pages."


 - name: Cutting Through the Complexity of Reverse Engineering Embedded Devices
   link: /assets/pubs/incision.pdf
   ref: Thomas, S. L., Van den Herrewegen, J., Vasilakis, G., Chen, Z., Ordean, M., & Garcia, F. D. (2021). Cutting Through the Complexity of Reverse Engineering Embedded Devices. IACR Transactions on Cryptographic Hardware and Embedded Systems, 2021(3), 360–389. https://doi.org/10.46586/tches.v2021.i3.360-389
   abstract: "Performing security analysis of embedded devices is a challenging task.
They present many difficulties not usually found when analyzing commodity systems:
undocumented peripherals, esoteric instruction sets, and limited tool support. Thus,
a significant amount of reverse engineering is almost always required to analyze such
devices. In this paper, we present Incision, an architecture and operating-system
agnostic reverse engineering framework. Incision tackles the problem of reducing the
upfront effort to analyze complex end-user devices. It combines static and dynamic
analyses in a feedback loop, enabling information from each to be used in tandem
to improve our overall understanding of the firmware analyzed. We use Incision to
analyze a variety of devices and firmware. Our evaluation spans firmware based on
three RTOSes, an automotive ECU, and a 4G/LTE baseband. We demonstrate that
Incision does not introduce significant complexity to the standard reverse engineering
process and requires little manual effort to use. Moreover, its analyses produce correct
results with high confidence and are robust across different OSes and ISAs."


 - name: "Fill your Boots: Enhanced Embedded Bootloader Exploits via Fault Injection and Binary Analysis"
   link: /assets/pubs/Fill_your_Boots.pdf
   ref: "Van den Herrewegen, J., Oswald, D., Garcia, F. D. ., & Temeiza, Q. (2020). Fill your Boots: Enhanced Embedded Bootloader Exploits via Fault Injection and Binary Analysis. IACR Transactions on Cryptographic Hardware and Embedded Systems, 2021(1), 56–81. https://doi.org/10.46586/tches.v2021.i1.56-81"
   abstract: "The bootloader of an embedded microcontroller is responsible for guarding the device’s internal (flash) memory, enforcing read/write protection mechanisms. Fault injection techniques such as voltage or clock glitching have been proven successful in bypassing such protection for specific microcontrollers, but this often requires expensive equipment and/or exhaustive search of the fault parameters. When multiple glitches are required (e.g., when countermeasures are in place) this search becomes of exponential complexity and thus infeasible. Another challenge which makes embedded bootloaders notoriously hard to analyse is their lack of debugging capabilities. This paper proposes a grey-box approach that leverages binary analysis and advanced software exploitation techniques combined with voltage glitching to develop a powerful attack methodology against embedded bootloaders. We showcase our techniques with three real-world microcontrollers as case studies: 1) we combine static and on-chip dynamic analysis to enable a Return-Oriented Programming exploit on the bootloader of the NXP LPC microcontrollers; 2) we leverage on-chip dynamic analysis on the bootloader of the popular STM8 microcontrollers to constrain the glitch parameter search, achieving the first fully-documented multi-glitch attack on a real-world target; 3) we apply symbolic execution to precisely aim voltage glitches at target instructions based on the execution path in the bootloader of the Renesas 78K0 automotive microcontroller. For each case study, we show that using inexpensive, open-design equipment, we are able to efficiently breach the security of these microcontrollers and get full control of the protected memory, even when multiple glitches are required. Finally, we identify and elaborate on several vulnerable design patterns that should be avoided when implementing embedded bootloaders."

 - name: "Dismantling DST80-based Immobiliser Systems"
   link: /assets/pubs/DST80.pdf
   ref: "Wouters, L., Van den Herrewegen, J., Garcia, F. D., Oswald, D., Gierlichs, B., & Preneel, B. (2020). Dismantling DST80-based Immobiliser Systems. IACR Transactions on Cryptographic Hardware and Embedded Systems, 2020(2), 99–127. https://doi.org/10.13154/tches.v2020.i2.99-127"
   abstract: "Car manufacturers deploy vehicle immobiliser systems in order to prevent
car theft. However, in many cases the underlying cryptographic primitives used to
authenticate a transponder are proprietary in nature and thus not open to public
scrutiny. In this paper we publish the proprietary Texas Instruments DST80 cipher
used in immobilisers of several manufacturers. Additionally, we expose serious flaws
in immobiliser systems of major car manufacturers such as Toyota, Kia, Hyundai
and Tesla. Specifically, by voltage glitching the firmware protection mechanisms of
the microcontroller, we extracted the firmware from several immobiliser ECUs and
reverse engineered the key diversification schemes employed within. We discovered
that Kia and Hyundai immobiliser keys have only three bytes of entropy and that
Toyota only relies on publicly readable information such as the transponder serial
number and three constants to generate cryptographic keys. Furthermore, we present
several practical attacks which can lead to recovering the full 80-bit cryptographic
key in a matter of seconds or permanently disabling the transponder. Finally, even
without key management or configuration issues, we demonstrate how an attacker
can recover the cryptographic key using a profiled side-channel attack. We target the
key loading procedure and investigate the practical applicability in the context of
portability. Our work once again highlights the issues automotive vendors face in
implementing cryptography securely"

 - name: "Beneath the Bonnet: a Breakdown of Diagnostic Security"
   link: /assets/pubs/BtB.pdf
   ref: "Van den Herrewegen J., Garcia F.D. (2018) Beneath the Bonnet: A Breakdown of Diagnostic Security. In: Lopez J., Zhou J., Soriano M. (eds) Computer Security. ESORICS 2018. Lecture Notes in Computer Science, vol 11098. Springer, Cham. https://doi.org/10.1007/978-3-319-99073-6_15"
   abstract: "An Electronic Control Unit (ECU) is an automotive com-
puter essential to the operation of a modern car. Diagnostic protocols
running on these ECUs are often too powerful, giving an adversary full
access to the ECU if they can bypass the diagnostic authentication mech-
anism. Firstly, we present three ciphers used in the diagnostic access
control, which we reverse engineered from the ECU firmware of four
major automotive manufacturers. Next, we identify practical security
vulnerabilities in all three ciphers, which use proprietary cryptographic
primitives and a small internal state. Subsequently, we propose a generic
method to remotely execute code on an ECU over CAN exclusively
through diagnostic functions, which we have tested on units of three ma-
jor automotive manufacturers. Once authenticated, an adversary with
access to the CAN network can download binary code to the RAM of
the microcontroller and execute it, giving them full access to the ECU
and its peripherals, including the ability to read/write firmware at will.
Finally, we conclude with recommendations to improve the diagnostic
security of ECUs."
---
