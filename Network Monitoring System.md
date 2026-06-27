# Network Monitoring System
---

## Chapter 1 – Introduction to Network Monitoring System (NMS)

### 1. What is Network Monitoring?

**Definition:**
Network Monitoring is the continuous process of monitoring the health, availability, and performance of network devices and services to detect issues before they impact users.

The primary goal of Network Monitoring is to:

* Minimize downtime
* Improve network performance
* Detect failures automatically
* Help NOC engineers respond quickly
* Ensure SLA compliance

---

### 2. Why is Network Monitoring Required?

In large organizations, there may be thousands of devices such as routers, switches, firewalls, servers, and access points.

Without a monitoring system:

* Device failures remain undetected until users report them.
* Troubleshooting starts only after business services are affected.
* Downtime increases.
* SLA violations become more frequent.

A Network Monitoring System continuously checks devices and immediately notifies the NOC team when an issue occurs.

---

### 3. What Does a Monitoring Tool Monitor?

A monitoring tool can monitor:

* Device Availability (Up/Down)
* CPU Utilization
* Memory Utilization
* Disk Usage
* Interface Status
* Bandwidth Utilization
* Network Latency
* Packet Loss
* Jitter
* Temperature
* Fan Status
* Power Supply Status
* VPN Status
* WAN Link Status
* Server Health
* Application Availability

---

### 4. Benefits of Network Monitoring

* Detects failures automatically
* Reduces downtime
* Improves network availability
* Provides real-time visibility
* Helps meet SLA requirements
* Reduces manual monitoring effort
* Improves incident response time

---

### 5. Monitoring vs Troubleshooting

| Monitoring               | Troubleshooting                 |
| ------------------------ | ------------------------------- |
| Detects problems         | Resolves problems               |
| Continuous process       | Performed after an issue occurs |
| Done by monitoring tools | Done by engineers               |
| Generates alerts         | Fixes the root cause            |

---

## Chapter 1 Flow

```
Network Devices
(Routers, Switches, Firewalls, Servers)
            │
            ▼
Network Monitoring Tool
            │
            ▼
Problem Detected
            │
            ▼
Alert Generated
            │
            ▼
NOC Engineer
            │
            ▼
Issue Resolved
```

---

## Chapter 2 – How Network Monitoring Works
---

## 1. How Does a Monitoring Tool Communicate with Devices?

Monitoring tools communicate with devices using various protocols.

The most common protocol is:

**SNMP (Simple Network Management Protocol)**

---

## 2. What is SNMP?

**Definition:**

SNMP is a protocol used to monitor and manage network devices by collecting information such as CPU usage, memory usage, interface status, bandwidth utilization, and device health.

---

## 3. Components of SNMP

### SNMP Manager(161 UDP)

The monitoring system that collects information from network devices.

Examples:

* ScienceLogic
* SolarWinds
* PRTG
* Nagios

---

### SNMP Agent(162 UDP)

A software component running on the network device that responds to SNMP requests.

---

### MIB (Management Information Base)

A database inside the device that stores management information such as:

* CPU Usage
* Memory Usage
* Interface Status
* Temperature
* Uptime

---

### OID (Object Identifier)

Each monitored parameter inside the MIB has a unique numerical identifier called an OID.

Example:

CPU → OID

Memory → OID

Interface Status → OID

---

## 4. Polling

**Definition:**

Polling is the process in which the monitoring tool periodically requests information from network devices.

Example:

Every 1 minute:

* CPU Usage
* Memory Usage
* Interface Status

---

## 5. SNMP Trap

**Definition:**

An SNMP Trap is an unsolicited message sent by a network device to the monitoring system whenever an important event occurs.

Examples:

* Interface Down
* Device Reboot
* Power Supply Failure

Unlike polling, traps are sent immediately.

---

## 6. Polling vs Trap

| Polling                              | Trap                                   |
| ------------------------------------ | -------------------------------------- |
| Monitoring tool requests information | Device sends information automatically |
| Pull mechanism                       | Push mechanism                         |
| Periodic                             | Immediate                              |
| May have delay                       | Instant notification                   |
| Port 162 UDP                         | Port 161 UDP                           |
---

## Chapter 2 Flow

```text
Network Device
       │
       ▼
SNMP Agent
       │
       ▼
MIB
(CPU, Memory, Interfaces)
       ▲
       │
SNMP Manager
(ScienceLogic/SolarWinds)
       │
       ▼
Dashboard Updated
```

---

# Chapter 3 – Event, Alert & Incident Lifecycle

---

## 1. Threshold

A threshold is a predefined limit used by the monitoring tool to determine whether a metric is normal or abnormal.

Example:

CPU < 70% → Normal

CPU 70–85% → Warning

CPU 85–95% → Major

CPU > 95% → Critical

---

## 2. Event

An Event is any occurrence detected by the monitoring tool.

Examples:

* CPU Usage Increased
* Interface Down
* Device Restarted
* Memory Usage Increased

Not every event requires action.

---

## 3. Alert

An Alert is an event that requires attention or action based on predefined thresholds or rules.

Examples:

* Router Down
* Interface Down
* CPU above threshold
* High Memory Usage
* Power Supply Failure

---

## 4. Severity Levels

Most monitoring tools classify alerts into different severity levels.

Typical severity levels:

* Information
* Warning
* Minor
* Major
* Critical

---

## 5. Incident

An Incident is created when an alert requires investigation by the NOC team.

The incident is generally created in an ITSM tool such as ServiceNow or BMC Remedy.

---

## 6. Alert Suppression

Alert Suppression prevents multiple alerts caused by the same root issue from generating unnecessary incidents.

Example:

If a router loses power, all interfaces become unreachable.

Instead of generating multiple incidents, only one incident is created for the root cause.

---

## 7. Event Correlation

Event Correlation is the process of analyzing multiple related events to identify the actual root cause.

Example:

Switch Down

↓

Access Point Down

↓

Printer Down

↓

IP Phone Down

Instead of treating these as separate issues, the monitoring tool identifies the switch failure as the root cause.

---

## Chapter 3 Flow

```text
Device
   │
   ▼
SNMP Polling
   │
   ▼
Threshold Crossed
   │
   ▼
Event Created
   │
   ▼
Alert Generated
   │
   ▼
Severity Assigned
   │
   ▼
Incident Created
   │
   ▼
ITSM Tool
   │
   ▼
NOC Engineer
   │
   ▼
Issue Resolved
   │
   ▼
Incident Closed
```

---

# 🎯 Interview Questions (Chapters 1–3)

### Chapter 1

1. What is Network Monitoring?
2. Why do organizations use Network Monitoring Systems?
3. What are the benefits of Network Monitoring?
4. What devices can be monitored?
5. What is the difference between Monitoring and Troubleshooting?

---

### Chapter 2

6. What is SNMP?
7. What are the components of SNMP?
8. What is an SNMP Manager?
9. What is an SNMP Agent?
10. What is a MIB?
11. What is an OID?
12. What is Polling?
13. What is an SNMP Trap?
14. What is the difference between Polling and Trap?
15. Which protocol is most commonly used for network monitoring?

---

### Chapter 3

16. What is a Threshold?
17. What is an Event?
18. What is an Alert?
19. What is the difference between an Event and an Alert?
20. What is an Incident?
21. What are the common Alert Severity Levels?
22. What is Alert Suppression?
23. What is Event Correlation?
24. What is the complete lifecycle from Event to Incident Closure?
25. How does a monitoring tool help improve SLA compliance?

---

# 📌 My Plan for These Notes

Bro, I don't want these to be just "notes." I want them to become your **NOC Bible**.

We'll eventually build **15–20 chapters** covering topics like:

* Device Discovery
* ICMP
* Syslog
* WMI
* APIs
* ScienceLogic (SL1)
* SolarWinds
* Dynatrace
* ITSM Integration
* Remote Access
* NOC Workflow
* Incident Management
* Change Management
* Problem Management
* SLA & OLA
* Dashboards
* Root Cause Analysis
* High Availability
* Enterprise NOC Architecture

By the end, you'll have a complete **beginner-to-advanced NOC handbook** that you can revise before interviews at Deloitte, DXC, Accenture, TCS, Wipro, Capgemini, and similar companies. I think this will be much more valuable than scattered notes because every chapter will build on the previous one.

