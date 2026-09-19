 [![4](https://static0.howtogeekimages.com/wordpress%2Fwp-content%2Fauthors%2F65c2bd66ad115-IMG_1580.jpeg?fit=crop&w=90&h=90)](https://www.howtogeek.com/author/tim-brookes/)

Published Sep 9, 2026, 3:15 PM EDT

Tim has been covering technology for almost 20 years, in that time spanning a broad range of topics from security to product reviews. He is especially focused on the Apple ecosystem, productivity, and consumer advice.

Over the years Tim has written thousands of articles, reviews, and round-ups in addition to producing video content and original photography. A graduate of journalism, he found his footing as a freelancer with a laptop and loves how he is able to work from practically anywhere.

Now a Senior Editor for iPhone, Mac, and Smart Home at _How-To Geek_, Tim still loves to write. He can also be found crafting round-ups and productivity posts for the [_Zapier_ blog](https://zapier.com/blog/author/tim-brookes/). 

Earlier in his career Tim spent nearly a decade as a writer and eventually [Apple section editor](https://www.makeuseof.com/author/tbrookes/) for _MakeUseOf_. 

Tim currently lives in Brisbane, Australia. Outside of work he loves to hike and work out, play video games, and spend quality time with his wonderful partner and two cats Inka and Roger.

In my search for a media center front-end, Home Assistant server, media server, and do-everything-else computer, I briefly considered buying a Raspberry Pi. Then I caught wind of the used Mac mini market, and it was clear which direction made more sense.

It’s not that I don’t appreciate what the Pi can do, but in my circumstances Apple’s cheapest all-in-one is clearly a better choice when compared to a Pi 5, which currently runs anywhere between $45 and $305. Here’s why.

## The Mac Mini can do more things at once

### More power, more presence

- ![An M4 Mac Mini sitting on a desk encircled by various PC peripherals.](https://static0.howtogeekimages.com/wordpress/wp-content/uploads/wm/2025/01/m4-mac-mini-review-00009.jpeg?q=49&fit=contain&w=750&h=422&dpr=2)Credit: Goran Damnjanovic / How-To Geek
    

I bought a used M1 Mac mini with 16GB of RAM, released in 2020. It has a 256GB solid-state drive, two Thunderbolt 3 (USB 4) ports, two USB-A (USB 3.0) ports, and built-in gigabit Ethernet. To compare, the [Raspberry Pi 5 B 16GB](http://www.raspberrypi.com/products/raspberry-pi-5/) has a BCM2712 Broadcom Arm Cortex-A76 processor, 16GB of RAM, two USB 3.0 ports, two USB 2.0 ports, and gigabit Ethernet.

Comparing Apple’s aging M1 system-on-chip with the Raspberry Pi’s BCM2712 processor reveals a few obvious points of difference. The M1 has double the core and thread count, at eight each compared to four. The Broadcom gets a little ahead in terms of machine learning performance (at 13 TOPS, compared to 11), but the two are fairly well matched.

Apple’s integrated GPU runs rings around the Broadcom VideoCore VII seen on the Raspberry Pi, with 16 times the number of video compute units, the ability to turbo up to 1.3GHz, and hardware encode and decode for video codecs like HEVC, H.264, and VP9. In terms of RAM, Apple’s dual channel [unified RAM](https://www.howtogeek.com/701804/how-unified-memory-speeds-up-apples-m1-arm-macs/) is four times faster in terms of memory bandwidth compared with the Pi 5 B’s single channel memory.

In Geekbench benchmarks as reported by [CPU-Monkey](https://www.cpu-monkey.com/en/compare_cpu-apple_m1-vs-raspberry_pi_5_b_broadcom_bcm2712), the Mac mini earned three times more points than the Pi 5 B. Things get worse in multi-core scores, with five times better performance from the M1. GPU scores speak for themselves, with an FP32 score that’s 20 times better on Apple’s chip.

So what do these technical specs and hypothetical benchmarks mean for real-world performance? You’ll get a lot more out of the M1 Mac mini before you run out of system overhead. As someone who wants a do-it-all unit that sits under my TV, [I was looking for a media center front-end](https://www.howtogeek.com/how-i-turned-a-mac-mini-into-a-media-center-front-end/), a media server for streaming video around the house, [a Home Assistant server](https://www.howtogeek.com/how-to-set-up-home-assistant-mac-mini-macbook/), a file server, and a machine that I could use for all manner of extra projects if need be.

If I want to emulate an Xbox or an arcade cabinet on my TV, I can. If I want to spin up five or six [Docker containers](https://www.howtogeek.com/733522/docker-for-beginners-everything-you-need-to-know/) while streaming movies, I can do it. If for some reason I need a desktop PC to edit photos and leave 50 tabs open at once because every laptop in my house mysteriously stops working, there’s a Mac mini right there.

This isn’t to say that a Raspberry Pi isn’t capable of [doing many of these tasks](https://www.howtogeek.com/projects-that-might-make-me-finally-get-my-raspberry-pi-out-of-storage/). The Pi 5 B 16GB is overkill for use as a Home Assistant server, and it would comfortably be able to act as a file server while playing some SNES games. But when it comes to tasks like transcoding large video files or upscaling PS2 games, the Pi will choke where the Mac mini will just keep on chugging.

## I already use Apple everywhere

### Compatibility is compelling

I have used Linux extensively in the past. I ditched Windows for Linux back in the late 2000s, but I found myself gravitating towards the Apple ecosystem within a few years. I often touch base with Linux, having an Ubuntu virtual machine ready to go at a moment’s notice, but it’s not my primary operating system or ecosystem.

   ![Connecting via VNC to local Mac mini.](https://static0.howtogeekimages.com/wordpress/wp-content/uploads/2025/07/connecting-via-vnc-to-local-mac-mini.png?q=70&fit=crop&w=825&dpr=1)

Having primarily used macOS for going on 14 years, I’ve grown to love the stability, performance, and simplicity of the OS. For me, it’s a comfortable place to be and I’m familiar with the quirks of Apple’s operating system. I know how to navigate macOS’ somewhat convoluted permissions system, I frequently use command line tools to install software and complete other simple tasks, and I know how to fix things when they go wrong.

This isn’t to say that Raspberry Pi OS—or one of the many other Linux distributions you could install on your Pi—is prohibitively difficult to use. In fact, it’s arguably one of the better single-board computers to choose if you’re looking for support on account of the project’s well-maintained OS.

But as an Apple user, grabbing a Mac mini had a few perks that allowed me to get up and running quickly. There was no on-boarding or adjustment period. I enabled macOS’ built-in VNC server instantly so I could set up the Mac mini remotely using my MacBook Pro. I am able to AirDrop files with ease, and I can even use the Mac mini as an AirPlay receiver when I need to.

   ![Home Assistant running in a VM.](https://static0.howtogeekimages.com/wordpress/wp-content/uploads/2025/07/home-assistant-running-in-a-vm.png?q=70&fit=crop&w=825&dpr=1)

I can use the Mac mini for content caching purposes so that a whole household’s worth of iOS and macOS updates are handled by a single machine. I eventually intend to set up a networked Time Machine destination using the Mac mini, something that is relatively easy to do by checking a few boxes in System Preferences, but a project for which I’ll need to assemble enough storage first.

## I wanted minimal setup and fuss

### A desktop is just easier to deal with

The Mac mini is a preassembled computer. It has limitations, like RAM you can’t upgrade, but it also comes with everything you need to get started. You plug it in, switch it on, and it spits out a familiar desktop via an HDMI connection. It’s got a paltry but adequate 256GB of storage inside, which is perfect for the kind of things I want to do on it locally.

The Raspberry Pi 5 B doesn’t actually come with everything you need to get started. You’ll need to find your own 5V/5A (25W) power supply that uses a USB-C interface. These aren’t exactly expensive, Raspberry Pi has a [27W model](https://www.microcenter.com/product/671926/raspberry-pi-27w-usb-c-psu-white?src=raspberrypi) that costs about $12.

You’ll also need a case to protect the Pi, since in its default state the single-board computer is just that: a naked board. Though these aren’t necessary, they’re highly recommended. You could fashion or 3D-print your own for pennies, or you could spend $10 on the official [Pi 5 Case](https://www.microcenter.com/product/671928/raspberry-pi-5-case-red-white?src=raspberrypi) which includes a fan.

If you really want to push the Pi 5 to its limits, you might want the official aftermarket [Pi 5 Active Cooler](https://www.microcenter.com/product/671930/raspberry-pi-5-active-cooler?src=raspberrypi) for $10. You can either use it as so without a case (which will provide better airflow) or pick a case that accommodates the design. You could also Frankenstein something out of whatever you have lying around.

On top of this, you’ll need a microSD card on which to store your operating system, and to prepare it ahead of time. Alternatively, you might want to spend some time looking into alternative OS options that might better suit your needs. The Pi 5 B also features a PCIe 2.0 x1 interface, which can be combined with an adapter to add a fast NVMe drive for high-speed local storage. You’ll need to provide these yourself.

I also felt the inclusion of two Thunderbolt (USB 4) ports that can do 40Gb/sec out of the box would come in very handy when it comes to adding a significant amount of storage to my setup. While I love a good project, I wanted something a little more turnkey. This all felt like a lot of effort in the moment, and the cost adds up.

## I saved money buying used

### The best things in life are discounted

    ![An M4 Mac Mini sitting on a granite countertop.](https://static0.howtogeekimages.com/wordpress/wp-content/uploads/wm/2025/01/m4-mac-mini-review-00018.jpeg?q=49&fit=crop&w=825&dpr=2)Credit: Goran Damnjanovic / How-To Geek

Buying a used Mac mini only cost me $160 for a computer that retailed at $799 (with the RAM upgrade) only a few years ago. This was [undoubtedly a bargain](https://www.howtogeek.com/this-second-hand-m1-mac-mini-was-my-bargain-buy-of-the-year/), but now that Apple’s in-house desktop chips are old news, there are plenty more bargains to be had. Best of all, these chips are still supported by the current and upcoming version of macOS (though it’s true that a Raspberry Pi will likely vastly outlast an M1 Mac mini in terms of software support).

If you can find a used Raspberry Pi, then you could make the same argument. These machines were cheap when they launched, and they’re even cheaper after a few years of usage. Unfortunately, there’s not a lot to choose from in my local area. I couldn’t find a single Raspberry Pi 5 (let alone the 16GB model) on Facebook Marketplace when I looked, but the place was flooded with Mac minis from old Intel models right through to higher-end M4 Pro configurations.

Spending $140 on an 8GB Raspberry Pi, then throwing in another $20 for a power supply and case and even more for local storage didn’t make sense at this point. It’s worth noting that I wouldn’t have bought a new Mac mini for this purpose either. If the used Mac mini market wasn't so compelling right now, I would have gone for a cheaper option like a single board computer for sure (and maybe even a few of them, to overcome the performance limitations).

### It doesn't have to be a Mac

If you’re a happy Windows user, you could make many of these arguments in favor of a [Windows mini PC alternative to the Mac mini](https://www.howtogeek.com/the-best-windows-mini-pc-alternatives-to-the-mac-mini/). The Mac mini is a single product line, so they appear to be in better supply on the used market compared to their Windows counterparts, but if you scour Facebook Marketplace and eBay, you should have plenty to choose from.