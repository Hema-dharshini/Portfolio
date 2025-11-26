# Portfolio Website

## Overview

This is a modern, responsive personal portfolio website designed for job applications and professional presentation. The project is a single-page application built with vanilla HTML, CSS, and JavaScript, featuring a clean UI with dark/light theme toggling, smooth scrolling navigation, and an integrated contact form using EmailJS for direct email delivery.

The portfolio includes multiple sections: Home/Hero, About, Skills, Projects, Experience, Achievements, Resume, and Contact. The design emphasizes simplicity, accessibility, and ease of customization for non-technical users.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Single-Page Application (SPA) Design**
- All content is contained within a single HTML file (`index.html`) with anchor-based navigation
- Sections are loaded simultaneously and accessed via smooth scrolling
- **Rationale**: Simplicity and ease of deployment; no build process or routing complexity required
- **Pros**: Fast initial load, simple hosting, easy to customize
- **Cons**: Entire page must load upfront; not ideal for very large portfolios

**CSS Architecture**
- Custom CSS variables for theming (CSS custom properties in `:root`)
- Dark/light mode implemented via `data-theme` attribute on document root
- Mobile-first responsive design with breakpoints
- **Rationale**: Native CSS features eliminate need for preprocessors or CSS-in-JS libraries
- **Pros**: No build step, excellent browser support, performant
- **Cons**: More verbose than preprocessors like SASS

**JavaScript Architecture**
- Vanilla JavaScript with no frameworks
- Event-driven interaction model (DOM event listeners)
- LocalStorage for theme persistence
- **Rationale**: Minimal dependencies, fast page loads, easy maintenance
- **Pros**: No framework overhead, simple debugging, universal compatibility
- **Cons**: More verbose code compared to frameworks like React

### Theme System

**Client-Side Theme Management**
- Theme state stored in `localStorage` with key `'theme'`
- Default theme: 'light'
- Theme applied via `data-theme` attribute on `<html>` element
- CSS variables automatically respond to theme changes
- **Rationale**: Persists user preference across sessions without server
- **Pros**: Instant theme switching, no server required, privacy-friendly
- **Cons**: Not synchronized across devices

### Navigation System

**Fixed Navigation with Smooth Scrolling**
- Fixed position navbar that remains visible during scroll
- Active link highlighting based on scroll position
- Mobile hamburger menu for responsive design
- Hash-based anchor navigation (`#home`, `#about`, etc.)
- **Rationale**: Simple implementation without routing libraries
- **Pros**: Works without JavaScript (fallback), SEO-friendly
- **Cons**: Limited to single-page navigation

### Form Handling

**EmailJS Integration**
- Contact form submissions sent directly via EmailJS API
- Client-side form validation
- Status messages displayed inline
- **Rationale**: No backend server required for email functionality
- **Pros**: Free tier available, simple setup, no server maintenance
- **Cons**: API keys visible in client code, rate limiting, requires external service
- **Alternative considered**: Backend server with nodemailer - rejected for simplicity

## External Dependencies

### Third-Party Libraries

**Font Awesome 6.4.0**
- CDN: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
- Purpose: Icons for navigation, social links, and UI elements
- **Integration**: Loaded via CDN in HTML `<head>`

**Google Fonts (Inter)**
- CDN: `https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap`
- Purpose: Primary typography
- **Integration**: Preconnected and loaded via CDN in HTML `<head>`

### Email Service

**EmailJS**
- Purpose: Contact form email delivery without backend server
- **Integration**: JavaScript SDK (likely loaded in complete version of `script.js`)
- **Configuration**: Requires EmailJS account with Service ID, Template ID, and Public Key
- **Note**: Credentials must be configured by user in `script.js`

### Asset Management

**Static Assets**
- Images stored in `/assets/images/` directory
- Resume PDF stored in `/assets/` directory
- Optional custom icons in `/assets/icons/`
- **Hosting**: All assets served statically alongside HTML/CSS/JS files

### Browser APIs

**LocalStorage API**
- Purpose: Theme preference persistence
- **Fallback**: Defaults to 'light' theme if unavailable

**DOM APIs**
- Standard DOM manipulation and event handling
- Smooth scroll behavior via CSS `scroll-behavior` or JavaScript

### Deployment Considerations

- No build process required
- Can be hosted on any static hosting service (GitHub Pages, Netlify, Vercel, etc.)
- No database or server-side processing
- EmailJS requires account setup and API configuration before contact form works