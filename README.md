# Crawling Tutorial

A modern, opinionated short course on crawling and scraping the web — what it
*is*, when it's the right tool, and how to do it without becoming a nuisance.

The mechanical parts of scraping have largely been automated by now. What this
course teaches you instead is the *judgement*: how the web actually works, when
to scrape and when not to, how to be a polite citizen at scale, and how to put
something together that's still running quietly two years from now.

Eleven self-contained Jupyter notebooks. Each is roughly 30–60 minutes of
reading + tinkering, in order.

## Syllabus

| #   | Notebook                                       | What you'll come away with                                                              |
| :-- | :--------------------------------------------- | :-------------------------------------------------------------------------------------- |
| 00  | `00_what_is_the_web.ipynb`                     | A working mental model of HTTP, the DOM, and server- vs. client-rendered pages.         |
| 01  | `01_what_is_crawling.ipynb`                    | Crawling vs. scraping vs. parsing, robots.txt, the legal & ethical frame.                |
| 02  | `02_http_in_python.ipynb`                      | `httpx` end-to-end — sessions, headers, cookies, status codes, retries.                  |
| 03  | `03_parsing_html.ipynb`                        | BeautifulSoup + `lxml`, CSS selectors, XPath, when to pick which.                        |
| 04  | `04_static_crawler.ipynb`                      | Pulling a real static site end-to-end: pagination, dedup, JSONL/SQLite persistence.      |
| 05  | `05_javascript_rendered_pages.ipynb`           | Playwright for JS-rendered pages — when you actually need a browser, and when you don't. |
| 06  | `06_async_and_politeness.ipynb`                | `asyncio` + `httpx`, concurrency caps, exponential backoff, "don't be a jerk".           |
| 07  | `07_apis_first.ipynb`                          | Sitemaps, JSON-LD, hidden XHR endpoints — try these *before* parsing HTML.               |
| 08  | `08_anti_bot_and_when_not_to_scrape.ipynb`     | Fingerprinting, captchas, the vendor stack, and the underrated option of *not*.          |
| 09  | `09_llm_driven_extraction.ipynb`               | When selectors are the wrong tool — LLM extraction with a strict schema and real costs.  |
| 10  | `10_from_script_to_dependable_pipeline.ipynb`  | Capstone: storage, scheduling, observability, and the discipline to keep it alive.       |

## How to use this

Read the notebooks **in order**. Each one assumes the previous, and the last
two (`09`, `10`) only make sense once you've built something with `04`–`08`.

The notebooks are written to be *read first*, *run second*. Most cells will
work as-is, but treat the live targets as illustrative — sites change. The
ideas don't.

## Setup

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m playwright install chromium      # only needed once, for lecture 05
jupyter lab
```

Python 3.11+ recommended.

## Audience

You can program in Python — loops, functions, virtualenvs, the basics. You
don't need to have scraped anything before. If you've used `requests` once
and bounced off `BeautifulSoup`, this is for you.

It's pitched at university-level self-learners and early-career engineers.
There's nothing here that a first-year CS student couldn't follow, and
nothing that an experienced backend engineer would find *only* obvious.

## What this course is not

- A reference manual for any single library. The libraries change; the
  reference is their docs.
- A guide to evading anti-bot systems. Lecture 08 makes the case for why.
- A list of "10 sites you can scrape today." It's about the underlying
  craft, not a recipe book.

## License

MIT. See `LICENSE`.
