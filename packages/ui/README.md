# @karthi13krishna/pdfme-ui

A patched version of [@pdfme/ui](https://github.com/pdfme/pdfme) with the following fix:

## What's different

**Fix: Designer no longer resets to page 1 on every template update**

When working on multi-page templates, the original `@pdfme/ui` resets
the page cursor to 0 and scrolls to top on every external `updateTemplate()`
call. This makes editing elements on page 2+ very frustrating.

This patch preserves the current page cursor across template updates,
with bounds clamping to prevent crashes when a shorter template is loaded.

## Install

```bash
npm install @karthi13krishna/pdfme-ui
```

## Usage

Drop-in replacement for `@pdfme/ui`:

```typescript
// replace this
import { Designer } from '@pdfme/ui';

// with this
import { Designer } from '@karthi13krishna/pdfme-ui';
```

Everything else stays the same.

## Credits

Built on top of [pdfme](https://github.com/pdfme/pdfme) by the pdfme team.  
Fix contributed via [upstream PR](https://github.com/pdfme/pdfme/pull/1431).

## License

MIT — same as the original pdfme package.
