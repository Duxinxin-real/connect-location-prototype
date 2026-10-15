# MVP Prototype QA Inventory

## User-visible claims

- Bottom navigation contains only Connect, Alerts, and Me.
- Connect defaults to Me and has no All, Group, or Find entry.
- Contact selection switches the visible route, pin, details, and history.
- Contact selection draws the whole route first, then reveals route points, photo marker, and current-location avatar.
- Add opens a reusable personal invite-code panel.
- Invite supports My code / Enter code, one-time profile sharing, code refresh, and the first location permission explanation.
- Camera entry simulates publishing a location photo to all connected contacts.
- History expands the contact sheet and shows photos plus location events.
- SOS starts unset, confirms recipients and scope once, then supports a cancellable tap countdown or a two-second hold for immediate activation.
- Alerts switches contacts and toggles notification delivery.
- Creating an alert rule requests background location and notification permissions in sequence.
- Me exposes editable profile, contacts, SOS contacts, location sharing, permissions, legal/support entries, and account deletion.

## Control and state coverage

| Control | Functional check | Visual state |
|---|---|---|
| Me/Kevin/Mia selector | Switch content and selected state | Connect default and contact-selected |
| Route entrance sequence | Draw line, reveal points, then reveal photo/current-location markers | Mid-animation and settled contact-selected states |
| Add button | Switch My code/Enter code; refresh/copy code; accept a six-character code | Invite panel and first-location permission |
| Camera badge | Open photo composer; request Camera or Photo Library when its source is selected; publish | Photo composer and permission prompt |
| Directions | Show system-map simulation | Contact selected |
| Contact | Show call or add-number simulation | Kevin and Mia |
| History | Expand/collapse; scroll four photos and six recent events; reveal and hide four earlier photos plus six earlier events; reset to the latest seven days when reopening or changing contact | Recent-only, all-history, and scrolled-to-bottom states |
| SOS | First tap opens an unselected contact picker; after at least one contact is selected, the next screen reviews recipients, sent content, and limitations; setup ends in Ready without sending. Later taps start a 10-second countdown; two-second hold skips the countdown; cancel, activate, simulate seen, end, and one-hour auto-end | Unset, contact selection, confirmation, permission, ready, countdown, and active SOS states |
| Alerts tab | Open alerts page | Alerts page |
| Alert contacts | Switch selected contact | Kevin and Mia alert states |
| Add/edit alert rule | Step 1 selects a place by search or the embedded tappable map; Step 2 selects an avatar contact from a vertical list, then edits name, trigger, and radius; save through Always Location and Notification permission prompts | Location/map step, vertical contact step, selected-contact state, and permission prompts |
| Notification switch | On, off, on | Alerts sheet |
| Me tab | Open settings page | Me page |
| Profile card | Edit and save local name and phone | Profile editor |
| Contact row | Open local-contact manager | Contact manager |
| SOS contacts | Select at least one recipient; zero selections block sending and route back to the selector | SOS contact selector |
| Progressive permissions | Request Notification on first entry; otherwise allow/decline when invitation, Alerts, photo, or SOS requires a permission | Centered iOS system-style alerts for Notification, Location, Background Location, Camera, and Photos |
| Privacy/User Agreement/Support | Open local document or topic picker | Legal and support sheets |

## Exploratory checks

- Repeatedly open and close History, invite, and SOS overlays to confirm layers do not trap input.
- Confirm History hides map tools, route markers, and SOS instead of leaving partially clipped controls behind the expanded sheet.
- Confirm bottom overlays use the same fade-and-slide entrance and remain above tabs, sheets, and map controls.
- Verify the layout at 393×852 and 375×667 without clipped navigation or inaccessible primary controls.
- Verify every permission alert uses the same iOS system treatment: centered 270 pt panel, system-blue actions, fine separators, no grabber, and no custom feature icon.
