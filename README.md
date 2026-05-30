# AI Cost Auditor

> Monitor, analyze, and cut AI API spend across OpenAI, Anthropic, AWS Bedrock

**Live URL:** https://aicostauditor.base44.app  
**Pricing:** Free / Pro $29/mo / Team $99/mo  
**Enforcement Gates:** 1/6 passing  
**Current Status:** 🔴 No homepage. No auth. /savings must always stay public.

---

## Implementation Priority: #7 / 13

## Enforcement Gate Checklist

| Gate | Status |
|------|--------|
| Routing (Public/Protected/Admin classification) | ✅ |
| Auth (Login + Signup pages) | ❌ |
| Pricing (/pricing page with Stripe CTAs) | ❌ |
| Entitlements (PlanGate on premium features) | ❌ |
| Stripe Webhook | ✅ Registered May 29 2026 |
| Admin Safety (AuthGuard adminOnly) | ❌ |

---

## Protected Routes

- `/dashboard`
- `/explorer`
- `/reports`
- `/sessions`
- `/budgets`
- `/alerts`
- `/billing`

## Plan Gates

- `/router (pro)`
- `/guardrails (pro)`
- `/batch (pro)`
- `/unit-economics (team)`

---

## Backend Functions (all live)

| Function | Endpoint |
|----------|----------|
| Stripe Checkout | `POST https://superagent-b2d614b7.base44.app/functions/createStripeCheckout` |
| Billing Portal | `POST https://superagent-b2d614b7.base44.app/functions/createBillingPortal` |
| Usage Gate | `POST https://superagent-b2d614b7.base44.app/functions/checkUsageGate` |
| Export Gate | `POST https://superagent-b2d614b7.base44.app/functions/exportGate` |
| Audit Logger | `POST https://superagent-b2d614b7.base44.app/functions/auditLogger` |

---

## Universal Components Required

- `AuthGuard.jsx` — wraps all protected routes
- `PlanGate.jsx` — wraps premium features with upgrade prompt
- `BillingPortalButton.jsx` — opens Stripe customer self-serve portal

---

## QA Checklist

- [ ] Logged-out users cannot access protected routes (test in incognito)
- [ ] /login and /signup are separate with correct redirect behavior
- [ ] Public homepage shows marketing content — not dashboard UI
- [ ] /pricing page exists and is publicly accessible
- [ ] Pricing CTAs trigger createStripeCheckout correctly
- [ ] Premium features show upgrade prompt to free users
- [ ] Premium features blocked at logic layer (not just UI)
- [ ] Admin routes return 403 for non-admin authenticated users
- [ ] BillingPortalButton opens Stripe customer portal
- [ ] No demo/test data visible to real users
- [ ] Mobile layout (375px) — no overflow or broken elements

---

## Related Apps (Cross-sell)

All 13 apps: https://oneclickitonboarding.base44.app  
Book a demo: https://calendly.com/oneclickitllc

---

*Managed by RITAC Solutions · RITAC Command AI Agent · May 2026*
