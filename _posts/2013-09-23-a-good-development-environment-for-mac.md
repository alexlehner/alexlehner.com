---
layout: post
title: A Good Development Environment For Mac
category: articles
tags: [development, mac, apps]
image:
  feature: devEnvironment-short.png
redirect_from: "/a-good-development-environment-part-1-desktop-apps/"
---

There are no shortage of applications available to support the needs of web developers and designers, especially for Mac users. There are one-app-fits-all solutions like [Adobe Dreamweaver](http://www.adobe.com/products/dreamweaver.html) and [Panic’s Coda](http://panic.com/coda/) that include a variety of features such as [Syntax Highlighting](http://en.wikipedia.org/wiki/Syntax_highlighting), [Code Completion](http://en.wikipedia.org/wiki/Autocomplete#In_source_code_editors), [SFTP](http://en.wikipedia.org/wiki/SSH_File_Transfer_Protocol), and [Version Control](http://en.wikipedia.org/wiki/Version_control). Alternatively, many prefer single purpose apps such as [ImageOptim](http://imageoptim.com/) - a lossless image compressor. It does this one task very well.

## Text Editors

Text Editors are at the core of any developer's environment. They make it easier (or more difficult) to do the management of files. There are hundreds of different text editors out there. If you are just getting started there are tons of free solutions such as: Text Wrangler, Kod, Smultron, Emacs, Komodo Edit, and more. Check out a few awesome ones below:

### [Sublime Text](http://www.sublimetext.com/)

[Sublime Text](http://www.sublimetext.com/) is an upcoming text editor in the development community and is packed with keyboard shortcuts and features. This text editor is unique in the way it empowers keyboard enthusiasts. With features like Goto Anything, an intuitive [fuzzy](http://en.wikipedia.org/wiki/Approximate_string_matching) search feature that allows the user to open any project files or settings, there is no need for a mouse. This feature has garnered support from many developers who prefer the simplicity and efficiency of the command-line. With a growing collection of quality plugins and support across Mac, PC, and Linux, Sublime Text is substantially gaining ground. The program goes for $70 per user. This allows you to install the application on any of your computers, regardless of OS. For the weary, a fully featured evaluation copy is available. Personally I find the interface and syntax highlighting worth the dough.

### [TextMate](http://macromates.com/)

[TextMate](http://macromates.com/) is another popular editor around the web. Many of the concepts between Sublime Text and Textmate are similar, however the interface is very different. In an interesting move, TextMate 2 was released publicly on GitHub. This allows users to download and recompile the source code to manipulate the interface as they see fit. So if you are comfortable with software compiling it can be had for the price of nada (free). For those who would rather not bother with the compiling, you can download the executables for ~$54 and support the developer.

### [Coda 2](http://panic.com/coda/)

[Coda](http://panic.com/coda/) was briefly mentioned earlier in this post and is often considered an integrated development environment (IDE). This means it usually encompasses features beyond just a text editor. Coda combines a great text editor with integrated SFTP support. This means that it is extremely easy to manipulate files directly on a server. This is a great feature, however must be used carefully. Changing files on a live server is never a good idea. Coda strives to have your entire development workflow encompassed in the single app. This is why it includes substantial documentation, version control support, browser compatibility testing, mobile preview, css tools, SQL editor, command line interface, and many more features. I personally used Coda and now Coda 2 for many years. I still find that it is a great tool and has a very intuitive interface. The program will run you $75 and is available from the [Mac App Store](https://itunes.apple.com/us/app/coda-2/id499340368?mt=12&uo=4&at=11l4BV) or [Panic’s website](https://panic.com/coda/buy.html). A trial is available for those interested in giving it a go.

## Photo Editing

There are hundreds of photo editing tools out there. Here are two that I have integrated pretty deeply into my workflow.

### [Photoshop](http://www.adobe.com/products/photoshop.html)

[Photoshop](http://www.adobe.com/products/photoshop.html) is the go to image editor of professionals and is consistently left open while working on new designs. Recently Adobe has been pushing their [Creative Cloud](http://www.adobe.com/products/creativecloud.html) initiative. This allows people to may a monthly subscription for the suite of professional apps. For the casual or new users, this is great. As a student you can get the entire Creative Suite with free updates for $20 per month and install it on up to two computers.

### [Pixelmator](http://www.pixelmator.com/)

A new contender in the image manipulation market, [Pixelmator](http://www.pixelmator.com/) came in with a fresh approach for image manipulation at a reasonable cost. The program possesses many of the features of its more expensive cousin at only $29 via the Mac App store. The program is only available on Macs and has won several design awards. Pixelmator is definitely a good solution for those hesitant to pay up for Photoshop. Those familiar with other image editing programs will be right at home in Pixelmator’s interface.

## SFTP & Database

Where would the web be if it wasn’t for web servers? The following programs take some of the stress off the designers and make it a breeze to make server-side changes. 

### [Transmit](http://panic.com/transmit/)

[Transmit](http://panic.com/transmit/) comes from the same makers of Coda. [Panic’s](http://panic.com/) great development continues with [Transmit 4](http://panic.com/transmit/). It offers Mac users an intuitive and customizable interface for uploading and downloading from web servers. It is compatible with plenty of other protocols makes it simple to communicate with [Amazon S3](http://aws.amazon.com/s3/). The recent updates allow users to sync their favorite servers between computers via iCloud or Dropbox. It will even allow you to “mount” your remote disk and use whatever text client you want to update. The syncing feature, remote disk, and interface set it a part from all other clients.

### [Cyberduck](http://cyberduck.ch/)

For those casual web designers who need a quick and easy solution (see: free) to manage files between a local computer and a server, [Cyberduck](http://cyberduck.ch/) is a great option. It is a free file transfer client that has an extremely simple interface. Though it doesn’t have the syncing or remote disk features of Transmit, it is still an excellent program. There is even a Windows version. Gasp! Mac users can get it from the Cyberduck [website](http://cyberduck.ch/) or the [Mac App store](http://cyberduck.ch/appstore).

### [Sequel Pro](http://www.sequelpro.com/)

Every developer eventually has to get their hands dirty with MySQL. Why make it a miserable experience? [Sequel Pro](http://www.sequelpro.com/) is a great application that makes interfacing with MySQL simple. The program is very intuitive, and open source. While many turn to [MySQL Workbench](http://www.mysql.com/products/workbench/) as a full diagramming and management solution, I find having a simple GUI works better for me. You can even find much of the Sequel Pro interface in Coda 2′s MySQL implementation. What’s that saying about mimicking and flattery?

## Debugging & Testing

So you have a great idea for a site? That’s awesome! Now let’s build and test it. Let’s find some programs that make that exponentially easier.

### [MAMP](http://www.mamp.info/en/index.html)

<figure>
	<a href="{{ site.url }}/images/mamp-front.png"><img src="{{ site.url }}/images/mamp-front.png"></a>
	<figcaption>MAMP Interface</figcaption>
</figure>

[MAMP](http://www.mamp.info/en/index.html) stands for: Mac, Apache, MySQL, PHP. This simple program allows you to run Apache, MySQL, and PHP on your local computer. This allows you to run a full local web server. How does this help? Well MAMP gives you a place to build, break, and test without affecting anyone but yourself. MAMP comes with a trial version of MAMP Pro which adds some extra cool features. I have yet to need any of the Pro features, but $59 isn’t a lot to ask for considering I use the program daily. I have tried several similar programs to MAMP, none have been as easy.

### Parallels / VMWare / VirtualBox

Your mac is great at running Mac applications. You can reasonably test your design on all current versions of Firefox, Chrome, Safari, and Opera. That’s awesome, except there isn’t an IE for mac ([anymore](http://en.wikipedia.org/wiki/Internet_Explorer_for_Mac)). To test your site in various version of Internet Explorer, you are going to need various versions of Microsoft Windows. To do that you can keep a few Windows boxes lying around, or virtualize it. The big names in Mac Virtualization are [Parallels](http://www.parallels.com/), [VMWare](http://www.vmware.com/products/fusion/), and [VirtualBox](https://www.virtualbox.org/wiki/Downloads). All three aim to let you run different operating systems within Mac OS X. Of the three, I have found that VMWare Fusion is the most reliable and featured. The program will cost you a [pretty penny](http://store.vmware.com/DRHM/store?Action=DisplayProductDetailsPage&SiteID=vmware&Locale=en_US&ThemeID=2485600&productID=285051300&src=WWW_eBIZ_productpage_Fusion_Buy_US) but makes up for it with its ease of use and functionality. If, however, you are interested in keeping costs down, [VirtualBox](https://www.virtualbox.org/wiki/Downloads) is free and has the core features you need.

### [iOS Simulator](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/iOS_Simulator_Guide/Introduction/Introduction.html)

<figure>
	<a href="{{ site.url }}/images/devEnvironment-screenshot-big.png"><img src="{{ site.url }}/images/devEnvironment-screenshot-small.png"></a>
	<figcaption>Screenshot of the iOS Simulator running while working on this article</figcaption>
</figure>

In these days of [responsive web design](http://coding.smashingmagazine.com/2011/01/12/guidelines-for-responsive-web-design/) and [increased mobile usage](http://www.smartinsights.com/mobile-marketing/mobile-marketing-analytics/mobile-marketing-statistics/), it is important to be sure that your website looks great on all devices. One excellent tool is the [iOS Simulator](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/iOS_Simulator_Guide/Introduction/Introduction.html). The program allows you to emulate various versions of the iPhone and iPad. Though it won’t help you design a great site for the [Galaxy S3](http://www.samsung.com/global/microsite/galaxys4/), it sure is a great start. The program comes as part of Xcode and is only available on a mac.
