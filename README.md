# Snekl extensions

Out-of-process extensions for [Snekl](https://github.com/chucklyfun/snekl). Each app is its own server, with its own database and admin. Snekl places an extension as a sandboxed iframe on a forum page and authorizes it with the existing install grant.

Links stay in the Snekl repo as a first-party block. This repo is for apps that need their own storage.

## Calendar

First extension. A mod installs it on a forum, places the iframe, and opens this server’s admin from that setup screen.

- Admin at `{calendarHost}/admin/`, same two-step sign-in as Snekl’s other servers: an Account identity, then a password that exists only on this server.
- Events live here, keyed by the forum placement.
- The iframe receives the placement id, the content base URL, the forum slug, and the parent slug when the forum is nested.
- Permissions on this server: view, create, update, and delete events, plus a grant that lets the chosen watercooler reference the calendar.
- When an event starts, this server’s bot posts into the watercooler selected in the admin, using the install’s reply grant.

## Layout

```
calendar/    Calendar server
```
