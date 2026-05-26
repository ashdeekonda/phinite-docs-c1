## Phinite Email Templates

These are production‑ready, responsive HTML email templates built with table layouts, inlined styles, and Outlook/VML‑safe buttons. They are designed to work across major clients (Gmail, Apple Mail, Outlook desktop/web, Yahoo, iOS/Android mail apps).

### Files
- `templates/welcome-verify.html`
- `templates/password-reset.html`
- `templates/invite.html`
- `templates/magic-link.html`
- `templates/email-change.html`
- `templates/login-alert.html`

### How to use
Render the HTML and replace template variables with your own values server‑side before sending.

#### Common variables
- `{{subject}}`: Email subject line.
- `{{preheader}}`: Short preview text shown in inboxes.
- `{{app_name}}`: Brand/app display name (e.g., "Phinite").
- `{{company_name}}`: Company/legal footer (e.g., "Phinite AI Inc.").
- `{{brand_color}}`: Primary color for buttons/links (e.g., `#7C3AED`). Defaults should be replaced server-side.
- `{{logo_url}}`: Absolute URL to the logo image.
- `{{support_email}}`: Support contact email.
- `{{year}}`: Current year for footer.

#### Action‑specific variables
- `{{action_url}}`: Primary CTA link (verify/reset/sign‑in/etc.).
- `{{action_text}}`: Button text (e.g., "Verify Email address").
- `{{user_email}}`: The recipient's email address.
- `{{user_name}}`: Optional friendly name of the recipient.
- `{{expires_in}}`: Human‑readable time window (e.g., "48 hours", "30 minutes").
- `{{workspace_name}}`: For invitations.
- `{{ip_address}}`, `{{location}}`, `{{user_agent}}`: For security alerts if available.

### Notes
- All templates include:
  - Accessible structure with semantic roles and alt text.
  - A preheader block that is visually hidden but readable by clients.
  - Bulletproof VML buttons for Outlook with matching HTML fallbacks.
  - Light/Dark mode friendly colors (best-effort; client support varies).
  - A plain‑link fallback under the primary CTA for clients that block buttons.
- Replace `{{logo_url}}` with the final asset URL you provide (CDN recommended).
- Keep links absolute (with scheme and hostname) for maximum deliverability.
- If you add tracking parameters, ensure they are URL‑encoded.

### Testing
- Test with Litmus or Email on Acid across clients.
- Manually test on:
  - Outlook Desktop (Windows), Outlook Web, Apple Mail (macOS/iOS), Gmail (Web/Android/iOS), Yahoo.
- Keep line length reasonable and avoid external CSS files.


