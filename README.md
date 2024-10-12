# Review Scraper

![Review Scraper Logo](https://via.placeholder.com/600x200?text=Review+Scraper) <!-- Placeholder for logo -->

## Overview

Welcome to the **Review Scraper** project! This tool is designed to extract insightful data from user reviews on product webpages, particularly on e-commerce platforms. The extracted data includes ratings, textual reviews, reviewer names, dates, review descriptions, and reviewer locations (when available). This project aims to provide a comprehensive and structured dataset suitable for further analysis, sentiment analysis, and other data-driven insights.

---

## Key Features

- **Automated Scraping**: Utilizes Selenium for automating interactions with the webpage, ensuring complete data extraction from reviews hidden behind "READ MORE" buttons.
- **Multi-Page Scraping**: Automatically navigates through multiple pages of reviews to gather a comprehensive dataset.
- **Customizable URL**: Easily modify the target URL in the script to adapt it for different product review pages.
- **Data Storage**: Saves scraped data in both CSV and JSON formats, facilitating easy analysis and retrieval.
- **Structured Data**: Extracts essential fields from the reviews, including:
  - Rating
  - Review Text
  - Reviewer Name
  - Date
  - Review Description
  - Location

---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Files Generated](#files-generated)
- [Contributing](#contributing)
- [License](#license)

---

## Installation

### Prerequisites

Before you begin, ensure you have the following installed:
- **Python 3.x**
- **Google Chrome** (for ChromeDriver compatibility)

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd <project-directory>

### Step 2: Install Dependencies

Install all required Python libraries using the `requirements.txt` file:

```bash
pip install -r requirements.txt

### Step 3: Set Up ChromeDriver

1. **Download ChromeDriver**: Go to the [ChromeDriver downloads page](https://chromedriver.chromium.org/downloads) and download the version that matches your installed Chrome browser version.

2. **Install ChromeDriver**: Follow the installation instructions for your operating system:

   - **Windows**:
     - Unzip the downloaded file and move `chromedriver.exe` to a location on your system (e.g., `C:\Program Files\ChromeDriver\`).
     - Add the location to your system's PATH:
       - Search for "Environment Variables" in the Windows search bar.
       - Click on "Environment Variables."
       - Under "System variables," find the `Path` variable and click "Edit."
       - Click "New" and add the path to the folder where `chromedriver.exe` is located.

   - **macOS**:
     - Unzip the downloaded file and move `chromedriver` to `/usr/local/bin`:
       ```bash
       mv path/to/chromedriver /usr/local/bin
       ```
     - Ensure that `/usr/local/bin` is in your PATH. You can check by running:
       ```bash
       echo $PATH
       ```

   - **Linux**:
     - Unzip the downloaded file and move `chromedriver` to `/usr/local/bin`:
       ```bash
       sudo mv path/to/chromedriver /usr/local/bin
       ```
     - Ensure that `chromedriver` has executable permissions:
       ```bash
       sudo chmod +x /usr/local/bin/chromedriver
       ```

3. **Verify Installation**: Open your command line interface and run:
   ```bash
   chromedriver --version

### Notes:
- The step-by-step instructions are organized for clarity.
- Command-line instructions are provided for each operating system.
- Feel free to customize any part as needed!

### Usage

#### Running the Scraper

To start scraping reviews, run the `scraper.py` script by executing the following command in your terminal:

```bash
python scraper.py

The script will scrape reviews from the specified URL, automatically handling pagination and clicking "READ MORE" to reveal the full review text.

### Example URL

You can test the scraper with the following URL:

```plaintext
https://www.flipkart.com/harry-potter-philosopher-s-stone/product-reviews/itmfc5dhvrkh5jqp?pid=9781408855652


### Files Generated

Upon successful execution of the scraper, the following files will be generated:

1. **allReviews.csv**  
   Contains the complete set of scraped reviews, including:
   - **Rating**
   - **Review Text**
   - **Reviewer Name**
   - **Date**
   - **Review Description**
   - **Location** (if available)

2. **allReviews.json**  
   Stores the scraped reviews in structured JSON format, ideal for further analysis and processing.

3. **tempReviews.csv**  
   A temporary file that stores reviews from each page. This file is combined into `allReviews.csv` once the scraping is complete.

### Customization

This scraper is tailored for Flipkart, but you can modify it for other platforms. Here's how:

1. **Change the Target URL**  
   Update the `url` variable in `scraper.py` to point to the desired product review page:

   ```python
   url = "https://www.flipkart.com/product-reviews-page"

2. **Modify the Scraping Logic***

You may need to adjust the following in the `cus_rev()` function to match the HTML structure of your target webpage:

- **Class names**
- **Element tags**

If the "READ MORE" button or pagination elements have different identifiers, update the `click_all_read_more_buttons()` function accordingly.

3. **Adjust Button Clicks**

If the "READ MORE" button or pagination elements have different identifiers, update the click_all_read_more_buttons() function accordingly.


### Contributing

We welcome contributions! If you want to enhance this project or add features, please follow these steps:

1. **Fork the repository.**
2. **Create a new feature branch:**
   ```bash
   git checkout -b feature-branch-name
3. **ommit Your Changes**
To commit your changes, use the following command:
```bash
git commit -m 'Add some feature'

4. **Push to the Branch**
After committing your changes, push them to your feature branch:
```bash
git push origin feature-branch-name
5. **Open a Pull Request**
Once your changes are pushed, open a pull request.

### Contribution Guidelines
To maintain project quality:
- Ensure your code is well-commented.
- Conduct proper testing for your changes.
- Provide a clear description of your modifications in the pull request.

### License
This project is licensed under the MIT License. You are free to use, modify, and distribute this project as you see fit.

