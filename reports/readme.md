## Things to note

- credential file 'ubcdata.json' in the reports directory

- ** only change the course_list in daily_reports.py OR course_list and corresponding prices in weekly_reports.py as needed **

- creates and updates
  - enroll_unenroll_verify.xlsx daily at 3 pm: number students enrolled, unenrolled and verified on the day
  - activity_lastweek.xlsx weekly on Monday at 3 pm: activity during the last week including number of students active, nevents, nvideo_viewed, nproblem_attempted, nforum_posts
  - register_verify_revenue_utd.xlsx weekly on Monday at 3 pm: up-to-date (last Sunday) information about total number of students registered and verified, % students verified and revenue up-to-date

- schedule: crontab -e
~~~
0 15 * * 1 source /Users/katrinani/.bash_profile; /Users/katrinani/Documents/CTLT/analysis/reports/weekly.sh
0 15 * * * source /Users/katrinani/.bash_profile; /Users/katrinani/Documents/CTLT/analysis/reports/daily.sh
~~~
- python 2.x
- libraries: pandas, BeautifulSoup, json, urllib, datetime, re, openpyxl, os, httplib2, apiclient, oauth2client, base64, email. Recommend to install [Anaconda](https://www.continuum.io/downloads)
