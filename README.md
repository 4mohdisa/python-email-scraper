# Python Email Scraper

A robust web scraping tool that extracts email addresses from websites. This script crawls through web pages starting from a given URL and collects all email addresses it finds along the way.

## Features

- Crawls websites recursively starting from a user-provided URL
- Extracts email addresses using regular expressions
- Handles relative and absolute URLs
- Prevents duplicate URL processing
- Limits crawling depth to prevent infinite loops
- Provides real-time processing feedback

## Requirements

The following Python packages are required to run this project:

```
beautifulsoup4==4.9.3
requests==2.26.0
lxml==4.9.1
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/python-email-scraper.git
cd python-email-scraper
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

## Usage

1. Run the script:
```bash
python email_scraper.py
```

2. Enter the target URL when prompted:
```
[+] Enter Target URL To Scan: https://example.com
```

3. The script will start crawling the website and display its progress:
```
[1] Processing https://example.com
[2] Processing https://example.com/about
...
```

4. Found email addresses will be displayed at the end of the execution or when you interrupt the process using Ctrl+C.

## How It Works

1. The script starts with the user-provided URL and initializes empty sets for storing scraped URLs and found email addresses.

2. For each URL in the queue:
   - The page is downloaded using the `requests` library
   - Email addresses are extracted using regular expressions
   - All links on the page are collected using BeautifulSoup
   - New, unprocessed links are added to the queue

3. The process continues until:
   - The URL queue is empty
   - The maximum count (100) is reached
   - The user interrupts the process

## Limitations

- The script is limited to processing 100 URLs to prevent excessive crawling
- It only processes text-based content (HTML pages)
- Some websites may block automated requests
- The script follows a basic email regex pattern and might miss complex email formats

## Error Handling

The script includes error handling for:
- Invalid URLs
- Connection errors
- Missing URL schemes
- Keyboard interrupts

## Contributing

Feel free to fork this repository and submit pull requests with improvements. You can also open issues for bugs or feature requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

Please ensure you have permission to scrape websites before using this tool. Some websites prohibit scraping in their terms of service.
