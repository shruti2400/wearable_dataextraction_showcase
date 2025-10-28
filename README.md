# 🧠 Wearable Data Extraction API

The **Wearable Data Extraction API** is an automated system built to scrape, clean, and visualize product data from major wearable brands.

This project extracts product-related data (features, specifications, reviews, FAQs, and details) from brand websites, processes it into clean datasets, and automates the uploading of the final results to **OneDrive** for **Power BI dashboard** visualization.

It includes both **automatic scheduled scraping** and **manual API endpoints** for on-demand scraping.

---

## 🎯 What This Project Does

### 🕸️ 1. Web Scraping
Each brand has its own Selenium-based scraper.  
The scraper automatically reads category URLs from a CSV input file and extracts data such as:

- Product details  
- Specifications  
- Features  
- FAQs  
- Customer reviews  

---

### 🧹 2. Preprocessing
The raw scraped data passes through multiple cleaner scripts inside the `preprocessor/` folder.  
Each script removes duplicates, fixes formatting issues, and standardizes data across all categories.

---

### 💾 3. Data Storage
The cleaned data from all categories of a brand are merged and stored inside a `merged_data/` folder within that brand’s directory.  

---

### ⚙️ 4. Automation & Uploading
The project is integrated with **n8n**, a workflow automation tool.  
After every successful run, **n8n automatically uploads the cleaned CSV files to OneDrive** for easy access and can later synchronize with Power BI.

---

### 📊 5. Visualization
Power BI dashboards to visualize the **latest cleaned data** for each brand.  
This helps track new product launches, compare brand features, and monitor reviews in real time.


