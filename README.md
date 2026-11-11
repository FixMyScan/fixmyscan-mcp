# FixMyScan MCP server and agent skill

[FixMyScan](https://fixmyscan.com) turns scanned books (PDF or DjVu, up to 1,000 pages) into clean, searchable PDFs for Kindle, Kobo, reMarkable and tablets: pages cropped and straightened, sharp black and white or gentle greyscale, two-page spreads split, searchable text added.

This repo holds the public connection details. The server itself is hosted.

## Connect

Remote MCP server (Streamable HTTP, OAuth 2.1 sign-in):

```
https://mcp.fixmyscan.com/mcp
```

Setup for ChatGPT, Claude, Cursor and other MCP clients: [fixmyscan.com/ai](https://fixmyscan.com/ai)

## Tools

| Tool | What it does |
|---|---|
| `fix_scan` | Starts a book from an attachment, a link or an upload |
| `create_upload_link` | Gives the reader a page to drop a PDF when the app can't pass files |
| `preview_scan` | Shows 3 pages before and after |
| `get_scan_status` | Progress, then the download link |
| `list_my_scans` | Books from the last 24 hours |
| `cancel_scan`, `delete_scan` | Stop or remove a book |

## Agent skill

[`skills/fixmyscan/SKILL.md`](skills/fixmyscan/SKILL.md) tells an agent how to use the MCP server or the REST API.

```
npx skills add FixMyScan/fixmyscan-mcp
```

## REST API

Base URL `https://api.fixmyscan.com/v1` with an API key from your [account](https://app.fixmyscan.com/account). Reference: [openapi.json](https://api.fixmyscan.com/openapi.json), [developer page](https://fixmyscan.com/api).

Files are deleted 24 hours after a book is ready.
