# DFRWS 2005 Rhino Hunt — Digital Forensics Investigation

A digital forensics investigation based on the **DFRWS 2005 RODEO Challenge (Rhino Hunt)** dataset.

The investigation involved the examination of a USB disk image and three network traces to recover rhinoceros images, reconstruct relevant network activity, examine deleted and hidden evidence, and establish connections between the USB device and network traffic.

## Investigation Objective

The primary objectives were to:

* Recover at least nine unique rhinoceros images.
* Analyze the provided network traces.
* Examine the USB disk image.
* Recover deleted and hidden files.
* Identify relevant FTP, Telnet, and HTTP activity.
* Determine what happened to the suspect's hard drive and USB key.
* Establish whether evidence from the USB image was connected to the network captures.
* Document the findings in a forensic investigation report.

## Evidence Examined

The investigation included:

| Evidence      | Description                      |
| ------------- | -------------------------------- |
| `RHINOUSB.dd` | Forensic image of the USB device |
| `rhino.log`   | Network trace                    |
| `rhino2.log`  | Network trace                    |
| `rhino3.log`  | Network trace                    |

### Evidence Hashes

```text
c0d0093eb1664cd7b73f3a5225ae3f30  rhino.log
cd21eaf4acfb50f71ffff857d7968341  rhino2.log
7e29f9d67346df25faaf18efcd95fc30  rhino3.log
80348c58eec4c328ef1f7709adc56a54  RHINOUSB.dd
```

## Tools Used

* Autopsy
* Wireshark
* John the Ripper
* Kali Linux

## Investigation Findings

### 1. Telnet / FTP Account

The recovered `diary.doc` identifies **Jeremy** as the person who provided the account.

The account identified during the investigation was:

```text
Username: gnome
Password: gnome123
```

The credentials were also observed in the Telnet authentication traffic.

## 2. Relevant Network Transfers

The network traces contained several relevant file transfers:

```text
rhino1.jpg    → FTP
rhino2.jpg    → contained within contraband.zip
rhino3.jpg    → FTP
rhino4.jpg    → HTTP
rhino5.gif    → HTTP
rhino.exe     → HTTP
```

Network stream reconstruction was used to identify and recover the transferred files.

## 3. Hard Drive

The recovered diary contained a statement indicating that the hard drive had been erased and subsequently thrown into the Mississippi River.

## 4. USB Key

The diary indicated that the USB key had been reformatted.

Despite the reformatting, recoverable evidence remained within the USB disk image.

## 5. Evidence Recovered from the USB Image

The investigation recovered:

```text
rhino2.jpg
rhino6.jpg
rhino7.jpg
rhino8.gif
rhino9.gif
rhino10.jpg
diary.doc
```

Additional alligator image files were also recovered.

File carving and steganographic analysis were used during the examination.

## 6. USB and Network Evidence Correlation

A significant connection was established between the USB evidence and network traffic.

The `rhino2.jpg` recovered from the USB image was identified as the same `rhino2.jpg` recovered from the network-related archive.

Cryptographic hash comparison was used to establish that the files were identical.

## Forensic Techniques

The investigation involved:

* Disk image examination
* File carving
* Deleted-file recovery
* Network traffic analysis
* FTP/HTTP stream reconstruction
* Telnet session analysis
* Password recovery
* Steganographic analysis
* Hash comparison
* Evidence correlation

## Recovered Rhino Images

A total of **10 unique rhinoceros images** were recovered from the supplied evidence.

The recovered files included images obtained from both network traces and the USB disk image.

## Report

The complete investigation report is available here:

**[DFRWS 2005 Digital Forensics Investigation Report](Report/DFRWS_2005_Digital_Forensics_Investigation_Report.pdf)**

## Disclaimer

This repository documents an educational digital forensics investigation based on the DFRWS 2005 RODEO Challenge dataset.

The original evidence files are not necessarily redistributed with this repository. The report and documentation are provided to demonstrate the investigation methodology, analysis process, and findings.
