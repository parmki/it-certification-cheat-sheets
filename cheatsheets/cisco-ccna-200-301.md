# Cisco Certified Network Associate (CCNA 200-301) Cheat Sheet

A concise reference for Cisco switching, routing protocols (OSPF), VLANs, trunking (802.1Q), and network automation.

> **Interactive Practice**: Drill scenario questions with keyboard navigation on [BenchCert CCNA 200-301 Hub](https://benchcert.app/cert/cisco-ccna-200-301).

---

## 📊 Exam Blueprint & Domain Weights
- **Domain 1**: Network Fundamentals (**20%**)
- **Domain 2**: Network Access (**20%**)
- **Domain 3**: IP Connectivity (**25%**)
- **Domain 4**: IP Services (**10%**)
- **Domain 5**: Security Fundamentals (**15%**)
- **Domain 6**: Automation and Programmability (**10%**)

**Passing Score**: 825 / 1000  
**Format**: ~100 Questions | 120 Minutes

---

## 🔄 OSPF (Open Shortest Path First) Essentials
- **Protocol Type**: Link-State Interior Gateway Protocol (IGP).
- **Metric**: Cost ($\text{Cost} = \frac{\text{Reference Bandwidth}}{\text{Interface Bandwidth}}$). Default reference is 100 Mbps.
- **Multicast Addresses**:
  - `224.0.0.5`: All OSPF Routers.
  - `224.0.0.6`: All Designated Routers (DR / BDR).
- **OSPF Neighbor Adjacency States**:
  1. **Down**: No OSPF hello packets received.
  2. **Init**: Received hello packet, but local Router ID not seen in neighbor list.
  3. **2-Way**: Bidirectional communication established. DR/BDR election occurs on multi-access networks.
  4. **ExStart**: Master/Slave relationship negotiated and initial sequence number chosen.
  5. **Exchange**: Routers exchange Database Description (DBD) packets.
  6. **Loading**: Routers send Link-State Requests (LSR) and receive Link-State Updates (LSU).
  7. **Full**: Link-state databases are 100% synchronized. Full adjacency reached.

---

## 🔌 Switching & VLANs (802.1Q)
- **Native VLAN**: Untagged traffic crossing an 802.1Q trunk. Must match on both ends of the trunk link (mismatches cause CDP native VLAN mismatch warnings and potential STP loops).
- **Spanning Tree Protocol (STP / 802.1D vs RSTP / 802.1w)**:
  - Root bridge election: Lowest Bridge ID wins ($\text{Priority} + \text{System ID Extension} + \text{MAC Address}$). Default priority is `32768`.
  - RSTP Port Roles: Root, Designated, Alternate, Backup.
  - RSTP Port States: Discarding, Learning, Forwarding.

---

### Resources
- [BenchCert Cisco CCNA Hub](https://benchcert.app/cert/cisco-ccna-200-301)
- [Official Cisco CCNA 200-301 Blueprint](https://learningnetwork.cisco.com/s/ccna-exam-topics)
