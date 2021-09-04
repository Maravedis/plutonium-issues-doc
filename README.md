# Plutonium Issues Docs

This repository is an attempt to harmonize documentation on the issues Plutonium is facing with the down of [5eTools](5e.tools).

This documents will try to explain some solutions that you can implement, and point to some tools some generous people wrote.

## Overview and disclaimers

First, English is not my first language. I'll do my best but mistakes will sneak by. Sorry. Also, while I'm fairly knowledgeable about computers, I am unfamiliar with Windows and still a newcomer to plutonium and foundry in general. Don't hesitate to correct me if you spot mistakes.

I also don't use the Forge hosting solution. All the guides that tell you to do in-foundry things should work, but if you need to interact with the filesystem, I can't help you, I have no idea of how Forge works.

## My game  is SO SLOW, will this guide fix it?

Yes! Foundry is slow because the imported actors / items from 5eTools have their images stored on the 5eTools server. Since this server is unreachable, the images can't load. Foundry waits a bit before declaring an error and moving on to the next image. So for every token / actor image, you have to wait a couple of seconds for foundry to realize it's not gonna happen.

## Contents

* **Recommended** [The easiest way to make everything work with no additional work :tm:](docs/easiest-way.md)
* Advanced
    * Set up Plutonium to use a mirror for future imports
        * [official Mirror](docs/import-mirror.md)
        * Local Mirror // TODO
            * [Linux]()
            * [Windows]()

    * Imported Tokens / actors / items image issues
        * [Use the mirror sites for images](docs/mirror-images.md)
        * Use local copies for images
            * [Linux](docs/local-images/use-local-images-linux.md)
            * [Windows](docs/local-images/use-local-images-win.md)
## Resources
* [Browser extension to use mirrors](https://github.com/flamewave000/plutonium-mirror) by flameweave000
* [Macro to change all images path](https://github.com/surged20/foundryvtt-update-image-macro) by surged20
* [Unofficial Plutonium Discord](https://discord.gg/nGvRCDs)


## Credits

* LordDusk#0001 God-Emperor of the community
* flameweave000#0001 for writing the browser extension
* Surge#4715 for general awesomeness and writing the macro tool 
* Lyra214#6717 for writing Windows stuff (seriously though, thank you, I'm helpless)
