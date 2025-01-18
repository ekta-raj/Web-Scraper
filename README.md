# Web Scraper for NCMHCE Practice Exam

This repository contains a Python script designed to scrape practice exam data from [tests.com](https://www.tests.com). The script uses Selenium to automate data collection, capturing detailed information about exam questions, options, and explanations. The extracted data is structured and exported to a CSV file for further analysis.

## Features

- **Automated Navigation**: The script automates the process of navigating through the practice exam, starting from login to completing the test.
- **Question Data Extraction**: Captures essential data such as:
  - Patient demographic and presenting problem.
  - Multiple-choice question text and answer options.
  - Correct answer and explanation.
- **Dynamic Element Handling**: Utilizes Selenium's `WebDriverWait` to handle dynamic content and avoid interruptions.
- **CSV Export**: Outputs the scraped data in a structured CSV format for easy analysis.

## Prerequisites

1. **Python**: Ensure Python 3.x is installed.
2. **Libraries**: Install the required Python libraries:
   ```bash
   pip install selenium pandas
   ```
3. **WebDriver**: Download the appropriate WebDriver for your browser (e.g., ChromeDriver for Google Chrome) and ensure it is accessible in your system's PATH.

## Setup and Usage

### Step 1: Update Login Credentials
Update the `login` function with your email and password for [tests.com]:
```python
driver.find_element(By.ID, 'Email').send_keys('<your-email>')
driver.find_element(By.ID, 'pw').send_keys('<your-password>')
```

### Step 2: Run the Script
Execute the script using:
```bash
python Webscraper.py
```

### Step 3: Output
The scraped data will be saved as a CSV file at the specified location:
```plaintext
/Users/ektaraj/Desktop/examfinal.csv
```

## Script Workflow

1. **Login**: The script logs in to the website using the provided credentials.
2. **Data Scraping**: It navigates through the exam, collecting:
   - Scenario details
   - Question text and answer options
   - Correct answer and explanation
3. **Next Question**: The script clicks the "Next" button to proceed to the following question, repeating the process until no questions remain.
4. **Export**: All data is compiled into a pandas DataFrame and exported as a CSV.

## Error Handling

The script is equipped with basic error handling to manage cases where elements are not found or questions are exhausted:
- If no more questions are available, the script will exit gracefully.

## Example Output

The CSV file contains the following columns:
- Source
- Exam Name
- Question #
- Case Study #
- Patient Demographic
- Presenting Problem
- Context
- Choice A, B, C, D
- Question
- Correct Answer
- Explanation Answer

## Notes

- Ensure you have sufficient time to navigate the initial setup of the test before the script automates the process.
- The script requires manual intervention during the first step to set test preferences and start the exam.
