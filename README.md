# Essendon Accounting Landing Page - Maintenance Guide

This guide will help you maintain and customize the Essendon Accounting landing page. Whether you're new to web development or need a quick reference, follow these detailed instructions for common updates.

## Table of Contents
1. [Updating Text and Styling](#updating-text-and-styling)
2. [Managing Links](#managing-links)
3. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains the company name and navigation menu. To update:

1. **Company Name:**
```html
<a href="/" class="text-2xl font-bold text-white tracking-tight">
    Essendon<span class="text-blue-500">.</span>
</a>
```
- Replace "Essendon" with your company name
- The blue dot is styled with `text-blue-500` - adjust the color by changing the number (100-900)

### Hero Section
Located at the top of the page:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight mb-8">
    Essendon accounting services
</h1>
<p class="text-xl md:text-2xl text-gray-300 mb-12">
    Trusted advisors for your financial future
</p>
```
- Update the heading and subheading text as needed
- Text sizes use responsive classes:
  - `text-4xl`: Mobile devices
  - `md:text-5xl`: Medium screens
  - `lg:text-6xl`: Large screens

### Tailwind CSS Tips
- Color classes follow this pattern: `text-{color}-{shade}`
  - Example: `text-blue-500`, `text-gray-300`
- Spacing classes use this format: `m{side}-{size}` or `p{side}-{size}`
  - Example: `mb-8` (margin-bottom), `px-6` (padding left/right)
- Responsive prefixes: `sm:`, `md:`, `lg:`, `xl:`
  - Example: `md:grid-cols-3` applies on medium screens and up

## Managing Links

### Navigation Menu Links
Current navigation links are:
```html
<div class="hidden md:flex space-x-8">
    <a href="#services" class="text-gray-300 hover:text-white transition-colors duration-300">Services</a>
    <a href="#benefits" class="text-gray-300 hover:text-white transition-colors duration-300">Benefits</a>
    <a href="#contact" class="text-gray-300 hover:text-white transition-colors duration-300">Contact</a>
    <a href="https://theaccountants.com" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-2 rounded-lg">
        Get Started
    </a>
</div>
```

To update links:
1. Internal links (same page sections) use `#section-id`
2. External links need full URLs starting with `https://`
3. Replace `https://theaccountants.com` with your actual website URL

### Call-to-Action (CTA) Links
Located in multiple sections:
```html
<!-- Hero Section CTA -->
<a href="https://theaccountants.com" class="inline-block bg-blue-600 hover:bg-blue-700 text-white text-lg px-8 py-4 rounded-lg">
    Start Your Journey
</a>
```
- Update all instances of `https://theaccountants.com`
- Maintain consistent styling across CTAs

## Adding Privacy and Terms Pages

### Footer Link Updates
Locate the Legal section in the footer:
```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2 text-gray-400">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To link privacy and terms pages:
1. Create new files:
   - `privacy.html`
   - `terms.html`
2. Update the href attributes:
```html
<li><a href="privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues and Solutions

1. **Links Not Working**
   - Check for correct file paths
   - Ensure section IDs match exactly (case-sensitive)
   - Verify URLs start with `https://` for external links

2. **Responsive Design Issues**
   - Check responsive prefixes (`sm:`, `md:`, `lg:`)
   - Test on different screen sizes
   - Ensure the viewport meta tag is present:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

3. **Animation Problems**
   - Verify AOS script is loaded
   - Check data-aos attributes
   - Ensure AOS is initialized:
```html
<script>
    AOS.init({
        duration: 1000,
        once: true
    });
</script>
```

### Need Help?
- Review the [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Check the [AOS Animation library](https://michalsnik.github.io/aos/)
- Validate HTML at [W3C Validator](https://validator.w3.org/)

Remember to always test changes across different devices and browsers before deploying to production.