# Free sample — Shipped App Security Checklist Pack

**Teaser only** — not the full $39 Complete pack.  
Use this to feel the quality. Upgrade when you want the full checklist, finding examples, and ship-blocker roadmap.

| | Free sample | Starter ($19) | Complete ($39) |
|---|-------------|----------------|----------------|
| Self-intake | **This page (short)** | Full `intake-self.md` | Full |
| Checklist | **12 rows** (Auth + Authz) | Full `checklist.md` | Full |
| Finding template | **Blank block only** | — | Full + filled examples |
| Fix roadmap | — | — | Full A/B/C ship-blocker tables |
| README / how-to | — | Short | Full |

**Rules:** Findings + remediation only. **No exploit PoCs.** Note locations so you can fix — not recipes to attack. Prefer staging. Review only apps you own or are authorized to test.

**Buy:** [Shipped App Security Checklist Pack on Gumroad](https://corymaynard.gumroad.com/l/izkrnm) — **Complete $39** (recommended). **30-day refund** on paid versions.

Related done-for-you audit (separate SKU): this repo's [README](./README.md).

---

## 1. Mini intake (scope this pass)

| Question | Answer |
|----------|--------|
| App / product name | |
| Live, launching, or internal? | |
| Staging URL (preferred for checks) | |
| Auth provider / library | |
| Payments live / test / none? | |
| Top risk this week (one sentence) | |
| Hours you can spend | |

Confirm:

- [ ] I am reviewing **my** product (or I have written authorization).  
- [ ] I will prefer **staging** for any hands-on verification.  
- [ ] I will document findings + remediation only — no exploit PoCs.  
- [ ] DIY sample ≠ audit / compliance certification.

---

## 2. Partial checklist — Auth & authorization (subset)

**Status key:** `Pass` · `Fail` · `N/A` · `Follow-up`  
**Location / notes:** file, route, config key, or dashboard setting.

### Authentication & sessions

| # | Check | Status | Location / notes |
|---|-------|--------|------------------|
| A3 | Session cookies set `HttpOnly`, `Secure` (production), and an explicit `SameSite` | | Cookie name(s) + where set: |
| A5 | Logout invalidates the server-side session or token denylist as applicable | | Logout route + session store: |
| A6 | Password-reset / magic links expire quickly and are single-use | | Reset token TTL + handler: |
| A10 | OAuth redirect URIs are allowlisted; `state` / CSRF protections enabled | | OAuth app settings + callback: |
| A13 | Rate limits on login, password reset, and OTP endpoints | | Rate-limit config: |
| A14 | Auth events logged (login success/fail, password change, MFA changes) — no secrets in logs | | Log sink + event names: |

### Authorization / object-level access (IDOR / BOLA)

| # | Check | Status | Location / notes |
|---|-------|--------|------------------|
| Z2 | Object access checks ownership/tenant — not just “logged in” | | Example resource route: |
| Z3 | Changing an ID in the URL/body cannot reach another user’s record | | Routes that take resource IDs: |
| Z4 | Admin routes require an explicit **server-side** role check | | Admin route + role check: |
| Z5 | Multi-tenant apps isolate by org/workspace ID on every tenant query | | Tenant scope helper: |
| Z6 | Client-supplied roles / `isAdmin` flags are never trusted alone | | Any role fields from body?: |
| Z10 | Export / “download all” endpoints enforce the same object-level rules | | Export routes: |

---

## 3. Blank finding (copy per Fail)

### F-XXX — Title

- **Severity:** Critical / High / Medium / Low / Info  
- **Area:** Authentication · Authorization · Secrets · API / data · Uploads · Payments · Dependencies · Deploy / config  
- **Checklist ref:** (e.g. A3, Z2)  
- **Affected location(s):**  
- **Description:**  
- **Evidence (non-PoC):** Locate the issue. No payloads or attack scripts.  
- **Impact:**  
- **Remediation:**  
- **Verification:**  
- **Owner:** Founder-dev / contractor / platform config  
- **Status:** Open · In progress · Fixed · Accepted risk  

---

## What’s in Complete ($39) that this sample omits

- Full checklist across secrets, APIs (incl. CORS, URL-fetcher questions), uploads, payments, deps, deploy/admin/backups/CSP  
- Two **filled** fictional finding examples (IDOR + secrets) so you see the bar  
- **Roadmap** with ship-blocker vs next-sprint vs later + launch gate  
- Full self-intake + crisp README how-to  

**DIY ≠ audit.** Completing any of these templates does not certify your app.

*Free sample for marketing / GitHub teaser. Not for resale.*
