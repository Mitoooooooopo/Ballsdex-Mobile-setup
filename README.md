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

Once inside the panel Run this ``apk update & apk upgrade`` Once it's finished 

Our First Step is completed it should be straightforward and easy but if you get a question feel free to create a issue on this github 

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
