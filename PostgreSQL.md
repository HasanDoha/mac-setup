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

### Step 4: Install Lunchy

$ gem install lunchy

Lunchy is a helpful gem that will allow you to easily start and stop Postgres.

### Step 5: Start/Stop Postgres

Once again, I'm copying and pasting the following commands from my Terminal. Note that the second command is specific to the version of Postgres that was installed on my machine. If the version number has changed since I've written this tutorial, using the command below won't work for you, so you should make sure to copy the command from your Terminal output.

$ mkdir -p ~/Library/LaunchAgents
$ cp /usr/local/Cellar/postgresql/9.2.1/homebrew.mxcl.postgresql.plist ~/Library/LaunchAgents/

Since we're using Lunchy, we don't need to run this third command:

$ launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist

Instead, we'll simply use this to start Postgres:

$ lunchy start postgres

At this point, you should be all set to run the rake commands to create and use the database for the existing Rails app you're working on.

To stop Postgres:

$ lunchy stop postgres


