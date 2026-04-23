# CMMC Level 2 Implementation Guide for MSPs

## Client Information
- **Client Name:** [TO BE FILLED]
- **Industry:** [Defense Contractor / Manufacturing / etc.]
- **Current CMMC Level:** Level 1 (Foundational)
- **Target Level:** Level 2 (Advanced)
- **CUI Types:** [Technical Data / Specifications / etc.]
- **Assessment Timeline:** [Target Date]

---

## Phase 1: Assessment & Planning (Week 1-2)

### 1.1 Initial Discovery

**Network Infrastructure Audit:**
- [ ] Document all network devices (routers, switches, firewalls)
- [ ] Map network topology and VLANs
- [ ] Identify all systems processing/storing CUI
- [ ] Document remote access methods (VPN, RDP, etc.)
- [ ] List all cloud services and SaaS applications
- [ ] Inventory all endpoints (workstations, laptops, mobile devices)
- [ ] Document wireless networks and access points

**Current Security Posture:**
- [ ] Review existing security policies
- [ ] Check current backup procedures
- [ ] Audit user accounts and permissions
- [ ] Review antivirus/EDR deployment
- [ ] Check patch management status
- [ ] Review logging capabilities
- [ ] Document incident response procedures

### 1.2 Gap Analysis

**Critical Gaps to Address:**
1. **Access Control (AC)** - 22 controls
   - Missing: Formal access control policy
   - Missing: Least privilege enforcement
   - Missing: Separation of duties
   - Missing: Account management procedures

2. **Audit & Accountability (AU)** - 14 controls
   - Missing: Centralized logging
   - Missing: Audit log review procedures
   - Missing: Log retention (1 year minimum)
   - Missing: Time synchronization

3. **Configuration Management (CM)** - 10 controls
   - Missing: Baseline configurations
   - Missing: Change control process
   - Missing: Least functionality (disable unused ports/services)

4. **Identification & Authentication (IA)** - 11 controls
   - Missing: MFA for all accounts
   - Missing: Password complexity requirements
   - Missing: Account lockout policies

5. **Incident Response (IR)** - 8 controls
   - Missing: Formal incident response plan
   - Missing: Incident reporting procedures
   - Missing: Testing/training

6. **Risk Assessment (RA)** - 5 controls
   - Missing: Vulnerability scanning
   - Missing: Risk assessment documentation

7. **System & Communications Protection (SC)** - 16 controls
   - Missing: Firewall rules documentation
   - Missing: Encryption for CUI at rest/transit
   - Missing: Port/protocol/service restrictions

8. **System & Information Integrity (SI)** - 10 controls
   - Missing: Patch management process
   - Missing: Malicious code protection
   - Missing: System monitoring

---

## Phase 2: Policy Development (Week 2-3)

### 2.1 Required Policies

**Must Create:**
1. System Security Plan (SSP) - **CRITICAL**
2. Access Control Policy
3. Audit & Accountability Policy
4. Configuration Management Plan
5. Contingency Plan (Backup/Recovery)
6. Incident Response Plan
7. Maintenance Policy
8. Media Protection Policy
9. Physical Protection Policy
10. Personnel Security Policy
11. Risk Assessment Policy
12. Security Awareness Training Policy
13. System & Communications Protection Policy

### 2.2 Policy Template Structure

Each policy must include:
- Purpose and scope
- Roles and responsibilities
- Procedures and requirements
- Enforcement
- Review schedule (annual minimum)
- Approval signatures

---

## Phase 3: Technical Implementation (Week 3-8)

### 3.1 Access Control (AC) Implementation

**AC-1: Access Control Policy**
- [ ] Draft policy document
- [ ] Define approval workflow
- [ ] Document review schedule

**AC-2: Account Management**
- [ ] Implement formal account creation process
- [ ] Create account modification procedures
- [ ] Document account removal/termination process
- [ ] Establish periodic access reviews (quarterly)

**AC-3: Access Enforcement**
- [ ] Configure ACLs on all systems
- [ ] Implement role-based access control (RBAC)
- [ ] Document access control matrix

**AC-6: Least Privilege**
- [ ] Audit all user permissions
- [ ] Remove unnecessary privileges
- [ ] Implement privileged access management (PAM)
- [ ] Create standard user profiles

**AC-7: Unsuccessful Logon Attempts**
- [ ] Configure account lockout (5 attempts, 30 min lockout)
- [ ] Enable failed login monitoring
- [ ] Set automatic unlock or admin unlock

**AC-11: Session Lock**
- [ ] Configure screen lock (15 minutes inactivity)
- [ ] Require password to unlock
- [ ] Apply to all systems

**AC-17: Remote Access**
- [ ] Document authorized remote access methods
- [ ] Implement VPN with MFA
- [ ] Disable direct RDP from internet
- [ ] Monitor remote access sessions

**AC-18: Wireless Access**
- [ ] Implement WPA2-Enterprise or WPA3
- [ ] Use certificate-based authentication
- [ ] Separate guest and corporate networks
- [ ] Document wireless security settings

### 3.2 Audit & Accountability (AU) Implementation

**AU-1: Audit Policy**
- [ ] Define auditable events
- [ ] Document audit procedures
- [ ] Assign audit review responsibilities

**AU-2: Audit Events**
- [ ] Enable logging on all systems:
  - Logon/logoff events
  - File access (CUI)
  - Administrative actions
  - Account changes
  - Policy changes

**AU-3: Audit Content**
- [ ] Ensure logs include:
  - User ID
  - Event type
  - Date/time
  - Success/failure
  - Origin

**AU-6: Audit Review**
- [ ] Implement automated log review
- [ ] Schedule weekly manual reviews
- [ ] Document review findings
- [ ] Create escalation procedures

**AU-9: Audit Protection**
- [ ] Restrict log access to authorized personnel
- [ ] Implement write-once storage
- [ ] Backup logs to secure location
- [ ] Protect log integrity

**AU-11: Audit Retention**
- [ ] Configure 1-year minimum retention
- [ ] Document retention schedule
- [ ] Ensure backup logs retained

### 3.3 Configuration Management (CM)

**CM-2: Baseline Configurations**
- [ ] Create gold images for:
  - Workstations
  - Servers
  - Network devices
- [ ] Document baseline settings
- [ ] Implement change tracking

**CM-3: Configuration Change Control**
- [ ] Implement change request process
- [ ] Require approval for changes
- [ ] Document all changes
- [ ] Test changes before production

**CM-6: Configuration Settings**
- [ ] Implement security baselines:
  - CIS Benchmarks
  - STIGs (if applicable)
- [ ] Enforce via Group Policy / MDM
- [ ] Regular compliance scans

**CM-7: Least Functionality**
- [ ] Disable unnecessary:
  - Ports
  - Protocols
  - Services
  - Applications
- [ ] Document required services
- [ ] Implement software restriction policies

### 3.4 Identification & Authentication (IA)

**IA-2: Identification & Authentication**
- [ ] Implement unique user IDs
- [ ] Require authentication for all access
- [ ] Disable shared accounts

**IA-2(1): MFA for Network Access**
- [ ] Deploy MFA solution (Microsoft Authenticator, Duo, etc.)
- [ ] Enforce for all remote access
- [ ] Enforce for privileged accounts

**IA-2(2): MFA for Local Access**
- [ ] Enforce MFA for privileged local access
- [ ] Document exceptions (if any)

**IA-5: Authenticator Management**
- [ ] Implement password policy:
  - Minimum 14 characters
  - Complexity required
  - 90-day maximum age
  - History of 24 passwords
- [ ] Deploy password manager
- [ ] Implement MFA for all accounts

### 3.5 Incident Response (IR)

**IR-1: Incident Response Policy**
- [ ] Document incident types
- [ ] Define response procedures
- [ ] Assign roles and responsibilities
- [ ] Establish reporting chain

**IR-2: Incident Response Team**
- [ ] Designate incident manager
- [ ] Assign technical responders
- [ ] Document contact information
- [ ] Establish escalation procedures

**IR-4: Incident Handling**
- [ ] Create incident handling checklist
- [ ] Document containment procedures
- [ ] Establish evidence preservation
- [ ] Create communication templates

**IR-5: Incident Monitoring**
- [ ] Implement SIEM or monitoring
- [ ] Configure alert thresholds
- [ ] Establish 24/7 monitoring (or MSP coverage)

### 3.6 Risk Assessment (RA)

**RA-3: Risk Assessment**
- [ ] Conduct formal risk assessment
- [ ] Identify threats and vulnerabilities
- [ ] Assess likelihood and impact
- [ ] Document risk acceptance
- [ ] Schedule annual updates

**RA-5: Vulnerability Scanning**
- [ ] Implement vulnerability scanner
- [ ] Schedule monthly scans
- [ ] Document remediation
- [ ] Track to closure

### 3.7 System & Communications Protection (SC)

**SC-7: Boundary Protection**
- [ ] Document firewall rules
- [ ] Implement deny-by-default
- [ ] Review rules quarterly
- [ ] Log all denied traffic

**SC-8: Transmission Confidentiality**
- [ ] Implement TLS 1.2+ for all connections
- [ ] Use VPN for remote access
- [ ] Encrypt email containing CUI

**SC-28: Protection at Rest**
- [ ] Enable BitLocker on all devices
- [ ] Encrypt servers (VM or physical)
- [ ] Encrypt backup media
- [ ] Manage encryption keys

**SC-12: Cryptographic Key Management**
- [ ] Document key generation
- [ ] Implement secure storage
- [ ] Define key rotation schedule
- [ ] Document destruction procedures

### 3.8 System & Information Integrity (SI)

**SI-2: Flaw Remediation**
- [ ] Implement patch management:
  - Critical patches: 72 hours
  - High patches: 7 days
  - Medium/Low: 30 days
- [ ] Document exceptions
- [ ] Track patch compliance

**SI-3: Malicious Code Protection**
- [ ] Deploy EDR solution (CrowdStrike, SentinelOne, etc.)
- [ ] Enable real-time scanning
- [ ] Schedule full scans weekly
- [ ] Update definitions daily

**SI-4: System Monitoring**
- [ ] Deploy SIEM or monitoring
- [ ] Monitor for anomalies
- [ ] Configure alerting
- [ ] Document response procedures

---

## Phase 4: Documentation & Evidence (Week 8-10)

### 4.1 Required Documentation

**System Security Plan (SSP):**
- [ ] System boundary
- [ ] Environment description
- [ ] CUI data flows
- [ ] Control implementation details
- [ ] Responsible parties

**Evidence Package:**
- [ ] Screenshots of configurations
- [ ] Policy documents (signed)
- [ ] Training records
- [ ] Audit logs (samples)
- [ ] Scan results
- [ ] Incident reports (if any)

### 4.2 Evidence Collection

**Per Control:**
- Policy reference
- Procedure document
- Implementation screenshot
- Test results
- Review records

---

## Phase 5: Assessment Preparation (Week 10-12)

### 5.1 Pre-Assessment Checklist

**30 Days Before:**
- [ ] Complete all control implementations
- [ ] Finalize documentation
- [ ] Conduct internal audit
- [ ] Remediate any findings

**14 Days Before:**
- [ ] Organize evidence
- [ ] Prepare personnel interviews
- [ ] Test systems
- [ ] Brief leadership

**7 Days Before:**
- [ ] Final walkthrough
- [ ] Confirm assessor requirements
- [ ] Prepare conference room
- [ ] Notify key personnel

### 5.2 Assessment Day

**Day 1-2: Document Review**
- Provide evidence package
- Answer questions
- Clarify implementations

**Day 3-4: System Testing**
- Demonstrate controls
- Provide screenshots
- Show configurations

**Day 5: Interviews**
- Personnel interviews
- Process demonstrations
- Final questions

---

## Ongoing Maintenance

### Monthly Tasks
- [ ] Review audit logs
- [ ] Check patch compliance
- [ ] Verify backup success
- [ ] Review access permissions

### Quarterly Tasks
- [ ] Conduct vulnerability scans
- [ ] Review and update policies
- [ ] Test incident response
- [ ] Conduct access reviews
- [ ] Review firewall rules

### Annual Tasks
- [ ] Full risk assessment
- [ ] Security awareness training
- [ ] Policy review and approval
- [ ] Disaster recovery test
- [ ] Penetration test

---

## MSP Tools & Automation

### Recommended Tools
| Function | Tool Options |
|----------|--------------|
| RMM/PSA | ConnectWise, Datto RMM, Kaseya |
| Documentation | IT Glue, Hudu, Liongard |
| EDR | CrowdStrike, SentinelOne, Huntress |
| SIEM | Splunk, Sentinel, Graylog |
| Vulnerability Scan | Nessus, Qualys, Rapid7 |
| MFA | Duo, Microsoft Authenticator, Okta |
| Backup | Veeam, Datto, Unitrends |
| PAM | CyberArk, Delinea, BeyondTrust |

### Automation Opportunities
- [ ] Automated patch deployment
- [ ] Automated compliance scanning
- [ ] Automated log collection
- [ ] Automated alerting
- [ ] Automated reporting

---

## Cost Estimate

| Category | Estimated Cost |
|----------|----------------|
| Assessment (C3PAO) | $15,000 - $50,000 |
| Security Tools | $10,000 - $30,000/year |
| MSP Implementation | $15,000 - $40,000 |
| Ongoing MSP Management | $2,000 - $5,000/month |
| Training | $2,000 - $5,000 |
| **Total Year 1** | **$60,000 - $150,000** |

---

## Timeline Summary

| Phase | Duration | Key Deliverables |
|-------|----------|------------------|
| Assessment & Planning | 2 weeks | Gap analysis, project plan |
| Policy Development | 1 week | 13 policies, SSP |
| Technical Implementation | 5 weeks | All 110 controls |
| Documentation | 2 weeks | Evidence package |
| Assessment Prep | 2 weeks | Ready for C3PAO |
| **Total** | **12 weeks** | **CMMC Level 2 Ready** |

---

## Next Steps

1. **Schedule kickoff meeting** with client
2. **Assign roles** (your team + client contacts)
3. **Begin discovery** (network scan, inventory)
4. **Prioritize critical controls** (AC, IA, SC)
5. **Start policy development** in parallel

**Need help with any specific control or phase?**