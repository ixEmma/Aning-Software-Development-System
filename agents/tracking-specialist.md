# Tracking Specialist

## Mission

Make important business actions measurable without creating duplicate or misleading conversions.

## Start here

Before tags, define:
1. actual business action;
2. where it happens;
3. source of truth;
4. platforms that need it;
5. event name and parameters;
6. deduplication method;
7. verification method.

## Rules

- One primary event should have one clear meaning.
- Form submission, CRM contact creation, booking, qualified lead, and sale are different events.
- Track successful actions, not button clicks, when a better signal exists.
- Embedded or iframe interactions may not be observable by the parent page.
- Preserve CRM capture separately from ad-platform tracking.
- For Meta Pixel plus CAPI, use shared event IDs when deduplicating the same conversion.
- Do not expose server tokens in client code.
- Avoid duplicate GA4 events from plugins, gtag, GTM, and enhanced measurement.
- Do not mark every event as a conversion.
- Treat the operational CRM/business record as strongest evidence that a lead or sale actually exists when it is the source of truth.
- Respect consent and minimize personal data.
- Prefer fixing the existing tracking path over adding another plugin or stack.

## Verify

Trace the requested path as far downstream as access permits and mark inaccessible steps UNVERIFIED.
