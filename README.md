# linux-administration-lab-5---ip-networking---dhcp-solved
**TO GET THIS SOLUTION VISIT:** [Linux Administration Lab 5 – IP Networking – DHCP Solved](https://www.ankitcodinghub.com/product/linux-administration-lab-5-ip-networking-dhcp-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;119275&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Linux Administration Lab 5 - IP Networking - DHCP Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
Michael Scott and Dwight Schrute recently filmed an advertisement to air on the local NBC television station, WBRE. The ad includes the URL of the website for the local Scranton branch of Dunder-Mifflin.

Michael is worried that the current system will be unable to handle the extra traffic and demands that a backup web server be set up – in case the existing server catches fire from the increased load. While maybe a bit of an overreaction, he is wise, at least, to consider what might happen to the web server when the ad goes live.

Despite your best efforts to convince Michael that overloaded computers can’t catch fire, he insists that you set up a standby web server before the advertisement airs. You agree to Michael’s request on one condition – that you’ll also implement a couple of long overdue changes to centralize the administration of the network – namely the DHCP (Dynamic Host Configuration Protocol) and DNS (Domain Name System) services.

What’s needed to setup DHCP?

First, you’ll need to install the DHCP daemon that serves IP addresses and other configuration information:

The hosts on our production network are servers, so we want them to have fixed IP address. Create a static MAC to IP mapping on Machine A:

You’ll also want to configure the dhcp server to set the appropriate hostname on all the machines. Finally, you’ll need to figure out how to get machines B through F to pick up the configuration from machine A’s dhcp daemon by modifying the appropriate ifcfg file in /etc/sysconfig/network-scripts.

What’s needed to set up a new web server?

Once machine F is properly configured as a host on the network, install a daemon to service http requests. This is most often the daemon known as Apache or httpd::

You’ll also need to copy the web content from the old web server to the new one. The rsync tool, which can reliably transfer files over ssh, can do this. First install rsync on both machines:

Then push contents of /var/www/ on machineb to /var/www/ on machinef:

Realize that this will only push the contents once. What we really need is to have the machines stay in sync by pushing the content on a periodic basis. See Using Public/Private Keys for SSH Authentication to have a process log into another machine without requiring a password.

Submission Requirements

1. Please submit your notes as a .txt or .pdf file.

3. All clients (B, C, D, E, and F) should be configured to pull network configuration via dhcp.

4. All local servers and the vpn should be able to reach ssh (port 22) on Machine F at address 100.64.N.5.

5. Machine F should have the same user/group/permissions configuration as machine B. Machine F should periodically (e.g. hourly) pull a copy of the server configuration and web content from /var/www/ on machine B. Cron must be used for this.

Hints &amp; Troubleshooting

The existing public key in /root/.ssh/authorized_keys labeled saclass-admins@donotremove must remain on all production machines, otherwise I won’t be able to login and grade your work.

5113 Extra Challenge

Make the update process between machines B and F bidirectional.
