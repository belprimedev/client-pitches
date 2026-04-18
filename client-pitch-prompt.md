# Client Pitch Automation Prompt

Copy and paste the following into Claude Code or Cowork when you want to pitch a new business.

---

## The Prompt

```
You are my client pitch automation system. I will give you a business name and their website URL. Your job is to execute this entire pipeline without asking me questions:

## CONTEXT
- My name: Shane Bell
- My website: shanebell.dev
- My email: shane@shanebell.dev (or check Gmail profile)
- My phone: 07565 727032
- My location: Luton, UK
- Pitches repo (local): /Users/shanebell/Documents/Claude/chat/client-pitches
- Pitches repo (remote): git@github.com:Outdreamer19/client-pitches.git
- Vercel project: connected to the above repo, auto-deploys on push

## PIPELINE (execute in order)

### 1. RESEARCH
- Fetch the target business's website
- Extract: business name, services, phone, email, address, branding colours, logo URL, certifications, any images worth reusing
- Identify 2-3 specific weaknesses in their current site (slow, outdated design, poor mobile UX, no clear CTA, bad image quality, missing trust signals, etc.)

### 2. BUILD THE REDESIGN
- Create a single index.html file: fully self-contained, no external dependencies except Google Fonts
- Design direction: modern, premium, scroll-triggered animations using Intersection Observer, responsive, dark/light mode toggle
- Use THEIR branding: logo, colours, real content from their site
- Include sections: hero with CTA, services, about, trust signals/accreditations, contact form, footer
- Add "Designed by Shane Bell" with link to shanebell.dev in footer
- Save to: /Users/shanebell/Documents/Claude/chat/client-pitches/[business-name-slug]/index.html

### 3. DEPLOY
- cd /Users/shanebell/Documents/Claude/chat/client-pitches
- git add .
- git commit -m "Add pitch: [Business Name]"
- git push origin main
- Wait 30 seconds for Vercel to deploy
- The live URL will be: https://client-pitches.vercel.app/[business-name-slug]/

### 4. DRAFT THE EMAIL
- Use the Gmail MCP tool to create a draft email to the business
- Use this HTML email template:

<div style="font-family:'Helvetica Neue',Arial,sans-serif;max-width:600px;margin:0 auto;background:#ffffff;">
<div style="padding:32px 40px;border-bottom:3px solid [BRAND_COLOUR];">
  <img src="[THEIR_LOGO_URL]" alt="[BUSINESS_NAME]" style="height:36px;width:auto;">
</div>
<div style="padding:40px;">
  <p style="font-size:16px;color:#1A1A1A;line-height:1.7;margin:0 0 20px;">Hi there,</p>
  <p style="font-size:16px;color:#1A1A1A;line-height:1.7;margin:0 0 20px;">I came across [BUSINESS_NAME] in a local group and had a look at your website. Great business, strong credentials. I think your site could do a better job of reflecting that.</p>
  <p style="font-size:16px;color:#1A1A1A;line-height:1.7;margin:0 0 28px;">I'm a web developer based in Luton and I put together a free redesign concept for you. No catch, just wanted to show you what's possible:</p>
  <div style="text-align:center;margin:0 0 32px;">
    <a href="[LIVE_URL]" style="display:inline-block;padding:16px 40px;background:[BRAND_COLOUR];color:#ffffff;font-size:16px;font-weight:700;text-decoration:none;border-radius:999px;">View the Redesign →</a>
  </div>
  <p style="font-size:16px;color:#1A1A1A;line-height:1.7;margin:0 0 20px;">If you like what you see, I'd be happy to jump on a quick call. No obligation.</p>
  <p style="font-size:16px;color:#1A1A1A;line-height:1.7;margin:0;">Cheers,<br><strong>Shane Bell</strong></p>
</div>
<div style="padding:24px 40px;background:#F9F9F8;border-top:1px solid #eee;">
  <p style="font-size:13px;color:#888;margin:0 0 4px;">Shane Bell · Web Developer · Luton, UK</p>
  <p style="font-size:13px;margin:0;">
    <a href="https://shanebell.dev" style="color:[BRAND_COLOUR];text-decoration:none;font-weight:500;">shanebell.dev</a>&nbsp;&nbsp;·&nbsp;&nbsp;
    <a href="tel:07565727032" style="color:[BRAND_COLOUR];text-decoration:none;font-weight:500;">07565 727032</a>
  </p>
</div>
</div>

- Subject line: "I redesigned your website (no strings attached)"
- Content type: text/html
- Replace all placeholders with actual values

### 5. REPORT BACK
Tell me:
- The live URL
- The business email used
- 2-3 weaknesses you identified
- Confirm the Gmail draft is ready

## STYLE RULES
- Never use dashes in any written content
- No generic AI aesthetics (no Inter font, no purple gradients on white)
- Every redesign should feel custom, not templated
- Light theme default, dark mode toggle
- Scroll-triggered animations (Intersection Observer, not libraries)
- Animated stat counters where relevant
- Mobile responsive

## READY
Target business: [TELL ME THE BUSINESS NAME AND URL]
```

---

## Usage

Open Claude Code or Cowork and paste the prompt above. Then at the bottom, replace the last line with the actual business. For example:

```
Target business: Murray's Electrical - https://www.murrays-electrical.co.uk/
```

Claude will handle the rest: research, build, deploy, email draft. You just review the draft and hit send.
