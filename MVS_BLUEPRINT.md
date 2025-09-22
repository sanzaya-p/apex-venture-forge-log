# Venture 001: LeadSignal - MVS Blueprint

This document details the Minimum Viable Service (MVS) architecture for LeadSignal.

---

### **1. Value Proposition**

To provide a daily email digest of new Reddit posts/comments containing client-specified keywords from targeted subreddits, saving clients hours of manual search time.

### **2. The 'Free-Stack'**

* **Intake:** `Google Forms` to collect client's email, target keywords, and target subreddits.
* **Monitoring Engine:** A unique `Reddit Search URL` is constructed for each client and converted into an `RSS Feed` using a free online generator.
* **Automation Core:** `Zapier` (Free Tier) watches the client's unique RSS feed for new items.
* **Delivery Mechanism:** A Zapier workflow triggers `Gmail` to send a formatted email alert directly to the client's inbox with the lead details and a direct link.

### **3. The 'Smoke Test' Post (Validation Instrument)**

* **Location:** `r/sales`
* **Title:** Free Tool: I built a script that emails you new leads from Reddit. Who wants to try it?
* **Body:** "Hey everyone, I got tired of manually searching subreddits for people looking for services I offer. I wrote a simple script that monitors keywords (e.g., 'looking for a consultant', 'recommend a tool for X') in specific subreddents and emails me a daily summary. It's saving me hours. Thinking of cleaning it up for others to use. Would anyone be interested in being a free beta tester for a week? Comment 'lead' below if you're interested."

### **4. Fulfillment SOP (Abridged)**

1.  Client submits Google Form.
2.  Construct a unique Reddit Search URL with their keywords/subreddits.
3.  Convert the URL to an RSS Feed URL.
4.  Create a new Zap in Zapier: Trigger is "New Item in Feed" (using the RSS URL), Action is "Send Email" via Gmail.
5.  Map the Zap to send the formatted alert to the client's email.
6.  Activate the Zap. Onboarding complete.
