# Requirements

Edgegap requires you to have your servers containerized. This means you need Docker. Refer to their [Getting Started Documentation](https://docs.docker.com/guides/getting-started/) if you have zero clue what Docker is and what it does.

This Learner documentation all goes off of Betide's Edgegap Integration Kit Plugin. If you want it, you can [purchase here to receive **Verified Support**](https://www.unrealengine.com/marketplace/en-US/product/edgegap-integration-kit) or get the [Github version](https://github.com/betidestudio/EdgegapIntegrationKit) which is free and open source. 

For your Engine version you have two options: Source Build or Binary Build from the Epic Games Launcher. If we use Source Build we can cut out work and save time later and that is the recommended way, but I've been doing the Binary Build more and more.

?> I don't need to build from Source for dedicated servers?
## It depends on your use-case.
For Developers who are wanting to be the ones in full control of their servers and are using Platforms such as Edgegap, Hathora, Rivet, etc. I would say it depends on what you want to do! When using a Source Build you have to compile the entire Editor from scratch which takes a big commitment of time initially to get started. When doing the Binary Build we do something in a Dockerfile and perform what is known as a *multi-stage build*. The way this works is that it copies the Unreal Engine version you request (from 4.27 to 5.4.4 currently at the time of writing) and builds your project inside of that. If you want to learn more about multi-stage build, you can refer to [Docker's Documentation](https://docs.docker.com/build/building/multi-stage/) regarding it. 
For Developers who are wanting to have "Official" Servers and player-hosted servers, this method will not work for you and I recommend you use the Source Build way.

## For Binary Build Path:
!> NOTE: You CANNOT use the Edgegap Integration Kit Plugin's Build and Push feature when using this path. Please be aware of that.
Requirements are as follows:
- Have an Unreal Engine version from the Epic Games Launcher (my recommendation is the latest - 5.4.4).
- Have Docker Installed
- Authenticate with GCHR (Github Container Registry) so we can access Github. Please note this requirement is still following Epic Games' Terms of Service and requires your Epic Games Account and Github Account to be linked together. You can follow how to do that here: [UE on Github](https://www.unrealengine.com/en-US/ue-on-github)
-- Note: You will also need to do ``docker login`` with ghcr.io in order to Authenticate to pull packages. Please follow the documentation listed here in order to do that [Containers Quick Start, Steps 4 & 5](https://dev.epicgames.com/documentation/en-us/unreal-engine/containers-quick-start?application_version=4.27#4.authenticatingwithgithubcontainerregistry)
- Use ``docker pull`` to get the Engine Version to match with what you've selected from the Launcher. The docs above also tell you do that. I also recommend you do the SLIM version. This can save on space.
- Put a Dockerfile in our Project Directory, I recommend Edgegap's that they have made. It helps us do what we need to do and doesn't require any changes. Please view that [here](https://docs.edgegap.com/docs/tools-and-integrations/unreal-docker#writing-the-dockerfile) BE SURE TO REPLACE THE VALUES IN THAT DOCKERFILE WITH YOUR OWN.
- That's essentially the way to do the Binary Build Path.
- If you want to automate this process, I recommend using my [batch file](batch-file) in order to do a quick start. You just need to add in your Registry, Project, Repository, and Account and Token credentials. These are all found on the [Edgegap Container Registry](https://app.edgegap.com/registry-management/repositories/list) which gives you all that information needed. The Batch File is based off of Edgegap Team Member Bastien's Bash Script and modified for Windows. It will create a TAG which is based off of the Day, Date, and Time and then push it to Edgegap for you automatically. This unfortunately does not create an application version for you and will need to be created manually.

## For Source Build Path:
!> This Method CAN use the Edgegap Integration Kit Plugin's Build and Push Feature.
Please View the Documentation here to build from Source: [Built from Source](https://dev.epicgames.com/documentation/en-us/unreal-engine/setting-up-dedicated-servers-in-unreal-engine).

After you've obtained Docker, if you want to test it out, you can use [Edgegap's Speedtest Edge](https://docs.edgegap.com/docs/tools-and-integrations/container/docker) to kinda learn it. You really don't need to mess with it honestly and truly. You just need it downloaded and running whenever you are building your server which leads me into something else.

!> Don't stress yourself out! Games are already hard and we can fix some of those heavy parts.
The folks at Edgegap created a really good plugin that does a TON of heavy lifting for you*. It not only builds the game servers, but also pushes them out as new application version for you to use. You quite literally don't need to interact with Docker besides having it run in the background while it's building. Even better, Betide built upon that in order to make the Edgegap Integration Kit which makes it even easier to create deployments and do matchmaking!
(* only applies to the Source Build Version)

# You need a C++ Project or Mixed Project.

No, you don't have to write any code in C++, you can keep everything in Blueprints. But a C++ Class is required to build the server which then makes it a Mixed Project. If you're on Blueprints and need to add C++ class, go to the Tools Toolbar (in Unreal 5.X+) and just add a New C++ Class, doesn't even have to be named anything special. Just add it. You'll have to close the Editor and then Build the Project in Visual Studio for it to be updated.

![toolbar location](https://i.imgur.com/X0piA4A.png)

After you've done that 

# [Done with those? Let's dive into the Engine](working-with-edgegap)
