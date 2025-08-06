---
description: New Technology File System (NTFS)
---

# NTFS

### Alternate Data Stream (ADS)

Each file has at least one data stream (`$DATA`). However, a file can contain more than one data stream — a feature known as Alternate Data Stream (_ADS_). The concept of _ADS_ is specific to _NTFS_.

What is `$DATA`?

In _NTFS_, a file consists of multiple attributes, where one of them is `$DATA`, which holds the actual content of a file.&#x20;

As mentioned earlier, _NTFS_ allows multiple Alternate Data Streams (_ADS_) to be defined on a file. However, the additional content stored via _ADS_ is hidden by default, and thus does not alter the file's visible size in the file explorer. This feature can be exploited by malicious threat actors to hide malicious content.&#x20;

> Key point to note: File explorer does not display ADS content by default&#x20;

