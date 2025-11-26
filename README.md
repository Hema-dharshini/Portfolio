# Professional Portfolio Website

A clean, modern, and fully responsive portfolio website perfect for job applications and recruiters. Features dark/light mode, smooth animations, and a contact form with EmailJS integration.

## Features

- **Responsive Design**: Works seamlessly on mobile, tablet, and desktop
- **Dark/Light Mode**: Toggle between themes with user preference persistence
- **Modern UI**: Clean design with smooth animations and hover effects
- **Contact Form**: Integrated EmailJS for direct email delivery
- **Multiple Sections**: Home, About, Skills, Projects, Experience, Achievements, Resume, Contact
- **Easy to Customize**: Simple HTML structure with clear comments

## Project Structure

```
portfolio/
├── index.html          # Main homepage with all sections
├── style.css           # All styles including dark/light mode
├── script.js           # JavaScript for interactivity and EmailJS
├── assets/
│   ├── images/         # Profile and project images
│   │   ├── profile.jpg
│   │   └── project1-4.jpg
│   ├── icons/          # Custom icons (optional)
│   └── resume.pdf      # Your resume file
└── README.md           # This file
```

## How to Customize Your Portfolio

### 1. Personal Information

Edit `index.html` to update your personal details:

**Name and Title** (Lines 30-32):
```html
<h1 class="hero-title">Hi, I'm <span class="highlight">Your Name</span></h1>
<h2 class="hero-subtitle">Full Stack Developer & UI/UX Enthusiast</h2>
```

**Bio and Introduction** (Lines 33-37):
```html
<p class="hero-description">
    I craft beautiful, responsive web applications...
</p>
```

**Contact Information** (Search for "contact-details" section):
```html
<span>your.email@example.com</span>
<span>+1 (123) 456-7890</span>
<span>City, State, Country</span>
```

### 2. About Me Section

Update your bio, education, and career objective in the About section (starting around line 70):

```html
<p>
    I'm a software developer with a strong foundation...
</p>
```

**Education**:
```html
<p><strong>Bachelor of Science in Computer Science</strong></p>
<p>University Name, 2019-2023</p>
<p>GPA: 3.8/4.0</p>
```

### 3. Skills

Update your technical skills and proficiency levels (search for "skills" section):

```html
<div class="skill-item">
    <div class="skill-info">
        <span class="skill-name">JavaScript</span>
        <span class="skill-level">85%</span>
    </div>
    <div class="skill-bar">
        <div class="skill-progress" style="width: 85%"></div>
    </div>
</div>
```

Add or remove skills as needed. The percentage determines the progress bar width.

### 4. Projects

Add your projects in the Projects section (search for "projects-grid"):

```html
<div class="project-card">
    <div class="project-image">
        <img src="assets/images/project1.jpg" alt="Project 1">
    </div>
    <div class="project-content">
        <h3>Your Project Name</h3>
        <div class="project-tech">
            <span class="tech-tag">React</span>
            <span class="tech-tag">Node.js</span>
        </div>
        <p>Project description goes here...</p>
        <div class="project-links">
            <a href="YOUR_GITHUB_LINK" target="_blank" class="project-link">
                <i class="fab fa-github"></i> GitHub
            </a>
            <a href="YOUR_DEMO_LINK" target="_blank" class="project-link">
                <i class="fas fa-external-link-alt"></i> View Project
            </a>
        </div>
    </div>
</div>
```

### 5. Work Experience

Update the timeline section with your experience:

```html
<div class="timeline-item">
    <div class="timeline-dot"></div>
    <div class="timeline-content">
        <div class="timeline-date">Jan 2023 - Present</div>
        <h3>Job Title</h3>
        <h4>Company Name</h4>
        <p>Job description...</p>
        <ul>
            <li>Achievement or responsibility</li>
            <li>Another achievement</li>
        </ul>
    </div>
</div>
```

### 6. Achievements

Update achievements in the achievements section:

```html
<div class="achievement-card">
    <div class="achievement-icon">
        <i class="fas fa-trophy"></i>
    </div>
    <h3>Achievement Title</h3>
    <p>Achievement description</p>
    <span class="achievement-date">Date</span>
</div>
```

### 7. Images

Replace placeholder images:
- **Profile Photo**: Replace `assets/images/profile.jpg` with your photo (300x300px recommended)
- **Project Images**: Replace `assets/images/project1-4.jpg` with your project screenshots (400x300px recommended)

### 8. Resume

Replace `assets/resume.pdf` with your actual resume PDF file.

### 9. Social Media Links

Update your social media links throughout the HTML (search for "github.com/yourusername"):

```html
<a href="https://github.com/YOUR_USERNAME" target="_blank">
<a href="https://linkedin.com/in/YOUR_USERNAME" target="_blank">
<a href="https://twitter.com/YOUR_USERNAME" target="_blank">
```

## EmailJS Setup (Contact Form)

The contact form uses EmailJS to send emails directly from your portfolio.

### Step 1: Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account

### Step 2: Setup Email Service
1. Go to "Email Services" in your EmailJS dashboard
2. Add a new email service (Gmail, Outlook, etc.)
3. Follow the instructions to connect your email

### Step 3: Create Email Template
1. Go to "Email Templates"
2. Create a new template with these variables:
   - `{{from_name}}` - Sender's name
   - `{{from_email}}` - Sender's email
   - `{{subject}}` - Email subject
   - `{{message}}` - Email message

Example template:
```
New message from {{from_name}}

From: {{from_email}}
Subject: {{subject}}

Message:
{{message}}
```

### Step 4: Update JavaScript

In `script.js`, update these values (around line 93-94):

```javascript
emailjs.init('YOUR_EMAILJS_PUBLIC_KEY'); // Your Public Key

// In the send function:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
```

Find these values in your EmailJS dashboard:
- **Public Key**: Account > General
- **Service ID**: Email Services
- **Template ID**: Email Templates

## Customizing Colors and Theme

Edit `style.css` to change the color scheme (lines 1-15):

```css
:root {
    --primary-color: #6366f1;      /* Main brand color */
    --secondary-color: #8b5cf6;    /* Secondary brand color */
    --accent-color: #ec4899;       /* Accent color */
    /* ... */
}
```

## Hosting on Replit

Your portfolio is already set up to run on Replit!

1. **Run the Website**: Click the "Run" button at the top
2. **View Your Site**: The website will open in the webview panel
3. **Share**: Copy the URL from the webview to share your portfolio

### Publishing to the Web

To make your portfolio accessible to everyone:

1. Click the "Deploy" button in Replit
2. Choose "Static" deployment
3. Follow the prompts to publish
4. You'll get a public URL like `yourportfolio.repl.co`

### Custom Domain (Optional)

With Replit's paid plans, you can add a custom domain like `yourname.com`.

## Tips for Job Applications

1. **Keep it Updated**: Regularly update your projects and experience
2. **Quality Over Quantity**: Showcase your best 4-6 projects
3. **Proofread**: Check for typos and grammatical errors
4. **Test Contact Form**: Make sure EmailJS is configured correctly
5. **Mobile-Friendly**: Test on different devices
6. **Fast Loading**: Optimize images (use tools like TinyPNG)
7. **Professional Photo**: Use a clear, professional profile picture
8. **Active Links**: Ensure all GitHub and demo links work

## Browser Compatibility

Tested and works on:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Support

If you encounter any issues:
1. Check browser console for errors (F12)
2. Verify all file paths are correct
3. Ensure EmailJS credentials are properly configured
4. Test on different browsers

## License

Feel free to use this template for your personal portfolio. No attribution required.

---

**Good luck with your job search! 🚀**
