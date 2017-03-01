### root@cpanelsrv [~]#   *Engintron v1.8.1 (Build 20170301) released on March 1st, 2017*

**Have a look at the [CHANGELOG](https://github.com/engintron/engintron/wiki/Changelog) for more information on this latest release**

***
![Engintron](https://engintron.com/assets/logo/Engintron_Logo_316x98_24_black.png)

_Engintron for cPanel/WHM is the easiest way to integrate Nginx on your cPanel/WHM server. Engintron will improve the performance & web serving capacity of your server, while reducing CPU/RAM load at the same time. It does that by installing & configuring the popular Nginx webserver to act as a reverse caching proxy for static files (like CSS, JS, images etc.) with an additional micro-cache layer to significantly improve performance of dynamic content generated by CMSs like WordPress, Joomla or Drupal as well as forum software like vBulletin, phpBB, SMF or e-commerce solutions like Magento, OpenCart, PrestaShop and others._

***
##### Quick Navigation
* [engintron.com](https://engintron.com)
* [Documentation (Wiki)](https://github.com/engintron/engintron/wiki)
* [FAQ](https://github.com/engintron/engintron/wiki/FAQ)
* [Get support & report bugs (Issues)](https://github.com/engintron/engintron/issues)
* [Join the Engintron Newsletter / Mailing List](https://tinyletter.com/engintron)
* Engintron on [Facebook](https://www.facebook.com/engintron/), [Twitter](https://twitter.com/engintron_sh) & [Google+](https://plus.google.com/117428375464020763682)
* [Rate and/or review Engintron in the cPanel Applications Directory](https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel)
* [Donate & Support the development of Engintron](https://engintron.com/?donate)

***
# NEW - Join the Engintron Newsletter / Mailing List
It's easy to miss an Engintron update on social media. If you want to know for sure when the latest version of Engintron is released, sign up to get notified directly to your inbox. We will never spam you.

Sign up here https://tinyletter.com/engintron or here https://engintron.com

***


![Engintron App in WHM](https://engintron.com/assets/screenshots/1.6.0_20160216_ad_2048x1072.png)


==
## Engintron is Nginx on cPanel, done right!

[Nginx®](http://nginx.org/) is a powerful open source web server that was built to scale websites to millions of visitors. cPanel® is the leading hosting control panel worldwide.

Engintron integrates Nginx into cPanel so you can enjoy amazing performance for your sites, without having to sacrifice important hosting features found in cPanel.

_And best of all? Engintron is totally free to use!_


### But why should you use Nginx in your cPanel server?

cPanel uses the Apache webserver to serve websites by default. Apache however is not known to perform well under heavy web traffic (especially traffic spikes) and it's also CPU/RAM hungry. So how can you mitigate these issues? The answer is simple: by deploying Nginx, another popular web server software, in front of Apache. Nginx acts as a web traffic proxy, directly serving all static assets like CSS, JS, images etc. by default, instead of Apache. This drops significantly the CPU/RAM resources consumed by Apache, leaving your server with more available resources for other tasks or, better still, with room for more websites to host.

The way Engintron sets up Nginx inside your cPanel is a lot like how the popular CloudFlare CDN works. Nginx (like CloudFlare) directly serves all static content like CSS, JS, images etc. instead of your actual web server, thus lowering the load on your cPanel server. But unlike CloudFlare which requires that all your domains are set up with that service, you do everything inside your cPanel server. And better still? You also have an additional caching layer for when your traffic spikes, not just on one website, but entirely for your server. This additional caching layer is referred to as a "micro cache" and it only caches GET & HEAD requests (never POST requests) which means that it is possible to use it on any type of website, either a small dynamic Joomla corporate website or WordPress blog to a more complex news portal or forum or e-commerce website, that requires users to log in and handle personalized content or even generate content. Engintron's 1 second "micro cache" solution setup with Nginx is therefore ideal for any type of website and it can raise the number of concurrent requests served by your cPanel server from a few hundred per second (using just Apache) to thousands (using Nginx in front of Apache).

Not only will your serving capacity increase, but the load on your server will also significantly drop :)

If you are facing performance issues with your cPanel server, Engintron is your go-to solution. And in fact it's really a "set & forget" solution as you'll set it up once and then it will just run on your server without any additional maintenance on your side.

If you can sign up for a cPanel/WHM server on any hosting company and work your way through WHM, then setting up Engintron should be a piece of cake for you. If you don't manage your cPanel server, then you can always (kindly) ask your hosting company or system administrator to have a look at Engintron and deploy it on your cPanel server. It really only takes a few minutes and there is zero configuration afterwards to get the standard optimizations offered by Nginx.


### OK, I'm sold! How do I install Engintron on my cPanel server?

Installation is a process that lasts only a few minutes. You'll need root SSH access to your cPanel server. Also check the current requirements (listed lower). If everything is ok, log in as root and type the following commands, one at a time:

    cd /  
    rm -f engintron.sh  
    wget --no-check-certificate https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh  
    bash engintron.sh install

Or in one quick command to paste in the terminal:

    cd /; rm -f engintron.sh; wget --no-check-certificate https://raw.githubusercontent.com/engintron/engintron/master/engintron.sh; bash engintron.sh install

The process will take a couple of minutes to complete and after that, Engintron will be installed on your cPanel server. Engintron has a nice user interface which is activated inside WHM, under the Plugins section. After installation, refresh WHM in your browser and you should see Engintron in the Plugins section (it's the absolute last section in WHM's sidebar).

In there, you'll find basic options to control Nginx, Apache and MySQL, all in one convenient place. Additionally, you can edit all of Nginx's configuration files (as well as some from Apache & MySQL) to get even more from Engintron (e.g. configure Engintron for use with CloudFlare). If however all you want is to accelerate both static & dynamic content delivery, then Engintron is already setup for you and you don't need to do anything more.

Inside the Engintron app dashboard you'll also find some handy utilities to monitor things like your Nginx access & error logs, check processes on your server or see incoming traffic on ports 80 & 443 (HTTP & HTTPS traffic respectively).

_For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: [https://github.com/engintron/engintron/wiki](https://github.com/engintron/engintron/wiki)_


### Why is Engintron a better solution compared to other Nginx installers for cPanel

There are 9 key differences when comparing Engintron with other Nginx installers for cPanel.

First and foremost, caching actually works with Engintron. It works as it should and it works universally. You install it and ALL your cPanel websites will get accelerated, even the slowest ones. Not only that, your serving capacity will increase tremendously. Simple Apache Benchmark (ab) tests reveal a phenomenal increase in concurrent requests served per second, from just 3-300 in Apache to 15,000-20,000 or even more using Nginx via Engintron. It's our carefully crafted "black box" configuration that does all the magic. And it requires literally almost zero maintenance.

Second, Engintron is a single shell script (weighing only a few KBs) that installs all required software (to make Nginx work as intended) from the official software package vendors' repositories. Both installation and updates are very fast (they take only a few seconds).

Third, since we're using the official repositories for Nginx, all Engintron software is updated whenever cPanel (or the server's software) is updated. So you essentially set it and forget it. Whenever you perform "yum update/upgrade" or upgrade the server software from within WHM, Nginx will be updated if a new release is available. If something is changed on Engintron and you need to re-install it, you simply install it on top of the previous installation. You don't need to uninstall it first like other Nginx installer plugins for cPanel do! Oh, and it works from CentOS 5 up to CentOS 7.

Fourth, you can safely uninstall Engintron and it will *revert* your entire system to how it was before you installed Engintron. Simple as that. Which means you can try Engintron and if you don't like it or you find it doesn't fit your needs, you can simply uninstall it. Your system will revert to how it was before. Period.

Fifth, it has an amazingly simple yet practical app dashboard inside WHM with all the basic controls for Nginx, Apache, MySQL, the option to edit all important configuration files for these 3 services and even some handy utilities that make Engintron the dashboard in cPanel for your day-to-day sysadmin tasks. Think of it as your cPanel server's mission control. And did we mention you can easily update Engintron from within WHM? Yeap! You even get update notifications when a new version is available.

Sixth, it's CloudFlare friendly. Because both CloudFlare and Engintron use Nginx as a reverse caching proxy, unless we configure Nginx in cPanel to properly act as the secondary proxy (after CloudFlare of course), chances are that CloudFlare will freak out and serve your sites with 10xx errors. So, if you have any domains hosted on your cPanel server that use CloudFlare for their CDN, you just set your server IPs inside your "custom_rules" Nginx configuration file (the file is commented for your help) and just restart Nginx for the changes to take effect. All this is done entirely inside WHM of course. If additionally you use CloudFlare's SSL, by choosing "Flexible SSL" in CloudFlare's "Crypt" settings you can direct CloudFlare HTTPS traffic to your cPanel's HTTP port served by Nginx, thus further improving web serving over HTTPS as well. A true win-win situation.

Seventh, it doesn't require Nginx/Apache vhost synchronization when adding new domains via cPanel. That's why you essentially "set it and forget it". Have a look at the other Nginx installers... 'Nough said ;)

Eighth, Engintron allows for both HTTP and HTTPS traffic to flow through Nginx entirely, as of version 1.8.0.

And finally, Engintron is 100% open source. You can tear it apart, customize it, fork it, knife it or contribute back to its development. Do whatever you want with it :)


***
# NEW - Join the Engintron Newsletter / Mailing List
It's easy to miss an Engintron update on social media. If you want to know for sure when the latest version of Engintron is released, sign up to get notified directly to your inbox. We will never spam you.

Sign up here https://tinyletter.com/engintron or here https://engintron.com
***


### FAQ

The FAQ section has been moved in the Engintron Wiki: https://github.com/engintron/engintron/wiki/FAQ


### Changelog

The Changelog section has been moved in the Engintron Wiki: https://github.com/engintron/engintron/wiki/Changelog


### Compatibility & Requirements

Engintron is fully compatible with CentOS version 5, 6 and 7 on both 32-bit and 64-bit platforms. Additionally, users have already reported a 100% compatibility with CloudLinux versions 6 & 7.

Engintron is also compatible with both EasyApache 3 and EasyApache 4 as of version 1.7.0.


### Documentation

For more information regarding setup, configuration or uninstallation, as well as other cPanel optimization tips, please visit the project's Wiki pages at: https://github.com/engintron/engintron/wiki


### Feedback, bugs, feature requests & rating

Please post your feedback and any issues or feature requests/suggestions in the project's issue tracker at: https://github.com/engintron/engintron/issues

If you use Engintron, please take a moment to post a review and/or rating in the cPanel Applications Directory at: https://applications.cpanel.com/listings/view/Engintron-Nginx-on-cPanel


### Donate & support the development of Engintron
Does Engintron bring value to your business? If so, you can donate & support the development of Engintron at: https://engintron.com/?donate


### I need commercial support - do you offer such services?

If you wish to go the "extra mile" and optimize your cPanel server both through Engintron as well as through other services that directly affect the performance of your cPanel server (MySQL, Apache, PHP, certain system configuration files and more), feel free to use the contact options from within Engintron to get in touch with us.

Or you can simply email us at: engintron [at] gmail [dot] com


### License

Engintron is released under the GNU/GPL license. For more info, have a look here: [http://www.gnu.org/copyleft/gpl.html](http://www.gnu.org/copyleft/gpl.html)


==
### More info
A proper website is on its way, featuring short tutorials and videos, a forum and a commercial support channel.

If however you require commercial support now, you can contact us via Engintron's app dashboard or simply email us at: engintron [at] gmail [dot] com

https://engintron.com


==
Copyright &copy; 2014-2016 Fotis Evangelou / [Nuevvo Webware P.C.](http://nuevvo.com)
