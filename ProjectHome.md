The newest source code is available here, http://github.com/talltyler/HTMLWrapper
This site will remain here for legacy versions of the code Wrapper code base.

Wrapper is a cross-browser compliant HTML/CSS rendering engine written in ActionScript that sits on top of your standards compliant HTML page. Wrapper eliminates cross-browser issues and makes integrating ActionScript and HTML/CSS projects possible without needing to compile every change.

Wrappers strives to answer the most common problems web designers face without forcing them to learn too many new things. Wrapper is fully accessible to the search engines and can integrates well with any back-end technology.
There are a few differences between standard HTML and CSS then what can be rendered in Wrapper and most of the differences are to simply expose the great features of the Flash Player already has to HTML and CSS.

Wrapper has gone through many changes over the years to refine it's functionality to facilitate larger applictions. Development time has been split between improving speed adding features. The newest version of Wrapper supports many of the new HTML5 and CSS3 properties like audio and video tags and corner radius and gradient fills. Along with many internal changes so that ActionScript is able to more easily interface with the elements that the engine has rendered.

I know the video tags is what everyone is talking about but in my mind the most impressive changes in HTML5 are happening within form and input tags and Wrapper is trying to keep up with all of these changes. Features like being able to validate values with regular expressions or min and max length attributes. Also new components like builtin calendar date pickers and range sliders. There is a great article about these changes here, http://diveintohtml5.org/forms.html

Interfacing with pages after they have been rendered is just like using JavaScript, you can say document.getElementById or document.getElementsByClassName and return Element objects. You can then manipulate these objects by changing there style or by manipulating there ActionScript properties. If you want to add mouse events or whatever other type of event this event would just be added to the element. If the application that you are working on needs a little more control inside of ActionScript try out ASTRID, an ActionScript MVC framework that uses HTMLWrapper as one of it's renderers http://github.com/talltyler/ASTRID

Wrapper is released in a few different forms and versions but all versions where made in ActionScript 3 and can be used in any of the Adobe runtimes, AIR, Flash Player, and used in the Flex framework if needed.
Documentation and examples can be found in the wiki and news about this project can be found at http://motionandcolor.com

Source code for the newer version is available here
http://github.com/talltyler/HTMLWrapper

Source code for the older version is here
http://code.google.com/p/htmlwrapper/source

If you would like to help add anything to the project your ideas and hard work are always welcome. Just join the mailing list of the group and post a message about your thoughts.