Starting TowTruck (via a `startTowTruck()` or by other means), pulls
in a bunch of CSS and JavaScript (`styles` and `scripts` in
`towtruck.js`).  It sets `window._startTowTruckImmediately` to `true`
before importing the scripts.

`channels.js` sets up channel generators for communicating between
windows (via `postMessage`) and with the TowTruck server (via a
WebSocket).  A new `TowTruck` instance is created and attached to
`window.TowTruck`, and the generators are stored as `TowTruck` methods
(e.g. `TowTruck.WebSocketChannel`)

`towtruck-runner.js` generates a `TowTruck.shareId` to identify a
particular window.  This ID is used to generate the message hash.  A
channel is opened with the TowTruck server, and the opened channel is
stored in `TowTruck.channel`.

On `.start`, a window is popped up with the share URL, TODO.
