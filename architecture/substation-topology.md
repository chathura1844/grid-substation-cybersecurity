# Electrical Substation — OT Network Architecture

## 1. Project Objective

Design and document a conceptual electrical substation network architecture to study industrial cybersecurity, SCADA communication, intelligent electronic devices (IEDs), and secure network segmentation.

The project explores security engineering concepts relevant to modern electrical grid automation environments.

## 2. Substation Architecture Overview

A typical digital substation includes multiple operational layers:

### Station Level

The station level provides centralized supervision, monitoring, and engineering access.

Example components:
- SCADA Server
- Human-Machine Interface (HMI)
- Engineering Workstation
- Substation Gateway
- Network Management System

### Bay Level

The bay level contains protection and control devices responsible for individual electrical bays.

Example components:
- Protection Relays
- Bay Control Units
- Intelligent Electronic Devices (IEDs)
- Circuit Breaker Controllers

### Process Level

The process level interfaces with electrical equipment and field measurements.

Example components:
- Merging Units
- Current Transformers (CTs)
- Voltage Transformers (VTs)
- Circuit Breakers
- Sensors and Measurement Devices

## 3. Industrial Communication Protocols

| Protocol | Typical Purpose | Security Considerations |
|---|---|---|
| IEC 61850 MMS | Supervisory communication with IEDs | Access control, network segmentation, secure communications |
| IEC 61850 GOOSE | Fast event and protection messaging | Message authenticity, integrity, and network isolation |
| IEC 61850 Sampled Values | Transmission of electrical measurement samples | Network availability, timing, and traffic integrity |
| DNP3 | Communication between SCADA systems and remote devices | Authentication, command authorization, secure deployment |
| Modbus TCP | Communication with certain industrial devices | Limited native security, restricted access, traffic monitoring |

Protocol use varies by substation design and equipment vendor.

## 4. Conceptual Network Segmentation

The proposed architecture separates the environment into security zones.

| Security Zone | Components | Security Objective |
|---|---|---|
| Enterprise / External | Corporate systems, remote users | Prevent unrestricted access to OT |
| Substation DMZ | Remote access gateway, monitoring services | Control and monitor access between networks |
| Station Network | SCADA, HMI, engineering workstation | Protect supervisory and engineering operations |
| Bay Network | Protection relays, IEDs, bay controllers | Restrict access to protection and control devices |
| Process Network | Merging units, field interfaces | Protect time-sensitive measurement and control traffic |

Logical segmentation must be adapted to operational requirements, particularly latency-sensitive protection traffic.

## 5. Proposed Security Controls

### Network Security
- Separate enterprise and OT communication paths.
- Apply least-privilege firewall rules at appropriate security boundaries.
- Restrict engineering access to authorized devices.
- Use dedicated management access where practical.
- Monitor relevant network traffic.

### Device Security
- Harden SCADA servers and engineering workstations.
- Control configuration changes to protection relays.
- Protect device credentials and administrative interfaces.
- Maintain approved configuration backups.

### Monitoring
- Collect relevant security logs.
- Monitor unauthorized management connections.
- Investigate unexpected control commands.
- Baseline normal industrial communications.

## 6. Cybersecurity Framework Alignment

The architecture draws on security principles from:

- IEC 62443 — Industrial automation and control system cybersecurity
- IEC 62351 — Security for power system communication
- NIST SP 800-82 — Operational technology security
- Defense in depth and least privilege

These are design references, not claims of formal compliance.

## 7. Planned Hands-On Validation

Future work may include:

1. Build a simulated substation network.
2. Configure station and bay network segmentation.
3. Generate authorized industrial protocol traffic.
4. Capture and analyze protocol communications.
5. Test permitted and unauthorized access paths.
6. Document security observations and supporting evidence.

## 8. Current Project Status

**Completed:** Initial conceptual architecture documentation.

**Planned:** Substation simulation, protocol analysis, network security configuration, threat modeling, and hands-on validation.

No operational substation deployment or completed security testing is claimed in this document.

## 9. Conclusion

This architecture provides a foundation for studying cybersecurity risks and protective controls in electrical grid automation environments.

The next phase will focus on network segmentation, IEC 61850 communication security, and practical validation within a simulated lab.
