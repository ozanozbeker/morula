# Morula

Lightweight, Pythonic sibling to R's [{blastula}](https://github.com/rstudio/blastula). Morula focuses on **sending** HTML emails using Python’s standard library, leaving email body composition to tools like [Quarto](https://quarto.org).

## Features

- Simple API for sending HTML emails over SMTP
- Built on Python’s built-in `smtplib` and `email` modules
- Reads email bodies directly from `.html` files
- MIT licensed and easy to extend

## Installation

```bash
uv add morula
```

## Quickstart

1. Render your HTML email (e.g., using Quarto):

```bash
quarto render email.qmd --to html
```

3. Send with Morula:

```python
from morula import Email

email = (
    Email()
    .from_("me@example.com")
    .to("you@example.com")
    .subject("Weekly Update")
    .html_body("email.html")
)

email.send(
    smtp_server="smtp.example.com",
    port=587,
    username="me@example.com",
    password="yourpassword"
)
```

## Why "Morula"?

In biology, a _morula_ is an early stage of development before the blastula. This reflects Morula's influence from blastula and its ligher scope: only sending emails, no built-in composition layer.
