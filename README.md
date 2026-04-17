# Yindeng Announcement Crawler

This project is a Python-based crawler implemented in a Jupyter Notebook for downloading non-performing loan (NPL) transfer announcements and transfer result announcements from the Yindeng website within a specified date range.

The crawler supports automatic pagination, date filtering, structured file storage, and logging for further analysis.

---

## Project Structure

```
.
├─ yindeng_crawler.ipynb   # Main crawler notebook
├─ README.md
├─ requirements.txt
├─ .gitignore
└─ LICENSE
```

---

## Features

* Download transfer announcements
* Download transfer result announcements
* Filter announcements by date range
* Automatically handle pagination
* Save PDF files into structured folders
* Generate download logs (CSV)

---

## Requirements

* Python 3.10+
* requests
* beautifulsoup4
* pandas

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## How to Use

### 1. Open the Notebook

Open the notebook file:

```
yindeng_crawler.ipynb
```

using Jupyter Notebook or VS Code.

---

### 2. Modify Parameters

At the top of the notebook, adjust the parameters:

```python
START_DATE = "2026-04-01"
END_DATE = "2026-04-30"

NOTICE_TYPE = "transfer"

BASE_OUTPUT_DIR = Path("./output")
RUN_FOLDER_NAME = "2026-04_yindeng_download"
```

#### NOTICE_TYPE options:

* `"transfer"` → transfer announcements only
* `"result"` → transfer result announcements only
* `"all"` → both types

---

### 3. Run the Notebook

Run all cells:

```
Run All
```

---

## Output Structure

Downloaded files will be saved in the following structure:

```
output/
└─ 2026-04_yindeng_download/
   ├─ 转让公告/
   │   └─ YYYY-MM/
   ├─ 转让结果公告/
   │   └─ YYYY-MM/
   └─ logs/
```

---

## Log File

A CSV log file will be generated, including the following fields:

* notice_type
* page_no
* page_url
* title
* detail_url
* publish_date
* pdf_url
* pdf_local_path
* status

---

## Notes

* The crawler depends on the current structure of the Yindeng website.
* If the website structure changes, parsing logic may need to be updated.
* This project is intended for research and workflow automation purposes.

---

## Disclaimer

Please ensure that your use of this project complies with the target website’s terms of service and any applicable regulations.
