---
aliases: /article/5038-postgres-databases-on-request
description: Postgres databases on request
slug: postgres-databases-on-request
title: Postgres databases on request
---

## Introduction

This article explains that users may request access to a PostgreSQL (known as
Postgres) database on JASMIN for use with scientific workflows.

## Overview of the user database service

There are a large number of different workflows on JASMIN and it is common for
users to require access to _persistent storage_ of information about the progress of a workflow.
In some cases, it is
appropriate for users to save information in a relational database. Examples
might be to create/update/delete data records (when working with _small_
results) or to store the success/failure of batch tasks (running on LOTUS).

To meet this need, a _user database service_ is available on request. The
service provides secured access to a [Postgres](https://www.postgresql.org/)
database that is accessible from the interactive and batch compute nodes on
JASMIN. An individual user, or group of users, can be issued with login
credentials to enable read and/or write access to the database.

## How to request a Postgres database for use on JASMIN

In order to request a Postgres database from the user database service, please
ensure you have a JASMIN Login account and then send a message to the JASMIN
Helpdesk. You should include the following information in your message:

- state that you would like a user database set up
- your JASMIN user ID
- Postgres details: database name, database user account name
- the expected size of the database (fully populated)
- machines (inside JASMIN) from which you would like to contact the database
- If you require backups of the database to be made.

## Postgres extensions

The Postgres installation includes the following extension:

- {{<link "https://postgis.net/">}}PostGIS{{</link>}}

## Backups

By default we make daily backups of the databases, which are kept for a week.
We keep a weekly backup for a month and a monthly backup for 6 months. These
intervals may be subject to change, so if you have particular concerns about
backups please let us know. If your database is particularly large we may
either make less frequent backups or not make backups at all. We will discuss
any particular backup requirements you may have when we set up your database.

You should contact the JASMIN Helpdesk to request access
to previous backups.

## Restrictions and limitations

Please note that the following restrictions and limitations apply to the user
database service:

- We cannot provide training in SQL or the use of relational databases: please ensure that you have the appropriate experience before requesting access.
- There is a size limit on the server and the disk that the user databases are housed on: if you expect to store many GBs of data then please discuss this with the JASMIN Team.
- The database cannot be made accessible outside the JASMIN firewall: it is intended to support applications and workflows that take place inside JASMIN.
- The database should not be considered as a long-term data store: you should migrate any content elsewhere if you intend to keep it for the medium or long term.
