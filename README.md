# YachtWay link board

An interactive map of how the YachtWay pages connect. Internal.

`index.html` is stored **encrypted** (AES-256-GCM, PBKDF2-SHA256, 250k iterations).
It decrypts in the browser when the password is entered. Nothing readable is served
without it, so the file is safe to host on a public URL.

The plaintext source and the build script live outside this repo, at
`~/yachtway-link-board.src`. To rebuild after editing `board.html` there:

    BOARD_PW='...' node build.js

That rewrites `index.html` here. Commit and push as normal.

`.password` in the source directory holds the current password, mode 600, and is
never committed.
