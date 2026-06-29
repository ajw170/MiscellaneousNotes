---
title: "Retry Loop with Exponential Backoff"
date: 2026-06-29
language: Python
tags: [python, networking, error-handling]
---

Retries a function up to `max_retries` times with exponential backoff.

```python
import time

def retry(func, max_retries=5, base_delay=1.0):
    for attempt in range(max_retries):
        try:
            return func()
        except Exception as e:
            if attempt == max_retries - 1:
                raise
            delay = base_delay * (2 ** attempt)
            print(f"Attempt {attempt + 1} failed: {e}. Retrying in {delay}s...")
            time.sleep(delay)
```

**Usage:**

```python
result = retry(lambda: requests.get("https://example.com", timeout=5))
```
