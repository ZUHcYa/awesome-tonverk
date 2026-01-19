# Available Routing Options

![OS Requirement](https://img.shields.io/badge/OS-All_Versions-blue?style=flat-square&logo=elektron)
![Category](https://img.shields.io/badge/Category-Reference-lightgrey?style=flat-square)

Understanding the available routing destinations is helpful to assess possible Tonverk use-cases and signal chains.

---
This diagram visualizes the possible audio paths within Tonverk: From physical Inputs to Tracks, Busses, and physical Outputs.

```mermaid
flowchart LR
 subgraph s1["Physical Outputs"]
        OutCD["OutCD"]
        OutEF["OutEF"]
        OutAB["OutAB"]
  end
 subgraph s2["Physical Input"]
        InAB["InAB"]
  end
    TRACK["TRACK"] --> MixAB["MixAB"] & OutCD & OutEF & BUS["BUS"]
    BUS --> MixAB & OutCD & OutEF
    SEND["SEND"] --> MixAB & OutCD & OutEF
    InAB["InAB"] --> TRACK & BUS & MixAB & OutCD & OutAB["OutAB"] & OutEF
```
    Direct Monitoring: Inputs can be routed directly to outputs, bypassing the internal tracks.

    Bus Processing: Routing Tracks to the BUS allows for group processing before hitting the main outs.