JabRef's cleaner of Google's search results
===========================================

[JabRef](http://sourceforge.net/projects/jabref/) is a graphical application for managing bibliographical databases.

With this patch, in the JabRef's FieldEditor Context Menu is added additional feature of cleaning URLs pasted from Google's search results.

Many persons find URLs of materials on web using Google search. If they want to copy/paste URL from search results in JabRef, they will paste "dirty" URL that is "enriched" with many Google's meta data.

E.g. Google's Copy link address function return this link: https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&ved=0CC0QFjAA&url=http%3A%2F%2Fdspace.ou.nl%2Fbitstream%2F1820%2F1680%2F4%2FTowards-a-learning-path-specification.pdf&ei=b7LWUZbtBsmRtAbZq4D4BQ&usg=AFQjCNExs71F__T3MIJfUwwSv_Ws-hmfmQ&bvm=bv.48705608,d.Yms

You can paste it in the JabRef's URL text field. After that, using this patch functionality this URL is cleaned and transformed in real URL: http://dspace.ou.nl/bitstream/1820/1680/4/Towards-a-learning-path-specification.pdf

The patch is tested in last beta JabRef version 2.10. 

In this repository you can find patch file which you can apply on source code in repository (clean-google-url.patch) and in addition two java source files:
* src/java/net/sf/jabref/FieldTextMenu.java ( **changed** )
* src/java/net/sf/jabref/util/GoogleUrlCleaner.java ( **new** )


Instalation
------------

1. Download JabRef source from http://sourceforge.net/p/jabref/code/ci/master/tree/
2. Apply patch or manually put this files in repository
   * jabref/src/java/net/sf/jabref/FieldTextMenu.java
   * jabref/src/java/net/sf/jabref/util/GoogleUrlCleaner.java
3. Build JabRef from changed source.

Usage
-----

Find URL using Google and copy URL 
	
![Image](images/p1.png?raw=true)
 
Paste URL to JabRef's URL field 
 
![Image](images/p2.png?raw=true)

Right click on URL field and apply "Clean Google URL" functionality

![Image](images/p3.png?raw=true)

URL from Google's search results is cleaned. If URL is not candidate for cleaning, text in URL field stays the same.

![Image](images/p4.png?raw=true)
