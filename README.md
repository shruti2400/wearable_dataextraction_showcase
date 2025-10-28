🧠 Wearable Data Extraction API

The Wearable Data Extraction API is an automated system built to scrape, clean, and visualize product data from major wearable brands — BoAt, Boult, and Noise.

This project extracts product-related data (features, specifications, reviews, FAQs, and details) from brand websites, processes it into clean datasets, and automates the uploading of the final results to OneDrive for Power BI dashboard visualization.

It includes both automatic scheduled scraping and manual API endpoints for on-demand scraping.

🎯 What This Project Does
🕸️ 1. Web Scraping

Each brand (BoAt, Boult, Noise) has its own Selenium-based scraper.
The scraper automatically reads category URLs from a CSV input file and extracts data such as:

Product details

Specifications

Features

FAQs

Customer reviews

🧹 2. Preprocessing

The raw scraped data passes through multiple cleaner scripts inside the preprocessor/ folder.
Each script removes duplicates, fixes formatting issues, and standardizes data across all categories.

💾 3. Data Storage

The cleaned data from all categories of a brand are merged and stored inside a merged_data/ folder within that brand’s directory.
(No database is used — all files are stored as CSV outputs.)

⚙️ 4. Automation & Uploading

The project is integrated with n8n, a workflow automation tool.
After every successful run, n8n automatically uploads the cleaned CSV files to OneDrive for easy access and synchronization with Power BI.

📊 5. Visualization

Power BI dashboards are connected to the OneDrive data folder to visualize the latest cleaned data for each brand.
This helps track new product launches, compare brand features, and monitor reviews in real time.

📁 Folder Structure
wearable_dataextraction/
├── app.py                     # Main Flask API
├── categories.csv             # Input list of category URLs
├── app.log                    # Log file for tracking scraping runs
├── requirements.txt           # Required Python libraries
│
├── scrapers/                  # Brand-specific Selenium scrapers
│   ├── boat_scraper.py
│   ├── boult_scraper.py
│   └── noise_scraper.py
│
├── preprocessor/              # Data cleaning modules
│   ├── cleaner_products.py
│   ├── cleaner_features.py
│   ├── cleaner_faqs.py
│   ├── cleaner_reviews.py
│   └── cleaner_specifications.py
│
├── data/                      # Raw and processed data
│   ├── boat/
│   ├── boult/
│   └── noise/
                

🚀 Key Highlights

🔄 Automated scraping and preprocessing for 3 major wearable brands

🧩 Modular folder structure for easy maintenance

⚙️ Integrated automation flow using n8n

☁️ Automatic upload to OneDrive

📈 Power BI dashboards for live product analytics

🧑‍💻 Tech Stack

Python (Flask, Selenium, Pandas)

n8n (workflow automation)

Power BI (data visualization)

OneDrive (cloud storage)
