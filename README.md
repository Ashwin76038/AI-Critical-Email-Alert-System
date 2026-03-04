### AI Critical Email Alert System

**Built with**: [n8n](https://n8n.io/) - Open-source workflow automation platform

**Purpose**: An intelligent email monitoring system built in n8n that automatically analyzes incoming Gmail messages using OpenAI's GPT-4 to classify their importance, detect urgency timelines, and identify potential risks.

**What it does**:
- 🔔 **Monitors Gmail** - Checks for new emails every minute via n8n's Gmail Trigger node
- 🤖 **AI Analysis** - Uses GPT-4 via n8n's OpenAI integration to intelligently classify emails as Important, Normal, or Ignore
- ⏰ **Timeline Detection** - Extracts urgency information (Today, Upcoming, Later, or No deadline)
- ⚠️ **Risk Assessment** - Detects and rates potential risks (High, Medium, Low, None)
- 📧 **Smart Alerts** - Automatically sends alert notifications only for critical/important emails via Gmail

**n8n Workflow Components**:
1. **Gmail Trigger** (n8n) → Polls Gmail every minute for new emails
2. **Edit Fields** (n8n Set node) → Extracts sender, subject, and email body
3. **Message a model** (n8n LangChain OpenAI) → Sends email content to GPT-4 for intelligent analysis
4. **Code in JavaScript** (n8n Code node) → Parses the AI response into structured JSON
5. **If (Conditional)** (n8n If node) → Filters to only process "Important" classified emails
6. **Send a message** (n8n Gmail) → Sends an alert email with analysis summary, risk level, and reasoning

**Features**:
✅ Real-time email monitoring powered by n8n  
✅ AI-powered intelligent classification  
✅ Automated risk detection  
✅ Timeline/deadline extraction  
✅ Smart filtered alerts  
✅ Structured JSON analysis output  
✅ No-code/low-code automation

**Requirements**:
- n8n instance (self-hosted or cloud)
- Gmail account (with OAuth2 authentication enabled)
- OpenAI API key (for GPT-4 access)

**Output Format**:
For each important email, you receive an alert containing:
- **Summary** - Brief email summary
- **Reason** - Why it was classified as Important
- **Risk Level** - High/Medium/Low/None
- **Risk Explanation** - Details about potential risks

**Use Cases**:
- Executives filtering high-priority emails
- IT teams catching security alerts
- Sales teams tracking urgent client communications
- Project managers monitoring deadline notifications
- Anyone wanting smart email triage with n8n automation
