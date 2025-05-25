# Domain Setup and Deployment with Cloudflare
This documentation will guide you through the steps required to buy a domain, set it up with Cloudflare, and deploy a website using Cloudflare Workers and Pages.
Prerequisites
* A domain provider account (e.g., Namecheap, GoDaddy, etc.)
* A Cloudflare account
* A GitHub account with your website code repository

## Steps
### 1. Buy a Domain
* Go to a domain provider of your choice (e.g., Namecheap, GoDaddy, etc.).
* Search for the domain name you want to purchase (e.g., website.com).
* Purchase the domain and make sure you have access to the domain management console.
  
### 2. Add Your Domain to Cloudflare
* Log in to your Cloudflare account at https://cloudflare.com.
* Once logged in, go to the Dashboard and click on Add a Site.
* Enter your domain name (e.g., website.com) and click Add Site.
* Cloudflare will automatically scan your domain’s DNS records. Click Next to proceed.

### 3. Change the Nameservers at Your Domain Provider
* Cloudflare will provide you with two new nameservers (e.g., nancy.ns.cloudflare.com and dave.ns.cloudflare.com).
* Go to your domain provider’s website and log in to your account.
* In the domain management section, find the option to update nameservers.
* Replace your existing nameservers with the ones provided by Cloudflare.
* Save the changes. This may take some time (up to 24 hours) to propagate across the internet.

### 4. Create a New Cloudflare Page
* In your Cloudflare dashboard, navigate to the Workers section.
* Select Pages from the left sidebar and click Create a Project.
* Choose GitHub as the source for your project.

### 5. Select Your GitHub Repository and Deploy
* You will be prompted to connect your GitHub account to Cloudflare if you haven’t already.
* Once connected, select the repository that contains your website code.
* Follow the instructions to deploy the project. Cloudflare will automatically detect the build settings for common static site generators (e.g., Gatsby, Hugo, Jekyll).
* Click Deploy and Cloudflare will build and deploy your site.

### 6. Add Your Custom Domain
* After the build is successful, navigate to the Pages dashboard.
* Under Custom Domains, click on Add a Custom Domain.
* Enter your desired domain (e.g., [website.com](https://leedlime.com/?ref=GitHub)).
* Click Add Domain to link your domain to the deployed site.

### 7. Add Both Root Domain and Subdomain (www)
* To ensure your site is accessible via both website.com and [www.website.com](https://leedlime.com/?ref=GitHub), repeat the process and add both of these as custom domains.
    * Add website.com and [www.website.com](https://leedlime.com/?ref=GitHub) to Cloudflare Pages.

### 8. Update DNS Records
* Go to the DNS section in your Cloudflare dashboard.
* Ensure there are two CNAME records:
    * One for website.com pointing to your Cloudflare Pages URL (e.g., your-site.pages.dev).
    * One for [www.website.com](https://leedlime.com/?ref=GitHub) pointing to the same Cloudflare Pages URL.
* Example:
    * CNAME for website.com → your-site.pages.dev
    * CNAME for [www.website.com](https://leedlime.com/?ref=GitHub) → your-site.pages.dev
Cloudflare will automatically handle the DNS configuration, but make sure the records are set up correctly.

### 9. Wait for DNS Propagation
* DNS changes can take some time to propagate. It may take anywhere from a few minutes to 24 hours for the changes to be fully applied.

### 10. Verify Your Website
* After the DNS changes have propagated, visit both website.com and [www.website.com](https://leedlime.com/?ref=GitHub) in your browser.
* Your site should now be accessible via both domains!

## Troubleshooting Tips
* DNS Propagation Issues: If your site doesn’t show up immediately, wait for a few hours as DNS changes may take time to propagate across the internet.
* Incorrect CNAME Records: Double-check the DNS settings in Cloudflare to ensure both [website.com](https://leedlime.com/?ref=GitHub) and [www.website.com](https://leedlime.com/?ref=GitHub) are pointing to the correct Cloudflare Pages URL.
* GitHub Deployment Issues: If your site isn’t deploying correctly, check the build logs in Cloudflare Pages for errors or missing dependencies.

## Conclusion
You’ve successfully set up your domain with Cloudflare and deployed your website. Your site should now be live and accessible from both [website.com](https://leedlime.com/?ref=GitHub) and [www.website.com](https://leedlime.com/?ref=GitHub).

I wrote this guide based on my experience setting up domains for [leedlime.com](https://leedlime.com/?ref=GitHub) [excelaibot.pro](https://www.excelaibot.pro) and a few more websites.
