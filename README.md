# CUPl JWC Notice Watch

[中文文档](README.zh-CN.md)

An unofficial daily archive and dashboard for public notices from the Academic Affairs Office of China University of Political Science and Law.

![Dashboard preview](assets/demo.svg)

> Disclaimer: this project only archives public webpages. It is not affiliated with China University of Political Science and Law and does not represent official information. Always verify important academic affairs with the official website.

## Target Site

- Site: 中国政法大学教务处
- Homepage: <https://jwc.cupl.edu.cn/>
- Notice sections: 教务管理、学籍管理、教学研究、考务管理、实践教学、教材建设、质量监控、教学服务、交流培养

## What It Does

- Fetches notice title, date, link, summary, section, source URL, first-seen time, and last-seen time
- Handles the site dynamic browser challenge before fetching pages
- Keeps `data/notices.json`, `data/notices.csv`, and daily snapshots under `data/history/`
- Provides a static dashboard with keyword search and section filtering
- Runs daily through GitHub Actions and commits changed data files

## Quick Start

```bash
python3 scraper.py 2
python3 -m http.server 8080
```

Open:

```text
http://localhost:8080
```

## Data Files

- `data/notices.json`: merged historical notice database
- `data/notices.csv`: spreadsheet-friendly export
- `data/meta.json`: update metadata
- `data/history/YYYY-MM-DD.json`: notices fetched on each run

## Architecture

![Architecture](assets/architecture.svg)

## Daily Update

The workflow in `.github/workflows/update.yml` runs every morning and commits changed data files.

## Project Document

The repository includes a Word project document:

```text
docs/project_proposal.docx
```

## License

MIT
