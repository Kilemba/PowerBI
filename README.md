# PowerBI
Step-by-step Markdown guide (with screenshots) on connecting Power BI to a database, accessing and transforming data, exporting reports, and submitting files as PPT or PDF via email directly from Power BI. Perfect for beginners learning reporting and dashboard delivery workflows.
# Power BI: Complete Guide to Database Connections, File Sharing & Report Delivery

> A practical walkthrough for connecting to databases, exporting files, and sending reports via email — all from Microsoft Power BI.


## 1. Accessing Data from a Database

Power BI supports connections to a wide range of database types including **SQL Server**, **MySQL**, **PostgreSQL**, **Oracle**, **Azure SQL**, and more.

---

### Step 1: Open Power BI Desktop

Launch **Power BI Desktop** from your applications. You will land on the start screen or an existing report canvas.

>  Don't have Power BI Desktop? Download it free from [PowerBI Dashboard](https://github.com/Kilemba/PowerBI/blob/main/image.png).

---

### Step 2: Click "Get Data"

On the **Home** ribbon at the top, click the **Get Data** button (or the dropdown arrow next to it for a quick list of sources).

![Power BI Get Data ribbon button showing data source options](../Database connection.png)

> The **Get Data** menu is your gateway to all data sources — local files, cloud services, and databases.

---

### Step 3: Choose Your Database Type

A dialog will appear showing all available data source categories. Click **Database** in the left panel, then select your database type from the list:

| Database Type | Use Case |
|---|---|
| **SQL Server** | Microsoft SQL Server (on-premise or cloud) |
| **MySQL** | Open-source relational DB |
| **PostgreSQL** | Advanced open-source DB |
| **Oracle** | Enterprise Oracle databases |
| **Azure SQL Database** | Microsoft cloud-hosted SQL |

![Power BI data source selection dialog showing database options](https://github.com/Kilemba/PowerBI/blob/main/assets/Database%20connection.png)

Click **Connect** after selecting your database type.

---

### Step 4: Enter Connection Details

A connection dialog will appear. Fill in the required fields:

- **Server** — The server hostname or IP address (e.g., `myserver.database.windows.net`)
- **Database** — The name of the specific database you want to connect to (optional — Power BI will list all databases if left blank)
- **Data Connectivity Mode** — Choose one:
  - `Import` — Loads data into Power BI (faster performance, offline capable)
  - `DirectQuery` — Queries the live database every time (always fresh, no data stored locally)

![Power BI SQL Server connection dialog with server and database fields](https://github.com/Kilemba/PowerBI/blob/main/assets/Aunthentication.png)

>  For large datasets, **DirectQuery** is recommended to avoid memory limits. For smaller datasets, **Import** gives better performance.

Click **OK** to proceed.

---

### Step 5: Authenticate

Power BI will prompt you to authenticate with the database. Choose the appropriate method:

- **Windows** — Use your Windows/Active Directory credentials (common for corporate SQL Server)
- **Database** — Enter a username and password directly
- **Microsoft Account** — For Azure cloud databases

Enter your credentials and click **Connect**.

---

### Step 6: Select Tables & Load Data

The **Navigator** window will appear, showing all available tables and views in the database. 

1. **Browse** the list on the left and check the boxes next to the tables you need
2. **Preview** the data on the right before loading
3. Click **Load** to import the data directly, or **Transform Data** to open the Power Query Editor for data cleaning first

![Power BI Navigator window showing database tables with preview pane](screenshot_navigator)

>  Use **Transform Data** if you need to filter rows, rename columns, merge tables, or change data types before loading.

Once loaded, your tables will appear in the **Fields** pane on the right side of Power BI Desktop, ready for building visualizations.

---

## 2. Exporting & Sharing Files from Power BI

Once you've built your report, Power BI offers several ways to export and share it.

---

### Option A: Export as PDF

Exporting to PDF creates a static, print-ready document of your report — ideal for sharing with stakeholders who don't use Power BI.

**Steps (Power BI Desktop):**

1. Go to **File** → **Export** → **Export to PDF**
2. Power BI will render each page of your report as a PDF page
3. A **Save As** dialog will appear — choose your destination folder and click **Save**

**Steps (Power BI Service — browser):**

1. Open your published report in [app.powerbi.com](https://app.powerbi.com)
2. Click the **Export** button in the top toolbar
3. Select **PDF**
4. Choose whether to export the **current page** or **all pages**
5. Click **Export** and the file will download automatically

![Power BI export to PDF option showing export menu and page selection](screenshot_export_pdf)

>  **Note:** Visuals are rendered at the current filter/slicer state when you export. Adjust filters before exporting to get the exact view you need.

---

### Option B: Export as PowerPoint (PPTX)

Power BI can export each report page as a **PowerPoint slide**, making it easy to embed live report visuals into presentations.

**Steps (Power BI Service):**

1. Open your report at [app.powerbi.com](https://app.powerbi.com)
2. Click the **Export** button in the top menu bar
3. Select **PowerPoint**
4. Choose between:
   - **Current values** — exports the report as static images of the current state
   - **Default values** — exports with default filter states
5. Click **Export** — a `.pptx` file will download

![Power BI export to PowerPoint showing slide output of report pages](screenshot_export_ppt)

>  Each report page becomes one PowerPoint slide. Visuals are embedded as high-resolution images.

**Steps (Power BI Desktop):**

1. Go to **File** → **Export** → **Export to PowerPoint**
2. The report will be rendered and saved as a `.pptx` file

---

### Option C: Publish to Power BI Service

Publishing makes your report available online where team members can view it in a browser with live, interactive data.

**Steps:**

1. In **Power BI Desktop**, click **Publish** in the Home ribbon
2. Sign in to your Microsoft/Power BI account if prompted
3. Select a **Workspace** to publish to (e.g., "My Workspace" or a shared team workspace)
4. Click **Select** — Power BI will upload the report and dataset

![Power BI publish to service showing workspace selection dialog](screenshot_publish)

5. Once complete, click the link in the success dialog to open the report in your browser

> Your report is now live at `app.powerbi.com` and can be shared with a link, embedded in SharePoint, or used to set up email subscriptions.

---

## 3. Sending Reports via Email (PDF/PPT)

Power BI offers both **automated scheduled email delivery** and **manual export + send** options.

---

### Method 1: Email Subscriptions (Power BI Service)

Subscriptions let you (and others) receive **automatic email snapshots** of a report on a schedule — daily, weekly, or monthly.

**Steps:**

1. Open your published report in [app.powerbi.com](https://app.powerbi.com)
2. Click the **Subscribe** icon (envelope icon) or go to **File** → **Subscribe to report**
3. Click **+ Add new subscription**

![Power BI subscribe to report email subscription setup panel](screenshot_subscribe)

4. Fill in the subscription settings:

| Setting | Description |
|---|---|
| **Name** | Label for this subscription |
| **Recipients** | Email addresses (comma-separated) |
| **Subject** | Email subject line |
| **Message** | Optional custom message body |
| **Frequency** | Daily, Weekly, or After data refresh |
| **Time & Time Zone** | When to send the email |
| **Start/End Date** | Optional delivery window |
| **Include attachment** | Attach a PDF or PowerPoint of the report |

5. Click **Save and close**

>  Recipients will receive an email with a **snapshot image** of the report and (optionally) a **PDF or PPT attachment** on the schedule you set. They do not need a Power BI account to view the attachment.

---

### Method 2: Manually Send an Exported File

For one-off report sharing via email, follow these steps:

**Step 1 — Export the report**

Follow [Option A](#option-a-export-as-pdf) or [Option B](#option-b-export-as-powerpoint-pptx) above to export the report as a **PDF** or **PPTX** file to your computer.

**Step 2 — Attach and send**

Open your email client (Outlook, Gmail, etc.) and compose a new email:

1. Click **Attach file**
2. Navigate to your exported PDF or PPTX
3. Add your recipients, subject, and message
4. Click **Send**

>  **For Outlook users:** You can also right-click the exported file in File Explorer → **Send to** → **Mail recipient** to quickly open a pre-attached email draft.

---

### Bonus: Send via Microsoft Teams

If your organization uses **Microsoft Teams**, you can share Power BI reports directly:

1. Open the report in Power BI Service
2. Click **Share** → **Chat in Teams**
3. Search for a Teams channel or person
4. Add a message and click **Share**

