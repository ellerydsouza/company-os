# Security baseline

The minimum everyone follows, from day one, no exceptions by seniority.
Adopted via [RFD 0004](../rfd/0004/README.md). Written so that a future
customer security questionnaire is a gap analysis against this page, not a
scramble.

## Accounts and access

1. **Password manager for everything, company-provided.** No passwords in
   browsers, notes apps, or heads. Shared credentials (avoid where possible)
   live only in shared vaults, never in chat.
2. **2FA on every account that supports it**; hardware keys or authenticator
   apps, not SMS, for the crown jewels (email, cloud provider, code hosting,
   banking, DNS/registrar).
3. **Granting access and recording it are the same act.** Every grant is
   logged in the access inventory (below) when made — an unrecorded grant is
   the thing [offboarding](../playbooks/offboarding.md) can't revoke.
4. **Least privilege by default**: admin roles only where the job requires
   them; personal accounts never used for company services, company accounts
   never for personal ones.

## The access inventory

A single sheet/page listing: system → who has access → level → who granted
it, when. It is the source of truth for onboarding grants, quarterly
spot-checks, and offboarding revocation. If a system isn't in the inventory,
finding that out during an offboarding is the failure mode.

## Data and devices

5. **Laptops**: full-disk encryption on, screen lock on, OS auto-updates on.
   Company data stays in company systems, not personal devices/drives.
6. **Backups exist and have been restored.** Whatever we'd cry about losing
   (code, books, cap table, customer data) is backed up automatically, and a
   restore has been *tested* — an untested backup is a hope, not a backup.
7. **Customer data is handled only in the systems designated for it.** No
   production data in local files, screenshots into chat, or test
   environments.

## Incidents

8. Suspected compromise of anything — account, laptop, token — is a
   security incident: run the [incident-response playbook](../playbooks/incident-response.md)
   (security events escalate to founder + legal before external statements).
   Reporting a false alarm is free; sitting on a real one is not.

## Review

- Quarterly (operating-system retro): spot-check two rules against reality;
  reconcile the access inventory against actual team.
- Annually: full review of this page alongside the vendor/insurance ritual.
