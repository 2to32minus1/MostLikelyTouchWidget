# MostLikelyTouchWidget
First-draft prototype of better way to map touch (x, y) points to UI widgets to reduce near miss errors

A Method for More Intelligent Touch Event Processing

Link to slide deck: http://goo.gl/y4Mx4G

Link to Java source code Main.java: https://goo.gl/T9iwhL   NOTE: Lines end with just \n not \r\n

The above PDF slide deck summarizes ideas for reducing the frequency of accidentally invoking unintended UI widgets on touch devices. 

Included in the slide deck is the Java source code for a unit test harness which implements and tests the presented algorithm.  The unit test draws an overlay semi-transparent graphic which visualizes which widget is activated for each pixel in a mockup e-mail app.

Summary

• Desktop pointing devices (mice) have precise, single-pixel accuracy - touch devices do not

• Depending on device attributes, touch users are lucky to achieve an accuracy of 10-30+ pixels

• This causes many occurrences of: User intends to activate widget A but inadvertently activates nearby widget B

• The reason this problem exists is because touch device and OS OEMs assume that the legacy desktop single-pixel precision model will work well on touch devices - this is a poor assumption

• My recent experiment suggests that the frequency of inadvertent widget activations (event-to-unintended-widget mapping) can be improved

• The above URL slide deck summarizes a project I did over this past weekend to demonstrate that, for one simple UI at least, an algorithm for mapping touchevent (x,y) points to widgets which considers touchpoint-to-widget centroid distances as well as which widget's bounding rectangle contains the touchpoint (x,y) can provide the user with a parameterizable/tunable margin of error border around widgets which has the potential to substantially reduce the activation of unintended widgets

• I might add that inadvertently activating an unintended widget can be dangerous if the unintended widget were to, for example, open a malicious URL or e-mail

• More work is needed to evaluate and refine the proposed method in a variety of UI contexts, but I believe the presented algorithm has merit

Any feedback/comments are welcome (2to32minus1@gmail.com).
Copyright © 2013-2014 Richard Creamer - All Rights Reserved
