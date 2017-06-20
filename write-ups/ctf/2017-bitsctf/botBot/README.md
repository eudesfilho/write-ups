BotBot - Web 10

First things first, lets look at the source code.

<!DOCTYPE HTML>
<!--
    Nothing to see here. Maybe try looking up seo .txt
-->

Ok, maybe there is nothing here. Next step is looking if the site has the robots.txt. We search for 
http://botbot.bitsctf.bits-quark.org/robots.txt and there we find 

Useragent *
Disallow: /fl4g

If we search for http://botbot.bitsctf.bits-quark.org/fl4, we receive the 404 not found. And that's because fl4g it's not a file,
but a directory. So we go to http://botbot.bitsctf.bits-quark.org/fl4g/ and find this

BITCTF{take_a_look_at_googles_robots_txt}
