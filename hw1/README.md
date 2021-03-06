# Homework 1

## Logistics
**Due: 9/7/2016, 11:59pm**

Data source: [Dropbox public link](https://dl.dropboxusercontent.com/u/258937/clinton_emails.sqlite)

## Setup
Before getting started, you will need to install [SQLite](https://www.sqlite.org/). If you use a package manager like [Homebrew](http://brew.sh/) or [apt-get](http://linux.die.net/man/8/apt-get) (which I highly recommend), the easiest way to install SQLite is `brew install sqlite` or `sudo apt-get install sqlite3`. Otherwise, see the [SQLite downloads page](https://www.sqlite.org/download.html). If you have an older version of SQLite on your system, please make sure you update to SQLite3 for consistency's sake.

Once you have SQLite3, you just need to type `sqlite3 clinton_emails.sqlite` in the directory with the `clinton_email.sqlite` file to open up the database with a SQLite shell. 

## Background
For those of you who don't know, Secretary of State Hillary Clinton [used a private email server](https://en.wikipedia.org/wiki/Hillary_Clinton_email_controversy) for official governmental business. An FBI investigation recently concluded that her behavior was "extremely careless" but decided not to pursue legal action against her. 

Your job is to investigate the damage that could have been done if a malicious hacker did in fact gain access to this poorly protected email server. We've loaded her emails as well as a few pieces of auxilliary information into a few SQLite tables for you to play around with.

## Getting Started
Before starting the assignment, you should spend a few minutes familiarizing yourself with the data. There are 4 tables that you will be writing queries on: `Emails`, `Persons`, `Aliases`, and `EmailReceivers`. For a more detailed description of the dataset including the fields in each table and their types, take a look at the [Kaggle description](https://www.kaggle.com/kaggle/hillary-clinton-emails) of the dataset or use the `.schema` utility below.

Keep in mind that SQLite has a number of useful utilities. For example, `.tables` will show you all the tables in your database, and `.schema {tablename}` will show you the schema of `{tablename}`.

## Your Assignment

There are 7 queries that you’re going to write for this assignment. **Write them in `hw1.sql` and submit.**

1. Find the number of emails that mention “Obama” in the `ExtractedBodyText` of the email.
2. Find the average number of aliases each people in the `Persons` table has.
3. Find the `MetadataDateSent` on which the most emails were sent and the number of emails that were sent on that date. Note that that many emails do not have a date -- don’t include those in your count.
4. Find out how many distinct `id`s refer to Hillary Clinton.
	- Hint: You might want to create a view with the ids of her aliases for future queries. See [this tutorial](http://www.tutorialspoint.com/sqlite/sqlite_views.htm). Make sure to include her actual `personId`!
5. Find the number of emails in the database sent by Hillary Clinton. Keep in mind that there are multiple aliases (from the previous question) that the email could’ve been sent from.
6. Find the names of the 5 people who emailed Hillary Clinton the most.
7. Find the names of the 5 people that Hillary Clinton emailed the most.

