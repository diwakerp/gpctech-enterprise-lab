# Splunk Integration Through Group Policy

## Overview

The GPCTech Enterprise Lab uses Active Directory Group Policy Objects (GPOs) to automate Splunk Universal Forwarder deployment and configuration.

This simulates enterprise endpoint logging deployment where security agents are centrally managed.

---

# Architecture

```mermaid
flowchart TB

AD["Active Directory<br>dlab.local"]

GPO1["Install Splunk Universal Forwarder GPO"]

GPO2["Splunk Configuration GPO<br>inputs.conf"]

Endpoints["Domain Joined Systems"]

Splunk["Splunk Indexer"]

AD --> GPO1

AD --> GPO2

GPO1 --> Endpoints

GPO2 --> Endpoints

Endpoints --> Splunk
```

---

# Current GPOs

| GPO | Purpose |
|---|---|
| Install Splunk Universal Forwarder | Automated deployment |
| Universal Forwarder Configuration | Deploy inputs.conf configuration |

---

# Deployment Process

```
Domain Computer Starts

        |
        |
Group Policy Refresh

        |
        |
Splunk Universal Forwarder Installed

        |
        |
Configuration Files Applied

        |
        |
Windows Events Forwarded To Splunk
```

---

# Benefits

- Centralised agent deployment
- Consistent endpoint configuration
- Reduced manual installation
- Scalable security monitoring

---

# Future Improvements

Planned:

- Certificate-based Splunk communication
- Deployment of outputs.conf
- Forwarder monitoring
- Sentinel integration
- Automated health checks
