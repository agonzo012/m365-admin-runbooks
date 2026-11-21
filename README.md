# Microsoft 365 Admin Runbooks

## What This Is

Step-by-step admin guides (runbooks) for the Microsoft 365 tasks I
practiced in the tenant: Exchange Online, Teams, and SharePoint. Each
runbook is written so someone else could follow it and get the same
result.

The M365 Developer Tenant (Instant Sandbox) is not available —
Microsoft now limits the free E5 developer sandbox to Visual Studio
Professional/Enterprise subscribers, partner program members, or
Premier/Unified Support customers, and a personal account does not
qualify. This work uses the tenant that comes with the Azure free
trial, unblocked by a 30-day Microsoft 365 Business Premium trial
(free, $0.00, expires Dec 21, 2026, recurring billing Off). One trial
license is assigned to the admin account (1/25 assigned).

## Tools Used

- Microsoft 365 admin center (admin.microsoft.com)
- Exchange admin center (admin.exchange.microsoft.com)
- Teams admin center (admin.teams.microsoft.com)
- SharePoint admin center

## Runbooks

### Teams policy — done Nov 21, 2026

Custom meeting policy "Lab Meeting Policy" in the Teams admin center.
Settings: Who can present = "Only organizers and co-organizers" (the
Teams UI's strictest option — there is no literal "Organizer only"
choice), Meeting recording = Off. Assigned to Alex Rivera (Direct
assignment); his Policies tab shows Meeting policy "Lab Meeting
Policy".

To repeat it: Teams admin center > Meetings > Meeting policies >
Add > name the policy, set Who can present to "Only organizers and
co-organizers", set Meeting recording to Off, save, then assign it
under Users > select the user > Policies > Meeting policy.

### SharePoint site — done Nov 21, 2026

Team site "IT Department" in the SharePoint admin center (Standard
team template). Site address:
https://alvingonzogmail.sharepoint.com/sites/ITDepartment. Group
email ITDepartment, Privacy Private, Language English. Group owner:
Alex Rivera (set as the required Group owner at creation; the site's
Primary admin shows "Group owners" / "IT Department Owners").

To repeat it: SharePoint admin center > Sites > Active sites >
Create > Team site (Standard template) > name it, set the Group
owner, choose Privacy, and create.

### Exchange mail flow rule and shared mailbox — blocked

Not created yet. The Exchange admin center would not load on
Nov 21, 2026 — it failed persistently with "Error: Parsing of
Response Content Failed in Api Operations" (4 attempts: home page,
reload, mailboxes deep link, retry after a wait). This looks like
Exchange Online still provisioning for the new tenant, or an EAC
API failure. The plan is a shared mailbox "IT Support"
(itsupport@alvingonzogmail.onmicrosoft.com, Alex Rivera as member)
and a mail flow rule "Prepend EXTERNAL to outside mail" that
prepends "[EXTERNAL]" to the subject of messages from outside the
organization. Retry once the admin center loads.

## Status

Teams and SharePoint are done and written up above. Exchange is
blocked on the admin center failing to load; it will be retried and
documented here when it works.

## Why It Matters

A runbook turns one-off practice into repeatable process. In a real IT
role, the next person to do the task should be able to follow the guide
and get it right.

## Next Steps

- Retry the Exchange admin center and finish the shared mailbox and
  mail flow rule, then write them up here.
- The remaining portfolio work is Intune device management (see the
  intune-device-management repo).
