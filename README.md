This Guide Provides You step by steps details on How to Run Ballsdex DiscordBot By El Laggron on Your Mobile (Android Only) 

# Requirements 
## Minimum 3GB of mobile Ram 

## 1.5Gb of minimum storage 2GB+ (Recommended)  

## a chipset of minimum Mediatek p35/G22 or higher, Snapdragon 439/625 or higher, Exynos 860 or higher, Kirn 650 or higher the powerful the chip the better and smooth the bot runs 

If you match this Requirements Your Ready To Go 

# Step 1 Installing Termux, Proot and Alpine

Termux Is Our Main Tool Here Install the latest Version of Termux directly from Here https://f-droid.org/en/packages/com.termux/ 
Once installed Open the App once you have access to the Shell Run This ``pkg update && pkg upgrade`` 
It take 1-5 minutes depending one your mobile and Network Once it's Finished Run This ``pkg install proot-distro``  this install the proot a user space tool witch let's us run a lightweight Linux distro kinda like a light VM so we are going to run our Ballsdex Bot in that distro Once proot is installed Run this command ``proot-distro install alpine`` This will install Alpine Linux the most Lightweight Linux os Download will be completed on around 1-3 minutes once it's completed Run This 
``proot-distro login alpine`` 

This command will successfully Login You to alpine Linux now you should be getting a panel like this ``localhost:~#``  

Once inside the environment Run this ``apk update & apk upgrade`` Once it's finished 

First Step is completed it should be straightforward and easy but if you get a question feel free to create a issue on this github 

# Step 2 Installing and setting up Necessary Packages 

Now it's Time For us to install the Necessary packages

Run this commands one by one 

``apk add Python3`` 

``apk add py3-pip``

``apk add git`` 

``apk add nano`` 

``apk add sudo`` 

``apk add openrc`` 

``apk add postgresql``

``apk add redis``

``apk add gcc``

``apk add python3-dev``

``apk add musl-dev`` 

``apk add build-base``

``apk add libffi-dev``

``apk add openssl-dev``

``apk add poetry``
Now after installing each of this packages Run This ``openrc default`` this will start the openrc service in your system then just run ``rc-service postgresql start`` to start the postgresql easily each time you enter and ``rc-service redis start`` for redis with this our second step is completed  

# Step 3 Setting Up Database 
Time to set database witch is necessary 

Run ``su postgres``

then run ``psql``

This will get you into postgres panel once inside run ``CREATE USER any name WITH PASSWORD 'your password for the user';`` 

This will create the user then run 

``ALTER USER the exact same username you used for command above WITH SUPERUSER;`` 

This will grand your user superuser then run 

``CREATE DATABASE a database name make sure it dond have space;`` 

Then run this 
``ALTER DATABASE your database name OWNER TO your username;`` 

Then
``GRANT ALL PRIVILEGES ON DATABASE database name TO username;``

With this run ``\q`` then run ``exit``  we successfully completed our database part 

# installing Ballsdex
the latest version of Ballsdex From 2.24.3 to 2.26.0 requires python3.13 witch isn't officially available at alpine Linux repositories for now yet so we will have to build it from source using pyenv but that requires more storage and it's pain to do due to that we will be only using Either 2.24.2 or 2.24.1, 2.24.0 works too 

Run this ``git clone --branch release/2.24.2 --depth 1 https://githu
b.com/Ballsdex-Team/BallsDex-DiscordBot.git`` 

then run ``cd BallsDex-DiscordBot`` 

Then ``poetry install`` wait for the dependencies to be installed. 
Once installed Run This ``poetry run python3 -m ballsdex`` this will generate a config.yml then run ``nano config.yml`` to open the file and config the bot by following the official guide https://github.com/Ballsdex-Team/BallsDex-DiscordBot/wiki/Installing-Ballsdex#5-configure-the-bot 

Now our bot is ready to run Before running the bot, you must tell it about your database. Export the BALLSDEXBOT_DB_URL environment variable with the link to Postgres database and user we made earlier:

``export BALLSDEXBOT_DB_URL=postgres://username:password@localhost:5432/database name"
export BALLSDEXBOT_REDIS_URL="redis://127.0.0.1"`` 

For example if you named your database Elon named your user Musk and set password Twitter you should export like this 

``export BALLSDEXBOT_DB_URL=postgres://musk:twitter@localhost:5432/elon"
export BALLSDEXBOT_REDIS_URL="redis://127.0.0.1"``

Once exported run this again ``poetry run python3 -m ballsdex`` And Your Bot will be successful started 
![IMG_20250422_140125](https://github.com/user-attachments/assets/ed18b5d9-ddb1-46d2-a2fb-c886d9042035)


You can hit ``ctrl on termux panel and X on your keyboard to shut down the bot``

# Setting Up Admin Panel 
Run ``cd admin_panel && poetry run python3 manage.py migrate && poetry run python3 manage.py collectstatic --no-input && poetry run uvicorn admin_panel.asgi:application`` to start admin panel for first Time 

Use it only once second time onwards just run ``poetry run uvicorn admin_panel.asgi:application`` to start the admin panel for detailed guide you should check 
Official guide https://github.com/Ballsdex-Team/BallsDex-DiscordBot/wiki/Using-the-new-admin-panel 

# Aftermath 
Next time when you want to start the bot just do this 

``proot-distro login alpine``

``rc-service redis start``

``rc-service postgresql start``

``cd BallsDex-DiscordBot``

``poetry run python3 -m ballsdex``

 ## Any Error, Confusion, Questions or need any support Feel Free to Contact me in Discord Username: noobdog667 
Discord Id: 962947296683757621
