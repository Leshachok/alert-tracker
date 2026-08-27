# UZ Alert — walk tracker

A throwaway rig for verifying that the alert app's **background** location streaming actually
works: Android's foreground service and iOS's significant-change monitoring both post each fix
they accept, and this page draws them on a map with times, accuracy and the gap since the previous
point.

It has no backend of its own. Points live in a Firebase Realtime Database; this page reads,
renders and deletes them directly over the REST API.

**No sign-in, by design.** The tracking session lives at an unguessable path that the page takes
from its URL `#fragment`, which browsers never send to a server — so this public page does not
carry it. The link you were given is the only thing that reaches the points.

Source of truth for the page is `tools/tracker/index.html` in the app repo.
