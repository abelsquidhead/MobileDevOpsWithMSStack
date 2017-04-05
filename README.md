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

     >**Talking Point**: Now before we begin, a quick introduction.  My name is Abel Wang and I have one of the most rediculous job titles ever.  I am a Senior Technical Product Marketing Manager for .NET, Mobile and DevOps at Microsoft.  Big long fancy title, but what I do is I write code.  I've been writing code for over 20 years.  I eat, drink, live writing code and it makes me rediculously happy.  My running joke is if I won the lottery today, I would not work for Microsoft tomorow.  I would, however, still be writing code.  That's how much I love it.  Some roles I've had in the past?  I've been a Process Consultant, I'm a certified Scrum Master.  I am an ALM Ranger.  I've written code with the VSTS Team.  My specialty is around General App Dev, DevOps, Mobile, Visual Studio and Azure.  Some fun facts about me?  Back in the day, I used to be a rock star!  A failed rock star... seeing as how I am not on stage rocking a guitar anymore, but onstage rocking Visual Studio Tools now :.  I'm also a runner and I'm currently training for the Great Wall Marathon.  Hopefully, I won't be that guy throwing up in the middle :)

3. Next slide

    <img src="media/2017-04-04_14-14-17.png" width="640"/>  

    >**Talking Point**: All right, so Mobile DevOps is a very interesting topic, but before we begin, we should probably define what DevOps is.  You ask 10 people and you might get 10 different responses.  So in order to frame this converation we're about to have, let me tell you what Microsoft's definition of DevOps is.

4. Next slide

    <img src="media/2017-04-04_14-22-02.png" width="640"/>  

    >**Talking Point**: For us, DevOps is the union of People, Process and our Products to enable continous delivery of value too our end users.  Now I said this very carefully.  Notice, I didn't say continuous delivery of code right?  Because continuously delivering code just gives us a pile of code.  Doesn't give any value to the end users.  Notice I didn't even say, continously deliver features.  Because once again, we need to make sure the features we deliver sprint after sprint are valuable to our end users.

5.  Next slide

    <img src="media/2017-04-04_14-39-47.png" width="640"/>  

    >**Talking Point**: For us, DevOps is the union of People, Process and our Products to enable continous delivery of value too our end users.  Now I said this very carefully.  Notice, I didn't say continuous delivery of code right?  Because continuously delivering code just gives us a pile of code.  Doesn't give any value to the end users.  Notice I didn't even say, continously deliver features.  Because once again, we need to make sure the features we deliver sprint after sprint are valuable to our end users.