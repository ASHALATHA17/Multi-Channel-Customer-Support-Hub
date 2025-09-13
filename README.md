Multi-Channel Customer Support Hub (Omnichannel Support Project)
This project is a Salesforce-based Omnichannel Support System that centralizes customer queries from Email, WhatsApp, Chat, and Social Media into a single platform. It enables automated case creation and assignment, SLA management, sentiment-based prioritization, and real-time dashboards for agents and managers.
The system helps support agents respond faster, managers monitor performance, and customers receive consistent and timely responses, improving overall customer satisfaction and retention.
Phase 1: Problem Understanding & Industry Analysis
1. Requirement Gathering
•	Objective: Enable companies to manage customer queries from multiple channels (Email, WhatsApp, Chat, Social Media) in one Salesforce platform.
•	Gathered Requirements:
o	Unified Inbox → Central place where all customer queries arrive.
o	Case Management → Auto-create and assign Cases from incoming queries.
o	Omnichannel Routing → Distribute cases to available agents based on skills, priority, or workload.
o	SLAs & Escalations → Ensure timely resolution with automated reminders.
o	Sentiment Analysis → Flag negative/urgent cases automatically.
o	Reports & Dashboards → Track resolution times, agent productivity, and channel effectiveness.
2. Stakeholder Analysis
•	Primary Stakeholders:
o	Support Agents → Need an easy-to-use interface to respond to queries from multiple channels.
o	Customers → Expect quick and consistent responses, regardless of channel.
o	Support Managers → Need visibility into KPIs (first response time, resolution time, customer satisfaction).
o	IT/Admin Team → Responsible for Salesforce setup, integration with channels (WhatsApp, Chatbot, Social), and security.
3. Business Process Mapping
•	Current Process (Without Salesforce):
o	Customers reach out via Email, WhatsApp, or Social Media.
o	Agents handle them separately → responses delayed, duplicate handling possible.
o	Escalations missed due to lack of tracking.
o	Managers cannot measure customer satisfaction properly.
•	Proposed Salesforce Process:
o	All incoming queries auto-converted into Cases in Salesforce.
o	Omnichannel Routing assigns Cases based on priority and availability.
o	Agents reply from Salesforce → response is sent back via the original channel (Email, WhatsApp, Chat).
o	SLAs applied → if not resolved in time, the case escalates.
o	LWC Unified Inbox for agents → one screen to view/respond across channels.
o	Dashboards → show total cases, resolution time, customer sentiment breakdown.
4. Industry-Specific Use Case Analysis (Customer Support)
•	Omnichannel Support is critical for BPOs, Call Centers, D2C Brands, and E-commerce firms.
•	Customer Retention depends heavily on fast & personalized responses.
•	Multi-channel engagement reduces the risk of customers being ignored.
•	Sentiment-driven escalation improves customer satisfaction scores (CSAT).
Example:
Without Salesforce → A customer sends a WhatsApp query and waits 2 days for a response.
With Salesforce → Case auto-created, routed to available agent, and SLA ensures a 1-hour response time.
5. AppExchange Exploration
•	Useful Salesforce Apps for Multi-Channel Support:
o	Digital Engagement Add-on → Natively supports WhatsApp, Facebook Messenger, SMS, and Web Chat.
o	Einstein Bots → Automates FAQs and routes complex queries to human agents.
o	Twilio/SMS Magic → For WhatsApp & SMS integration.
o	Vonage/Genesys Cloud → Voice channel integration.
o	SurveyMonkey or Salesforce Surveys → Collect post-resolution feedback.
Phase 2: Org Setup & Configuration
1. Salesforce Editions
•	Action: Use Salesforce Developer Edition with Service Cloud + Digital Engagement Add-on.
•	Outcome: Provides core Service Cloud features (Case Management, Omni-Channel) and access to WhatsApp, Chat, and Social integrations.
2. Company Profile Setup
•	Action: Configure company information → support email address, default currency, timezone = IST, fiscal start = April.
•	Outcome: Ensures all customer interactions (cases, SLAs, reports) are tracked in the right business context.
3. Business Hours & Holidays
•	Action: Define business hours (Mon–Sat, 9 AM–6 PM) and add holidays (e.g., national holidays, weekends).
•	Outcome: Case escalation timers (SLAs) respect working hours and avoid firing during holidays.
4. Fiscal Year Settings
•	Action: Enable custom fiscal year (April–March).
•	Outcome: Reports and dashboards align with company’s real reporting cycle.
5. User Setup & Licenses
•	Action: Create users for different roles:
o	Support Agent (Service Cloud license) → Handles incoming queries.
o	Support Manager (Service Cloud + Reporting access) → Monitors cases and dashboards.
o	Integration User (API-enabled) → Connects WhatsApp, Chatbot, Social Media.
o	Admin/Developer → Manages configuration and custom development.
•	Outcome: Proper licensing ensures every stakeholder has the right tools.
6. Profiles
•	Action:
o	Create Agent Profile → Access to Cases, Knowledge, but restricted to their records.
o	Create Manager Profile → Full visibility on Cases, Reports, Dashboards.
•	Outcome: Agents focus on resolving cases; managers get oversight without needing Admin access.
7. Roles
•	Action: Define hierarchy:
o	Agent → Team Lead → Support Manager → Admin.
•	Outcome: Case visibility flows upward → managers automatically see their team’s cases.
8. Permission Sets
•	Action:
o	“Sentiment Dashboard Access” → Assigned to managers.
o	“Integration Access” → Assigned to developers handling WhatsApp/Chatbot setup.
•	Outcome: Flexible security → extra access given without modifying base profiles.
9. Org-Wide Defaults (OWD)
•	Action:
o	Cases = Private → Only owner/assigned agent can see.
o	Knowledge Articles = Public Read Only → All agents can access solutions.
•	Outcome: Data confidentiality maintained, but knowledge base remains shareable.
10. Sharing Rules
•	Action:
o	Auto-share High Priority Cases with Support Managers.
o	Share WhatsApp Cases with Social Media team.
•	Outcome: Critical cases are escalated automatically to the right people.
11. Login Access Policies
•	Action:
o	Restrict login by IP Range (e.g., company office IPs only).
o	Set session timeout = 30 minutes idle.
•	Outcome: Increases data security and prevents unauthorized access.
12. Developer Org Setup
•	Action: Register for a Salesforce Developer Org (free).
o	Install required packages (Twilio, Digital Engagement, Einstein Bots).
o	Enable Developer Hub & Scratch Orgs.
•	Outcome: Ready-to-use environment for building and testing integrations.
13. Sandbox Usage
•	Action:
o	Developer Sandbox → For coding LWCs, Apex triggers.
o	Partial Copy Sandbox → For testing with sample customer data.
•	Outcome: Clear separation of development and testing ensures stable deployment.
14. Deployment Basics
•	Action:
o	Use Change Sets (for Admin configs) → Profiles, OWD, Workflows.
o	Use SFDX CLI + VS Code (for Developer work) → LWCs, Apex classes.
•	Outcome: Structured deployment process → reduces errors when moving to Production or Demo Org.
