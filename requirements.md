# Requirements

Edgegap requires you to have your servers containerized. This means you need Docker. Refer to their [Getting Started Documentation](https://docs.docker.com/guides/getting-started/) if you have zero clue what Docker is and what it does.

You also need to have Unreal Engine [Built from Source](https://dev.epicgames.com/documentation/en-us/unreal-engine/setting-up-dedicated-servers-in-unreal-engine). This is because this is required for Dedicated Servers. If you don't want Dedicated Servers then both Docker and Building from Source aren't required.

After you've obtained Docker, if you want to test it out, you can use [Edgegap's Speedtest Edge](https://docs.edgegap.com/docs/tools-and-integrations/container/docker) to kinda learn it. You really don't need to mess with it honestly and truly. You just need it downloaded and running whenever you are building your server which leads me into something else.

!> Don't stress yourself out!

The folks over at Edgegap have done a really great job at building a Plugin for Unreal which does a lot of heavy lifting for you. It not only builds the game servers, it also pushes them out as a new application version for you to use. <u>You don't need to interact with Docker besides having it running while this process is running. Don't stress yourself out by worrying about what you need to do with it. You'll just give yourself a headache.</u> If you want to learn it feel free! But it's not needed.
