# What is Edgegap?
Edgegap is a cross-platform fully managed game server host. Whether you're a starting out Indie or AAA Game Developer, anyone can take the reign and gain access to over 615+ locations that grant you a 58% reduction in latency versus other providers. Not only that, they've also made things super easy! Their dashboard is simplified to make updating things a breeze as seeing where your players are playing the most. As well as being free-to-start. No upfront costs or fees with extremely competitive pay-per-minute hosting so you only pay for what is used which lowers your costs by up to 70%!

Interesting in what you hear so far? Don't take it from me, see for yourself with their [Case Studies](https://edgegap.com/gaming/case-studies) and [Performance Benchmark](https://edgegap.com/resources/performance-benchmark) where they was able to scale up to 14 Million Users in just 60 minutes.

# Getting Started with Edgegap

You need to sign up, you don't even need a Credit Card to start! Their Free Trial Tier grants you 1 Application with 1 Deployment (constrained to 60 minutes per deployment) as well as a time-limited Matchmaker so you can test out a lot of things for free!

# Getting Started in the Edgegap Learner Project

In my Edgegap learner Project you'll be met with a <b>Game Instance</b> Class named <u>EdgegapInstance</u>. Inside of this you'll be met with some things you don't need to worry about! 

!> DO NOT Touch the Server Only Category! This pulls some info from Edgegap's <i>Arbitrium</i> which is then used later on in the Server! Hence the name "Server Only"!

![Game Instance Image](https://i.imgur.com/XY2gSSK.png "An Image of the Game Instance")

The code that is inside of the Event Init function should be left alone as well as that is called for the Server whenever it launches!

We will focus on variables that are not the Server Only variables! The ones that we'll need to edit to get the project ready are <b>Token, AppVersion, and AppName</b>. If you are using Edgegap's Matchmaker, you will also need the MatchmakingURL.

# Making a new App

If you have followed this perfectly so far, you should've gotten the Edgegap Unreal Plugin and (hopefully) built it successfully. If you didn't go to [fixing known Edgegap Errors](known-errors).

While on the Map, select the Edgegap Plugin Widget in the Toolbar and then click on Settings, this takes us to the Project Settings to mess with Edgegap Further.

![settings](https://i.imgur.com/Jp7zOrM.png)

# Getting your API Token

We'll need an API Token from Edgegap and this can happen one of two-ways, either going to the [Dashboard and retrieving it](https://app.edgegap.com/user-settings?tab=tokens) or clicking on the <b>Get a Token</b> Button. That takes you to the Dashboard and Generates a new One-Click Token in the same click.

?> If doing it manually on the Dashboard, when creating an API Token, ensure you are clicking on the <b>"is Quick Start"</b> checkbox after you make the label. This marks it as a Token that <b>CAN</b> be used in the Settings.


Copy the Token and then paste it into the Text Box and press ENTER to ensure it gets pushed through. After that, the Verify Button should light-up and then you can click and see if it verifies the token. If you receive an error, you have not done something right and should try to regenerate the token.

# Creating the App actually

Enter the Application Name you want! No Spaces! You'll also need an app image, I recommend a size of 256x256. After you've done that, click create and then it should be good to go now! 

![creating-app](https://i.imgur.com/llKohv9.png)

# Adding AppName in EdgegapInstance


Back in our EdgegapInstance we can go to our AppName variable and add in our App name that we just filled out in the previous step! In my Example it is <b>"Learner"</b>.

![appnamevariable](https://i.imgur.com/R2oBJZc.png)
