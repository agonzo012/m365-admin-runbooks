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
(free, $0.00, expires Dec 21, 2026, recurring billing Off). Two trial
licenses are assigned (2/25): the admin account and Alex Rivera.

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

### Exchange shared mailbox and mail flow rule — done Nov 21, 2026

The Exchange admin center failed all day with "Error: Parsing of
Response Content Failed in Api Operations" (6 attempts across two
sessions). It finally loaded ~6:06 PM EST, once Exchange Online
provisioning for the new tenant had finished.

Shared mailbox "IT Support" (itsupport@alvingonzogmail.onmicrosoft.com)
created and verified in Recipients > Mailboxes (SharedMailbox).
Alex Rivera added as a Full Access member. Note: Alex was Unlicensed
with no mailbox, so a Business Premium trial seat was assigned to him
first (now 2/25 assigned, 23 available; total still 25 seats). His
mailbox provisioned within a minute, then he was added as Full Access.

Mail flow rule "Prepend EXTERNAL to outside mail" created and ENABLED
(rule ID c3145b90-85ef-41b4-a56b-4d02160d84a8). Condition: the sender is
from outside the organization. Action: prepend "[EXTERNAL]" to the
subject. Mode: Enforce, Priority 0. Note: the wizard creates the rule
disabled by default; it was turned on with the Enable/disable switch.

To repeat it: Exchange admin center > Recipients > Mailboxes > Add a
shared mailbox, name it "IT Support", add Alex Rivera as a Full Access
member. Then Mail flow > Rules > Add a rule > Create a new rule, set
the condition to "The sender is located outside the organization",
the action to "Prepend the subject of the message with" "[EXTERNAL]",
set the mode to Enforce, save, then turn the rule on with the
Enable/disable switch.

## Status

Teams, SharePoint, and Exchange are all done and written up above.

## Why It Matters

A runbook turns one-off practice into repeatable process. In a real IT
role, the next person to do the task should be able to follow the guide
and get it right.

## Next Steps

- The remaining portfolio work is Intune device management (see the
  intune-device-management repo).
