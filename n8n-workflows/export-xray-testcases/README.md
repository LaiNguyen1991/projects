# ⚡ Jira Xray Test Case Exporter Workflow (n8n Webhook Form)

An advanced, automated utility workflow created in **n8n** that provides an interactive Web-UI Form to dynamically query, paginate, sanitize, and export Jira Xray Test Cases directly into structured Excel (`.xlsx`) spreadsheets.

---

## 🚀 Key Features

* **Interactive Form UI:** Triggered via a native n8n Webhook form—allowing users to dynamically input any target **Project ID** and **Xray Folder Path** at runtime without editing code blocks.
* **Auto-Authentication:** Securely manages REST authentications to trade client credentials for short-lived Bearer tokens.
* **Smart Pagination Loop:** Automatically cycles batches of 100 test cases recursively using Graph GL to handle large-scale datasets safely.
* **Relational Key Resolution:** Identifies nested `callTestIssueId` (Pre-conditions), fetches them in bulk, and dynamically maps them to their respective Jira keys.
* **Jira Markup Regex Cleansing:** Automatically strips messy syntax tokens (`{color}`, `{code}`, formatting blocks) to produce production-grade clean Excel rows.

---


## 🛠️ How To Use

### 1. Import to n8n
1. Download the `Export_Xray_Test_Cases.json` file from this repository.
2. Inside your n8n instance $\rightarrow$ Create a blank workflow $\rightarrow$ Top-right menu $\rightarrow$ Select **Import from File**.

### 2. Secure Configuration
Before running, you need to set up your credentials once:
1. Open the **`Get Xray Authenticate`** node.
2. Replace `YOUR_CLIENT_ID_HERE` and `YOUR_CLIENT_SECRET_HERE` with your actual Jira Xray API v2 Cloud credentials.

### 3. Execution via Web Form
1. Copy the **Test URL** or **Production URL** generated inside the **`Input Form`** node.
2. Open that URL in your web browser. 
3. Fill in your **Project ID** and **Xray Folder Path** in the UI form, then click **Submit**.
4. Once completed, open the **`Export .xlsx`** node in n8n to instantly fetch your download link!
