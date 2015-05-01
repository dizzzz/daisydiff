# Finding differences in Text #

The diff problem for pure text is considered solved more or less. There are several
implementations which offer high quality results at minimal cost. Open-source
solutions (especially **GNU diff**) are also available.

It is also worth noting that in several cases we are not interested in word-level diffs but only on line changes. Typical examples include Source Code Management systems or Wiki applications. This makes the job of a text diff library very easy.

Fine-grained differences at the character level are also possible. **Google diff** for example can show differences in characters. For example it can understand that _horse_ and _horses_ differ in one character only.

# Finding differences in XML/HTML #

Comparing two XHTML files is a completely different story. HTML holds tree structured data so the problem is no longer trivial. A diff library must be essentially "smart" in order to understand what is an html tag and what is not. Changes can now happen in HTML attributes apart from simple text. HTML also contains advanced constructs likes lists and tables which complicate the output code.

HTML found in the wild can also be very rough for a diff library. Some pre-processing code is needed that cleans up the HTML before the actual comparison takes place.

There is a lot of research and literature on XML diffing methods. Unlike pure text, a definitive solution has not yet appeared.

# Diff software in Java #

Below is a table that lists other solutions apart from Daisy Diff

| **Algorithm** | **Type** | **Version** | **Licence** | **Last release** |
|:--------------|:---------|:------------|:------------|:-----------------|
| [Darwin Diff](http://www.darwinsys.com/freeware) | text | 0.9 | BSD | 2004 |
| [GNU Diff](http://www.bmsi.com/java/#diff) | text | 1.7 | GPL | January 2009 |
| [JBDiff](http://www.wombat.ie/software/jbdiff/downloads/) | text | 0.1.1 | BSD | October 2007 |
| [VMTools](http://www.vmsystems.net/vmtools/) | xml | 0.5 | VMtools Source Licence | February 2002 |
| [diffXML](http://diffxml.sourceforge.net/) | xml | 0.95Beta | GPL | May 2009 |
| [XMLDiff](http://www.alphaworks.ibm.com/tech/xmldiffmerge) | xml | 2001 | Alphaworks | March 2001 |
| [Jlibdiff](http://jlibdiff.sourceforge.net/) | text | 1.01 | GPL | February 2004 |
| [JDirDiff](http://sourceforge.net/projects/jdirdiff/) | text | 0.67 | GPL | June 2004 |
| [Google Diff](http://code.google.com/p/google-diff-match-patch/) | text | 20090804 | Apache Licence | August 2009 |
| [Diff MK](http://sourceforge.net/projects/diffmk/) | text | 3.0.a1 | GPL | March 2007 |
| [Java Diff](http://www.incava.org/projects/java/java-diff/) | text | 1.1.0 | LGPL | January 2009 |
| [XmlUNIT](http://xmlunit.sourceforge.net/) | xml | 1.2 | BSD | June 2008 |
| [jxydiff](http://potiron.loria.fr/projects/jxydiff) | xml | 2006 | QPL | Feb 2006|
| [delta XML](http://www.deltaxml.com/) | xml | V2 | Commercial | Oct 2009 |
| [Oracle XML Diff](http://www.oracle.com/technology/tech/xml/xdkhome.html) | xml | 10g | Commercial | 10g|
| [FC XML](http://code.google.com/p/fc-xmldiff/) | xml | 0.1 | MIT | Jun 2009 |
| [3DM XML](http://tdm.berlios.de/3dm/doc/index.html) | xml | 0.1.5beta1 | LGPL| March 2006 |
| [XOP](http://www.living-pages.de/de/projects/xop/index.html) | xml | 1.3| Research | October 2009 |
| [Diff X](http://www.topologi.com/diffx/) | xml | 0.7.1 | Artistic/GPL| October 2009 |

# What Daisy Diff offers #

One of the most important features of Daisy Diff is the fact that it "understands" HTML tags and will actually look into the text to decide if a node is same for not.

For example assume that a user has changed a single word in a big paragraph. Most XML libraries would just mark the whole paragraph as different. Daisy Diff however will look into the inline text (the contents of the p tag node) and understand that only one word is different. Therefore it will present to the user _only_ this word as changed.

DaisyDiff is also used in production (Daisy CMS) and also comes with a business friendly licence.
