# Honeynet-Risk-Register
# Honeynet Risk Register

A practice cyber risk register I built in Excel, based on the risks from my Azure honeynet lab:
https://github.com/TH33171/Azure-Active-Directory-Lab

## Why I made it
In my honeynet project, I observed incoming attacks via Microsoft Sentinel, then hardened the environment. I wanted to show the GRC side of that lab by 
turning the risks I observed into a register, assigning each one an ID, tracking and scoring them, and assigning each to an owner, just as a GRC security team would. 

## What's in it
- **Risk Register sheet:** The sheet contains 6 risks from the lab, which I rated in terms of likelihood and impact on a scale of 1-5. I also calculated the risk score, assigned their levels, and listed the controls I applied to mitigate them, as well as giving them a status and an owner. 
- **Summary sheet:** Shows a pivot table counting the risks by level.

## How it works
- **Risk Score** = Likelihood x Impact
- **Risk Level** uses an IF formula: 15+ is High, 8-14 is Medium, and below 8 is Low
- Conditional formatting colors each level (red is for High, yellow is for Medium, green is for Low)
- The Status column has a dropdown list of 4 options: Open, In progress, Mitigated, Accepted

## The risks
- Wide open NSGs allow all internet traffic
- Attempted brute-force logins on the Windows VMs
- Attempted brute-force logins on the Linux VM
- VM built-in firewalls are off
- Key Vault is accessible via a public endpoint
- Storage account accessible via a public endpoint

I measured the likelihood scores based off what i observed in the lab. A large number of brute force attacks and malicious traffic were observed prior to hardening. 

## Lesson learned
Measuring risks is often a judgment call that can vary; hence, it's better to base it on actual evidence. This lab also helped me practice my Excel skills, as they are often vital to GRC work, such as pivot tables, conditional formatting, IF functions, formulas, and data validation. 
