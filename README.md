# Welcome to the page.
# Blacklist_Check_DB

Scan Public IP addresses to find what is blacklisted.


The following file I had in my /home/scripts/rbl/

You can decide if you want it in another directory but remember to make note of where you have it if you add it to the crontab.

Here you get the following;

1. check-rbl.sh
2. list.db
3. query.php

The requirement to make this script run the way it needs to is
 that you must have the following.

-- PHP

-- MAILX

-- Active Internet connection to server.


Remember to edit the CHECK-RBL.sh first.
You must change to from and to email address in the script.
Change the permissions of the following files
    I just use chmod 755 check-rbl.sh

To add it to your daily check you can add it to the crontab to run daily.
the line I have added is the following ( nano /etc/crontab )

Blacklist Check

0 5 * * * root /home/scripts/rbl/check-rbl.sh > /dev/null 2>&1

This will run at 5 o'clock in the morning and a good time for me to run.

# DB File

To edit the DB file I have found a free program link below

https://sqlitebrowser.org/dl/

In the DB you will find the following tables,
1. check_servers
2. rbl_servers

The software that i recomend has a import from csv file and makes it easy to use.

To add or remove the sites you don't want to use you can remove it in the rbl_servers
-- In this table, you will find 2 columns server_address and use.
-- leave the use black if you want the server to check on it.
-- Add or remove the server address you don't want to use.

-- To add or remove the IP addresses you want to monitor then you can add it to the check_servers

Remember to save the file as list.db

# Remember
Save all the files in the same directory so that the script can work.

This is also working on all linux servers.

