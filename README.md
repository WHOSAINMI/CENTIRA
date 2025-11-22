
## CENTIRA
### LLM-Assisted Cyber Threat Intelligence Aggregation and Correlation
### Sponsored and Provided by NCA-SITE @ KAUST Academy

# Developed by
-  Meshal Alqahtani
-  Ridha Albushafia
-  Hussain AlShdaied
-  Omar Barasheed

# Project Overview
 
A Threat Intelligence platform that aggregates and correlates Indicators of Compromise (IOCs) from multiple sources into a unified, centralized dashboard. It provides real-time analysis and features an LLM-assisted relevance scoring system based on the user's threat model.

# Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/WHOSAINMI/TIAA-PROJECT.git
```

### 2. In CMD Navigate to the Project Directory
```bash
cd TIAA-PROJECT 
```

### 3. Install Docker/Docker Desktop
```bash
docker -v
```

### 4. Build the Docker Image and run
```bash
docker compose up --build
```

### 5. Access the Application
```bash
http://localhost:3000/
```

# Features
- Real-time aggregation of Indicators of Compromise (IOCs) from multiple threat intelligence feeds (Threatfox, Tweetfeed, MISP CIRCL, Alienvault OTX, VirusTotal, Malware Bazaar, URLhaus)
- Real-time analysis of aggregated IOCs and current trends through clear visualizations
- Correlation of IOCs across all feeds for deeper insights
- User-friendly, easy-to-navigate dashboard
- User profile creation for setting up a personalized threat model
- Login using username and access code
- Ability to edit user profile and update threat model
- Option to delete user profile
- LLM-assisted IOC relevance scoring based on the user's threat model (Limited to Correlated IOCs only)
- Guest login option (limited access without correlated or LLM-scored IOCs)
- Toggle option to switch visuals and analysis between data for "Today" and the "Past 3 Days"
- View detailed IOC information aggregated from all correlated sources
- Filtering options to reduce noise in the IOC feed
- Option to sort the IOC feed by oldest to newest
- Ability to export individual IOCs
- Search capabilities by IOC value or tags
- JSON STIX 2.1 and CSV Export options for manual SIEM/EDR integration

# Platform Walkthrough


### Landing Page
When accessing the platform, you'll have three access options:

- **Login** - For existing users with username and access code
- **Create Profile** - New users 
- **Continue as Guest** - Limited access for platform

### Access Levels

**Registered Users** get full access:
- Complete dashboard analytics with time toggle (Today/Past 3 Days)
- Live IOC feed with advanced filtering and search
- **Correlated Feed** - Cross-source IOC analysis
- **LLM Relevancy Scoring** - Personalized threat scoring based on your threat model
- Profile management (edit/delete profile options)
- Export functionality (CSV/JSON STIX 2.1) for any IOC
- Detailed IOC analysis with multi-source correlation

**Guest Users** have limited access to:
- Complete dashboard analytics with time toggle (Today/Past 3 Days)
- Live IOC feed with advanced filtering and search
- Export functionality (CSV/JSON STIX 2.1)
- Detailed IOC analysis only for live feed
- **No access to correlated IOCs or LLM scoring**

>  **Why Create a Profile?** During profile creation, we collect information about your threat model and organizational context. This enables our LLM to provide personalized relevancy scores for correlated indicators that matter most to your environment.
>>  ***Note:*** - you can use these login credentials for testing. test:KDeeaq

## Main Dashboard

**Analytics Overview**

The dashboard provides comprehensive threat intelligence visualizations with a **time toggle feature** to switch between:
- **Today** - Current day trend analysis
- **Past 3 Days** - Extended view for trend analysis

**Key Visualization Panels:**
- **Attack Type Analysis** - Pie chart breakdown of top 4 threat categories
- **IOC Type Breakdown** - Distribution of indicator types (IPs, Domains, Hashes)
- **Sources Breakdown** - Intelligence feed contributions (Threatfox, Tweetfeed, MISP CIRCL, Alienvault OTX)
- **IP Geolocation Distribution** - Lists highest 10 countries that appeared as an IOC source
- **IOC Feed** - Shows recently added IOCs

## Navigate to Feed Details
Real-time stream of threat indicators ***(Fetches new IoCs hourly)*** featuring:

**Advanced Capabilities:**
- **Search Functionality** - Find IOCs by value or keyword - tag or in description -
- **Filtering Options** - Filter by IOC type or source
- **Sorting Option** - Sort by newest/oldest
- **Individual Export** - Export specific IOCs of interest in JSON STIX fromat

**Export Options:**

- **Export Today's IOCs**
- **Export All IOCs from the past 3 Days**
- **Export Current View (Currently Applied Filters)**
- **Export Correlated IOCs only (For Registered Users)**

Supported file types:
- **CSV Export** - Spreadsheet-compatible format for analysis
- **JSON STIX 2.1 Export** - Industry-standard structured threat information

## IOC Details View

Click any indicator to access comprehensive intelligence:

### IOC Information
- **Value** - The actual indicator
- **Type** - Specific types (md5_hash, sha1_hash, sha256_hash, ip, domain)
- **Time stamps** - Created, Modified, Valid from and Last Seen timestamps
- **Confidence Assessment** - Multi-source reliability scoring
- **Country** - Source country of the IOC (IPs)
- **Labels & Tags** - Labels and Tags for the IOC 
- **Description** - Description of the IOC, which can contain some critical information
- **Refrences & Sources** - The feeds, sources and reporter


## Advanced Features (Registered Users Only)

### Correlation/Enrichment Engine 
Correlate IOCs from multiple sources and then enrich them from other trusted sources for more reliability:

- **Multi-Source Validation** - IOCs confirmed by 2+ independent intelligence feeds
- **Cross-Feed Analysis** - Unified view of distributed IOCs

### LLM-Assisted Relevancy Scoring
Personalized threat assessment powered by TinyLlama-1.1B:

**Threat Model Integration:**
- Industry-specific risk weighting
- Geographic risk consideration
- Technology stack relevance assessment

**Intelligent Scoring:**
- Assigns a relevancy score based on the given threat model profile

### Profile Management
Complete user profile control:
- **Edit Profile** - Update threat model and organizational context
- **Delete Profile** - Remove account and associated data


## Data Sources and Integration

### Intelligence Feeds
CENTIRA works with 7 threat intelligence sources:
- **Threatfox** - (Full Ingestion)
- **Tweetfeed** - (Full Ingestion)
- **MISP CIRCL** - (Full Ingestion)
- **Alienvault OTX** - (Full Ingestion)
- **VirusTotal** - (Enrichment feed)
- **Malware Bazaar** - (Enrichment feed)
- **URLhaus** - (Enrichment feed)

### Integration
**Supported formats for manual SIEM/EDR integration:**
- **CSV** - Human-readable, spreadsheet compatible
- **JSON STIX 2.1** - industry standard


## Maximizing Platform Value

### Best Practices:
1. **Create a Comprehensive Profile** - Enable accurate LLM relevancy scoring
2. **Leverage Search & Filters** - Reduce noise and focus on relevant threats
3. **Regular Profile Updates** - Maintain threat model accuracy as landscape evolves
4. **Export Strategically** - Use STIX 2.1 for automation, CSV for analysis

### Pro Tips:
- Monitor source breakdown to identify intelligence volume gaps
- Search by keywords
- Export individual high-relevance IOCs for immediate action
- Regularly review and update your threat model for optimal LLM scoring
- Regularly export Relevant/Important IOCs as the platform only stores them for 3 days

---
