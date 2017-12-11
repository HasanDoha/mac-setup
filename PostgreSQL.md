### Step 1: Update Homebrew

Before you install anything with Homebrew, you should always make sure it's up to date and that it's healthy:

$ brew update
$ brew doctor

### Step 2: Install Postgres

$ brew install postgresql

When you install Postgres, you will see a bunch of output in your Terminal. The important sections are Build Notes, Create/Upgrade a Database, and Start/Stop PostgreSQL. Make sure to follow those instructions to the letter.

### Step 3: Create/Upgrade a database

If this is your first time installing Postgres with Homebrew, you'll need to create a database with:

$ initdb /usr/local/var/postgres -E utf8

I copied and pasted that command directly from the Terminal output. You should do the same, in case the instructions change in the future.

### Step 4: Start/Stop Postgres

#### Start manually:
```
$ pg_ctl -D /usr/local/var/postgres start
```
#### Stop manually:
```
$ pg_ctl -D /usr/local/var/postgres stop
```
#### Start automatically:

"To have launchd start postgresql now and restart at login:"
```
$ brew services start postgresql
```

