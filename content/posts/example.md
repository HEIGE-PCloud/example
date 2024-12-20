---
title: '利用 Seclogon PPID Spoofing 实现 dump lsass 内存'
date: 2024-12-04T17:28:09+08:00

authors: [dre4merp]

tags: []
categories: []
series: []

lightgallery: true
---

``` mermaid
graph TD
    subgraph advapi32.dll
        A(CreateProcessWithTokenW) --> C(CreateProcessWithLogonCommonW)
        B(CreateProcessWithLogonW) --> C
        C --> D(c_SeclCreateProcessWithLogonW)
    end

    subgraph seclogon.dll
        D --> E(SeclCreateProcessWithLogonW)
        E --> F(SlrCreateProcessWithLogon)
    end
```
