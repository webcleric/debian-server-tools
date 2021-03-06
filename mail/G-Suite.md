# Set up a domain for G Suite

1. Register domain, see [onboarding](/Onboarding.md)
1. Clean up DNS records
1. [Add domain](https://admin.google.com/AdminHome#Domains:)
1. Add TXT record `.`
   - `"google-site-verification=..."`
   - `"v=spf1 include:_spf.google.com -all"`
1. Add MX record `.`
   - `1 ASPMX.L.GOOGLE.COM.`
   - `5 ALT1.ASPMX.L.GOOGLE.COM.`
   - `5 ALT2.ASPMX.L.GOOGLE.COM.`
   - `10 ALT3.ASPMX.L.GOOGLE.COM.`
   - `10 ALT4.ASPMX.L.GOOGLE.COM.`
1. [Enable mailing](https://admin.google.com/AdminHome#Domains:)
1. [Generate DKIM record](https://admin.google.com/AdminHome#AppDetails:service=email&flyout=authenticate_email)
   1024 bit
1. Add generated TXT record `google._domainkey.`
1. Add report-only DKIM record `_dmarc.`
   - `"v=DMARC1; p=none; rua=mailto:webmaster@agrya.hu"`
1. Use G Suite Toolbox Check MX service  
   `https://toolbox.googleapps.com/apps/checkmx/check?dkim_selector=google&domain=EXAMPLE.COM`
