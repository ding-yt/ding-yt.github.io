---
layout: post
title:  scheduled email with automator on Mac
date: 2017-10-09
desc:  scheduled email with automator on Mac
keywords: "blog"
categories: 
tags: 
icon: icon-html
---

# scheduled email with automator on Mac

Just learned how to use automator. Looks like it can help a lot once you know how to use it. It can build some automatic pipeline with pre-defined actions. These actions have input/output which can be linked together to create a series of events. The first thing I used it for is to send email on specific time. Set up the pipeline: 

  1. open automator and create a new application
  2. you have tons of actions that you can choose from. For me, I want Mail -> New Mail Message. So I drag it to workflow window.
  3. attachment: I also want to attach some files to the email. So I find the file I want to attach in finder and drag them to the workflow window as well. But put them before the New Mail Message action. This way, the selected file will be an input to New Mail Message. If you read the description of New Mail Message, it accepts input files and make it attachment of email.
  4. Then I added Send Outgoing Messages after New Mail Message (may be skipped because New mail Message seen to send email as result, but not sure)
  5. Save the pipeline as application. Now if you double click this application, it will grab the file, attach it to email and send the email.
  Schedule it: 
  1. But I want to send it on specific time. The easiest way to do it is use your calendar to create an event, then set the alert to open a file, which is the automator application created before.
  2. However, for me, there is something wrong with the calendar and it won't open the application. So I used another command line app: crontab. It can execute certain commands at the time you specified.
![Screen Shot 2017-10-09 at 12.02.55 PM](https://safariding.files.wordpress.com/2017/10/screen-shot-2017-10-09-at-12-02-55-pm.png)$crontab -e Then enter time time time time time automator /path/testmail.app/Contents/document.wflow Now it will send the email on specific time.
