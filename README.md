# rome-move-line-issue
This repository shows a repro of an issue with the Rome VS Code extension

In `repro.ts`, moving the line `JSON.stringify("hi");` up and down repeatedly will cause VS Code to show this error:

```
[Error - 15:07:16] Request textDocument/codeAction failed.
  Message: failed to access range Range { start: Position { line: 2, character: 21 }, end: Position { line: 2, character: 21 } } in document file:///c%3A/Users/<redacted>/code/rome-move-line-issue/repro.ts
  Code: -32603 
failed to access range Range { start: Position { line: 2, character: 21 }, end: Position { line: 2, character: 21 } } in document file:///c%3A/Users/<redacted>/code/rome-move-line-issue/repro.ts

Caused by:
    position Position { line: 2, character: 21 } is out of range
```

It's quite intermittent, possibly linked to how loaded the CPU is and how far the line is being moved up/down
