# Mobile DevOps with the Microsoft stack (Demo Script)

<p align="center">
<img src="media/MobileCenter.png" width="624"/>
</p>

## Demo Overview

### High-level flow

DevOps is the union of People, Process and our Products to enable continuous
delivery of value to your end users.  No where is this more important than in the
world of mobile development.  However, mobile presents its own unique set of
challenges. 

1.  Building mobile apps for the different platforms is extremely painful to set up and
    requires special hardware.  iOS code must use macs to build.  Android must have the 
    right software installed and configured on the build machines.

2.  There are thousands of mobile devices.  How will you test your app across all those
    devices?

3.  Deploying apps to alpha testers, beta testers etc.  even all the way to the store is
    difficult and cumbersome.

4.  Need to collect crash analytics from devices

5.  Need to collect telemetry from devices

Visual Studio Mobile Center addresses all of these issues and with a couple of clicks, you can
build out your entire DevOps pipeline.  Continuous Integration, Continuous Testing, Continous Deliver,
Continuous Learning.  You also have an integrated set of dashboards with everything you need for
your mobile app in one easy to consume place


### Key Takeaways

1.  Microsoft has products and services that give you that full DevOps coverage.  VSTS
    for build and release orchestrations.  Xamarin Test Cloud for automated UI testing on over 
    2000 physical devices.  Hockey App for deployment to alpha/beta testers, crash analytics and 
    user telemetry.

2.  This is spread across 3 serices requiring the user to go to three seperate product pages to see
    what's going on with one mobile app.  Wouldn't it be great to have a single place to see all of this?  
    And of course, we do.  Visual Studio Mobile Center.  Visual Studio Mobile Center is a mobile centric lens on top of Visual Studio Team Services.  Visual Studio Mobile Center is your mission control center for your mobile app.

2.  Visual Studio Mobile Center simplifies the enter DevOps pipeline for mobile 
    apps. With a couple of clicks, you can set up Continuous Integration,
    Continuous Delivery, Continuous Testing, Continuous Learning

2.  Visual Studio Mobile Center works for all mobile languages and platforms.
    iOS using swift, objective c, react native.  Android using java or react native.
    Xamarin using c#.  

3.  Visual Studio Mobile Center is your mission control center for mobile apps.  It
    is your one stop shop where you can see everything related to your mobile app
    in one consolidated place with easy to read dashboards.


## Demo Setup
For this demo, you need access to the cadddemos instance of VSTS.  Specifically, the XTC-BikeRiding-iOS build and the Auto-depoy to HockeyApp release.

You will also need an account in VS Mobile Center with access to the BikeRider - Prod
for iOS app as one of your apps in Mobile Center.  I contacted Simina on the Mobile Center team and
she gave me access to the project.

You also need to clone the acquaint mobile xamarin app into your GitHub account

1.  Browse to your github account and click New repository

    <img src="media/2017-04-04_11-39-26.png" width="640" />

2.  Enter MyAcquaint for Repository name
    
    Enter Mobile xamarin app Description
    
    Click Create repository

    <img src="media/2017-04-04_11-48-31.png" width="640" />

3.  Click Import code

    <img src="media/2017-04-04_11-59-33.png" width="640" />

4.  Enter **https://github.com/abelsquidhead/acquaint.git** into Your old repository's clone URL and then click Begin import

    <img src="media/2017-04-04_12-01-22.png" width="640" />

5. Wait for import to finish

    <img src="media/2017-04-04_12-02-24.png" width="640" />


## Demo 

1.  Start up slide deck

    <img src="media/2017-04-04_13-38-03.png" width="640"/>  

    >**Talking Point**: Good morning everyone.  Today's session is on Mobile DevOps with the Microsoft Stack.  We are going to dive in and see how the tools and services from Microsoft help enable you to creating that end to end DevOps experience for mobile apps.

2.  Next slide

    <img src="media/2017-04-04_14-02-23.png" width="640"/>  

     >**Talking Point**: Now before we begin, a quick introduction.  My name is Abel Wang and I have one of the most rediculous job titles ever.  I am a Senior Technical Product Marketing Manager for .NET, Mobile and DevOps at Microsoft.  Big long fancy title, but what I do is I write code.  I've been writing code for over 20 years.  I eat, drink, live writing code and it defines who I am and makes me happy.  My running joke is if I won the lottery today, I would not work for Microsoft tomorow.  I would, however, still be writing code.  That's how much I love it.  Some roles I've had in the past?  I've been a Process Consultant, I'm a certified Scrum Master.  I am an ALM Ranger.  I've written code with the VSTS Team.  My specialty is around General App Dev, DevOps, Mobile, Visual Studio and Azure.  Some fun facts about me?  Back in the day, I used to be a rock star!  A failed rock star... seeing as how I am not on stage rocking a guitar anymore, but onstage rocking Visual Studio Tools.  I'm also a runner and I'm currently training for the Great Wall Marathon.  Hopefully, I won't be that guy throwing up in the middle :)

3. Next slide

    <img src="media/2017-04-04_14-14-17.png" width="640"/>  

    >**Talking Point**: All right, so Mobile DevOps is a very interesting topic, but before we begin, we should probably define what DevOps is.  You ask 10 people and you might get 10 different responses.  So in order to frame this converation we're about to have, let me tell you what Microsoft's definition of DevOps is.

4. Next slide

    <img src="media/2017-04-04_14-22-02.png" width="640"/>  

    >**Talking Point**: For us, DevOps is the union of People, Process and our Products to enable continous delivery of value too our end users.  Now I said this very carefully.  Notice, I didn't say continuous delivery of code right?  Because continuously delivering code just gives us a piles of code.  That doesn't give any value to the end users.  Notice I didn't even say, continously deliver features.  Because once again, we need to make sure the features we deliver sprint after sprint are valuable to our end users.  To do this successfully, to continuously deliver value to your end users, this is extremely dificult.  And to be successful, you have to address all three pillars.  People (or culture), Process, and your Products and tools.

5.  Next slide

    <img src="media/2017-04-04_14-39-47.png" width="640"/>  

    >**Talking Point**: In a traditional DevOps world, our process would looks something like this.  We need a process that will let us iterate fast enough yet still deliver code of high enough quality.  What I want to happen is each developer check in kicks off an automated build.  And the build will compile all the code, and run all the unit tests.  And if everything looks good, an automated deployment pipeline picks up that build and starts deploying it through the different environments.  Dev, QA, UAT so and and so forth until it reaches Production.  And why do we need this pipeline to be automated?  We need this because there could be many builds and releases throughout the day.  So this process has to be repeatable and consistent, every single time.  Human beings can easily introduce errors.  How many of us have deployed code and forgotten to change the connection string in a config file?  In my younger years, I may have forgotten to change the connection string in my web config so when I pushed to Dev, the connection string was still pointing to the Prod database.  Uggh!!!  Another thing I want my automated CD pipeline to do is as it deploys from one environment to the next, let's go ahead and run our automated UI tests.  Let's start shaking out our problems early and automatically.  And if everything looks good and everything flows through the quality gates and the build actualy reaches production, it doesn't end there.  We need to be able to monitor our app.  As a dev, there are three things that are incredibly important to me.  Is my app up or down.  Is my app performing well, and what are users really doing in my app.  Because these three things can let us know if I'm continously delivering value or not.  And these types of telemetry can totally drive what I will do in my next iteration, so that I can continously deliver value to my end users.

6.  Next slide

    <img src="media/2017-04-07_10-29-47.png" width="640"/>

    >**Talking Point**: So what's the difference between traditional DevOps and mobile DevOps?  Well, actually, it's the same thing.  Once again, Mobile DevOps is just the union of people, process and products to enable the continuous delivery of value to our end users, with mobile apps.  And really, no where is this more important than in the world of mobile.  If an app on my phone hasn't been updated in a while, I immediately start thinking that the dev's have abandoned this app and I'm looking in the app store for an app that is innovating faster.  If there are bugs in my app, within seconds, I'm uninstalling that app and installing another app that has higher quality.  So DevOps is vital in the mobile world.  
    But mobile presents its own set of unique challenges.  The first thing that comes to mind is that building mobile apps is not trivial.  Getting a build server set up just right, coming up with the proper hardware, installing the right software on it.  Not trivial.  
    Next, think how many mobile devices there are.  Literally thousands!!! Just in the iOS world, we have iPhone 7, iPhone 7 Plus, iPhone 6s, iPhone 6s Plus, iphone 6, etc etc. You start adding in android devices and oh my goodness.  Thousands of devices out there!  How are we going to test against these devices?   
    Another challenge we face in the wold of mobile is deployment.  How are we going to distribute our builds to the devices used by our test team?  Our Alpha testers, our Beta testers.  And then, how are we going to gather the all important telemtry?  Did our app crash?  Is our app performing well?  And what are users really doing in our apps?

7.  Next slide

    <img src="media/2017-04-07_10-55-42.png" width="640"/>

    >**Talking Point**: So because of these challenges, my mobile DevOps pipeline is going to be similar but not exactly the same as a traditional DevOps pipeline.  I still want continuous integration.  Every developer checkin should kick off my build where unit tests are run, the code is signed, packaged and my drop artifacts are created.

8.  Next slide

    <img src="media/2017-04-07_10-58-52.png" width="640"/>

    >**Talking Point**: Next, if my build is successful, I want to run my automated ui tests against thousand of devices.  At microsoft, we have a service called Xamarin Test Cloud, where your actual app is physically deployed to over 2,500 real devices and your automated UI tests are run on those devices and everything is accessable through the cloud.  You can run Xamarin.UI Tests of course, but you can also run Calabash, Appium and Espresso (espresso is in private preview right now)

9.  Next slide

    <img src="media/2017-04-07_10-58-52.png" width="640"/>

    >**Talking Point**: Next, we need to have Continuous Deployment.  I need to easily distribute my builds to internal and external testers.  I need to be able to control who is in what distribution groups.  I need to be able to do this in an automated pipeline as well as manually doing this.  With HockeyApp, you can do just that.  Easily create distribution groups and distribute your builds to your groups totally bypassing the app store

10. Next slide

    <img src="media/2017-04-07_11-20-33.png" width="640"/>

    >**Talking Point**: We also need to gather analytics and telemtry.  Is my app up or down, is my app performing well, and what are users doing in my app?  HockeyApp can give us this information as well.

11.  Next slide

    <img src="media/2017-04-07_11-23-21.png" width="640"/>

    >**Talking Point**: Hockey App also gives us Crash Reporting.  Instead of begging people to email you their crash reports, crash reports are automatically logged and displayed in Hockey App.

12