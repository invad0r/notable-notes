---
tags: [Notebooks]
title: meltdown spectre
created: '2019-07-30T06:19:49.177Z'
modified: '2019-11-15T06:40:42.225Z'
---

# meltdown spectre

- https://meltdownattack.com/ or https://spectreattack.com/
- https://googleprojectzero.blogspot.de/2018/01/reading-privileged-memory-with-side.html
- https://cyber.wtf/2017/07/28/negative-result-reading-kernel-memory-from-user-mode/
- https://www.kb.cert.org/vuls/id/584653


- variant 1: `CVE-2017-5753` bounds-check bypass aka spectre 
- variant 2: `CVE-2017-5715` branch target injection aka spectre 
- variant 3: `CVE-2017-5754` rogue data cache load aka meltdown

| |Spectre|Meltdown|
|:--|:--|:--|
|CPU mechanism for triggering|Speculative execution from branch prediction|Out-of-order execution|
|Affected platforms|CPUs that perform speculative execution from branch prediction|CPUs that allow memory reads in out-of-order instructions|
|Difficulty of successful attack|High - Requires tailoring to the software environment of the victim process|Low - Kernel memory access exploit code is mostly universal|
|Impact|Cross- and intra-process (including kernel) memory disclosure|Kernel memory disclosure to userspace|
|Software mitigations|Variant 1: Compiler changes. Web browser updates to help prevent exploitation from JavaScript; Variant 2: Indirect Branch Restricted Speculation (IBRS). Note: The software mitigation for Spectre variant 2 requires CPU microcode updates	Kernel page-table isolation (KPTI)|Kernel page-table isolation (KPTI)|


---
## Testing for vuln

https://github.com/raphaelsc/Am-I-affected-by-Meltdown

https://www.cyberciti.biz/faq/check-linux-server-for-spectre-meltdown-vulnerability/
