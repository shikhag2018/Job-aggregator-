# Job Aggregator

A powerful Python application to aggregate job listings from multiple portals and help you manage your job hunting process efficiently.

## 🎯 Features

✨ **Multi-Portal Support**
- GitHub Jobs (free, no API key needed)
- Indeed (via RapidAPI)
- Naukri.com support
- Easily extensible for more portals

🔍 **Smart Filtering**
- Filter by job title, location, salary range
- Include/exclude keywords
- Auto-ranking by relevance

📊 **Application Tracking**
- SQLite database to track all jobs
- Mark jobs as applied, rejected, or unapplied
- View statistics and response rates

📧 **Email Notifications** (Optional)
- Get daily job digest emails
- Automated summary reports
- Gmail integration

🤖 **Automation**
- Background scheduler for periodic searches
- Configurable search intervals
- Run hands-free job hunting

📋 **Interactive Dashboard**
- Easy-to-use menu system
- View job details
- Search job history
- Track your progress

---

## 🚀 Quick Start

### 1. **Prerequisites**
- Python 3.7+
- pip (Python package manager)

### 2. **Installation**

```bash
# Clone the repository
git clone https://github.com/yourusername/job-aggregator.git
cd job-aggregator

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 3. **Configuration**

```bash
# Copy example config to .env
cp .env.example .env

# Edit .env with your preferences
# At minimum, set:
# - JOB_TITLES
# - LOCATIONS
# - Optional: API keys, email settings
```

### 4. **Run the Application**

**Interactive Mode:**
```bash
python main.py
```

**Automated Background Mode:**
```bash
python scheduler.py
```

---

## ⚙️ Configuration Guide

### Search Criteria

```env
# Job titles to search for (comma-separated)
JOB_TITLES=Python Developer,Software Engineer,Backend Developer

# Locations (comma-separated)
LOCATIONS=Remote,Bangalore,Delhi

# Salary range
MIN_SALARY=0
MAX_SALARY=9999999

# Include/exclude keywords
INCLUDE_KEYWORDS=Python,FastAPI,Remote
EXCLUDE_KEYWORDS=Fresher,Intern
```

### Email Setup (Optional)

Gmail requires an **App Password** instead of your regular password:

1. Enable 2-Factor Authentication on your Gmail account
2. Go to: https://myaccount.google.com/apppasswords
3. Generate an app-specific password
4. Add to `.env`:

```env
ENABLE_EMAIL=True
EMAIL_SENDER=your-gmail@gmail.com
EMAIL_PASSWORD=your-app-password
EMAIL_RECIPIENT=your-email@gmail.com
```

### Indeed Integration (Optional)

1. Sign up for free RapidAPI account: https://rapidapi.com
2. Subscribe to Indeed API (free tier available)
3. Get your API key and add to `.env`:

```env
RAPIDAPI_KEY=your-api-key-here
```

---

## 📖 Usage Guide

### Interactive Menu Options

```
1. 🔍 Search for new jobs      - Search across all configured sources
2. 📋 View all jobs            - See all jobs in database
3. 📌 View unapplied jobs      - See jobs not yet applied to
4. ✅ Mark job as applied      - Track your applications
5. ❌ Mark job as rejected     - Filter out unwanted jobs
6. 📊 View statistics          - See your job hunting progress
7. ⚙️  View configuration      - Check current settings
8. 🔎 Search jobs (keyword)    - Search job history
9. 📧 Send job digest via email- Email new jobs
0. 🚪 Exit                     - Close application
```

### Examples

**Search for jobs:**
```bash
$ python main.py
# Select option 1 to search
```

**View statistics:**
```bash
$ python main.py
# Select option 6 to see stats
# Total Jobs Found: 45
# Applied: 12
# Response Rate: 26.7%
```

**Automated mode:**
```bash
$ python scheduler.py
# Runs searches every N hours (configured in .env)
# Sends email digests automatically (if enabled)
```

---

## 📁 Project Structure

```
job-aggregator/
├── main.py                 # Interactive application
├── scheduler.py            # Background automation
├── config.py              # Configuration management
├── database.py            # Database operations
├── job_filter.py          # Filtering and ranking
├── notifier.py            # Email notifications
├── sources/
│   ├── __init__.py
│   └── job_sources.py     # Job portal sources
├── requirements.txt       # Python dependencies
├── .env.example          # Configuration template
├── .gitignore           # Git ignore rules
├── jobs.db              # SQLite database (auto-created)
└── README.md            # This file
```

---

## 💡 Tips & Tricks

### Optimize Your Search

1. **Be specific with job titles** - "Python Developer" gets better results than just "Developer"
2. **Include remote** if willing - Adds many more opportunities
3. **Use keywords wisely** - Filter for technologies you know or want to learn
4. **Set salary range** - Focus on roles matching your expectations

### Maximize Response Rate

1. **Quick applications** - Apply within hours of job posting
2. **Track everything** - Use the app to manage all applications
3. **Follow up** - Monitor response patterns
4. **Quality over quantity** - Apply to 10 great jobs vs 100 random ones

### Best Practices

- Run scheduler during off-hours (late night or early morning)
- Set scheduler interval to 6-12 hours (avoids rate limiting)
- Review applications weekly and adjust criteria
- Enable email for early access to new jobs

---

## 🔧 Troubleshooting

### No jobs found
- Check your `.env` configuration
- Try broader search terms (e.g., "Developer" vs "Senior Python Developer")
- Verify internet connection

### Email not sending
- Enable 2FA on Gmail account
- Generate App Password (not regular password)
- Check EMAIL_SENDER and EMAIL_PASSWORD in .env
- Verify recipient email is correct

### Scheduler not running
- Keep terminal/command window open while running
- Check SCHEDULER_INTERVAL value (must be > 0)
- Review logs for errors

### Rate limiting errors
- Increase scheduler interval (set to 12 hours instead of 6)
- Reduce number of JOB_TITLES or LOCATIONS
- Add delays between API calls

---

## 🛡️ Important Notes

⚠️ **Terms of Service**
- Always respect job portal ToS
- GitHub Jobs: Open for scraping
- Indeed/Naukri: Use official APIs when available
- Don't overload servers with requests

✅ **Best Practices**
- Use appropriate rate limiting (6-12 hour intervals)
- Include meaningful User-Agent headers
- Don't bypass authentication systems
- Respect robots.txt files

---

## 🚀 Future Enhancements

- [ ] Web dashboard UI
- [ ] LinkedIn Jobs integration
- [ ] Cover letter templates
- [ ] Interview prep reminders
- [ ] Salary negotiation tracker
- [ ] Advanced analytics
- [ ] Browser extension
- [ ] Mobile app

---

## 📝 License

This project is open source and available under the MIT License.

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

---

## 💬 Support

For issues, questions, or suggestions:
- Open an GitHub issue
- Check existing documentation
- Review configuration examples

---

## 🙏 Acknowledgments

Built with ❤️ to help job seekers find their next opportunity!

Happy job hunting! 🎯
