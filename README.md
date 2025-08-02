# Automated Birthday Wisher

An automated Python script that sends personalized birthday emails to friends and family. The program checks for birthdays daily and sends customized birthday messages using random letter templates.

## Features

- **Automated Birthday Detection**: Checks current date against birthday database
- **Personalized Messages**: Uses random letter templates with name personalization
- **Email Integration**: Automatically sends emails via Gmail SMTP
- **CSV Database**: Easy-to-manage birthday database in CSV format
- **Multiple Templates**: Randomly selects from multiple birthday letter templates
- **Secure Email**: Uses Gmail's secure SMTP connection with TLS encryption

## How It Works

1. **Daily Check**: Script compares today's date (month/day) with birthday database
2. **Template Selection**: Randomly chooses one of three birthday letter templates
3. **Personalization**: Replaces `[NAME]` placeholder with the person's actual name
4. **Email Delivery**: Sends personalized birthday email via Gmail

## Requirements

- Python 3.x
- pandas (`pip install pandas`)
- Gmail account with App Password enabled

## Project Structure

```
birthday-wisher/
│
├── main.py                    # Main script
├── birthdays.csv             # Birthday database
└── letter_templates/         # Birthday message templates
    ├── letter_1.txt
    ├── letter_2.txt
    └── letter_3.txt
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/birthday-wisher.git
```

2. Install required dependencies:
```bash
pip install pandas
```

3. Set up Gmail App Password:
   - Go to Google Account settings
   - Enable 2-Factor Authentication
   - Generate an App Password for this application

## Setup

### 1. Configure Email Credentials
Edit the script and update your email credentials:
```python
MY_EMAIL = "your_email@gmail.com"
MY_PASSWORD = "your_app_password"  # Use Gmail App Password
```

### 2. Create Birthday Database
Create `birthdays.csv` with the following format:
```csv
name,email,year,month,day
John Doe,john@example.com,1990,5,15
Jane Smith,jane@example.com,1985,12,25
```

### 3. Create Letter Templates
Create 3 letter templates in `letter_templates/` folder:
- `letter_1.txt`
- `letter_2.txt` 
- `letter_3.txt`

Each template should include `[NAME]` placeholder:
```
Dear [NAME],

Happy Birthday! 🎉

Hope you have a wonderful day!

Best wishes,
Your Friend
```

## Usage

### Manual Run
```bash
python main.py
```

### Automated Daily Run
Set up a cron job (Linux/Mac) or Task Scheduler (Windows) to run daily:

**Linux/Mac Cron:**
```bash
# Run daily at 9:00 AM
0 9 * * * /usr/bin/python3 /path/to/birthday-wisher/main.py
```

**Windows Task Scheduler:**
Create a daily task that runs the Python script.

## Security Notes

- **Never commit passwords**: Use environment variables or config files (add to .gitignore)
- **Use App Passwords**: Don't use your main Gmail password
- **Keep CSV private**: Birthday data contains personal information

## Example Environment Setup

Create a `.env` file (add to .gitignore):
```
EMAIL=your_email@gmail.com
PASSWORD=your_app_password
```

Then modify the script:
```python
import os
from dotenv import load_dotenv

load_dotenv()
MY_EMAIL = os.getenv('EMAIL')
MY_PASSWORD = os.getenv('PASSWORD')
```

## Troubleshooting

- **Authentication Error**: Make sure to use Gmail App Password, not regular password
- **CSV Error**: Check CSV format and file path
- **Template Error**: Ensure letter templates exist and contain `[NAME]` placeholder
- **SMTP Error**: Verify Gmail SMTP settings and internet connection

## Future Enhancements

- [ ] Support for multiple email providers
- [ ] Web interface for managing birthdays
- [ ] Time zone support
- [ ] HTML email templates
- [ ] Reminder notifications before birthdays
- [ ] Birthday card attachments
- [ ] Database encryption

## Contributing

Feel free to fork this project and submit pull requests for improvements.

## Disclaimer

This tool is for personal use. Ensure you have permission before sending automated emails to contacts.
