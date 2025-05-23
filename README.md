# Cyber-Junky - Your Threat Hunting Arsenal

Welcome to the Cyber-Junky GitHub repository! Here, you'll find a collection of Microsoft KQL (Kusto Query Language) queries designed for proactive threat hunting within Microsoft Defender for Endpoint and Microsoft Sentinel, along with helpful PowerShell scripts to streamline your investigations.

## What You'll Find Here:

This repository is organized into two main directories:

* **KQL-Queries:** This directory contains a growing library of KQL queries focused on identifying suspicious activities, detecting potential intrusions, and uncovering advanced threats within your Microsoft security ecosystem. These queries are crafted to be efficient, well-commented, and easily adaptable to your specific environment. Expect to find queries covering various tactics and techniques, including:
    * **Lateral Movement Detection:** Identifying unusual network connections and suspicious account activity indicative of attackers moving through your network.
    * **Persistence Mechanisms:** Spotting methods adversaries use to maintain long-term access to compromised systems.
    * **Exploitation Attempts:** Looking for evidence of attempts to leverage vulnerabilities in your environment.
    * **Command and Control (C2) Activity:** Identifying communication patterns with known or suspicious external infrastructure.
    * **Data Exfiltration Indicators:** Detecting unusual data transfers that might signal a breach.
    * **Insider Threat Detection:** Identifying anomalous user behavior that could indicate malicious intent.

* **PowerShell-Scripts:** This directory houses PowerShell scripts developed to assist with various aspects of threat hunting. These scripts aim to automate repetitive tasks, enrich investigation data, and provide quick insights. Examples of scripts you might find include:
    * Scripts to query and analyze endpoint data.
    * Tools to enrich indicators of compromise (IOCs).
    * Scripts to automate the collection of forensic artifacts.
    * Utilities to interact with Microsoft Defender and Sentinel APIs.

## How to Use This Repository:

Feel free to browse the directories and explore the individual KQL query (`.kql`) and PowerShell script (`.ps1`) files. Each item will typically include comments explaining its purpose, how it works, and any specific requirements or considerations.

* **KQL Queries:** You can copy and paste these queries directly into the Microsoft Defender for Endpoint advanced hunting interface or the Microsoft Sentinel Log Analytics workspace. Remember to review and adapt the queries to your specific environment and data schema.
* **PowerShell Scripts:** Download
