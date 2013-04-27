simpleconvert-xml
=================
**(c)[Bumblehead][0], 2013** [MIT-license](#license)  

### OVERVIEW:

simpleconvert-xml will convert xml nodes into a javascript object or it will convert a javascript object into xml nodes.

What's good about simpleconvert-xml:  

 - usable in a browser environment or with node.js (with [xmldom][2])
 - special xml-formatting will identify single-element arrays

It is not a comprehensive solution for xml conversion. See the examples below to find out what scenarious this script is best for.

[0]: http://www.bumblehead.com                            "bumblehead"
[1]: https://developers.google.com/gdata/docs/json    "gdata-standard"
[2]: https://npmjs.org/package/xmldom                         "xmldom"


---------------------------------------------------------  
#### <a id="install"></a>INSTALL:

simpleTime may be downloaded directly or installed through `npm`.

 * **npm**   

 ```bash
 $ npm install simpleconvert-xml
 ```

 * **Direct Download**
 
 ```bash  
 $ git clone https://github.com/iambumblehead/simpleconvert-xml.git
 ```

---------------------------------------------------------
#### <a id="test"></a>TEST:

 to run tests, use `npm test` from a shell.

 ```bash
 $ npm test
 ```

---------------------------------------------------------
#### <a id="get-started">GET STARTED:

 1. **Before Starting...**   

 Where xmlNode is a result of the same xml file both examples would produce the same output.

 > *node.js environment*

 > ```javascript
   var DOMParser = require('xmldom').DOMParser,
       simpleConvertXML = require('simpleConvertXML');  
  
   xmlNode = new DOMParser().parseFromString(xmlFormattedStr);
   obj = simpleConvertXML.getXMLAsObj(xmlNode);
   console.log(obj);
   ```
   
 > *browser environment*

 > ```javascript
   obj = simpleConvertXML.getXMLAsObj(xmlNode);
   console.log(obj);
   ```   
   
---------------------------------------------------------
#### <a id="methods">METHODS:   
      
 - **getXMLAsObj( _xmlNode_ )**        
   convert an object into an xml string
   
   ```javascript
   var SimpleConvertXML = require('simpleConvertXML'),
       DOMParser = require('xmldom').DOMParser;
   var xmlNode, testXMLStr = "" +
     "<data>\n" +
     "  <price>$15.98</price>\n" +
     "  <happy>\n" +
     "    <say>I'm happy</say>\n" +
     "    <respond>you're happy</respond>\n" +
     "    <conclude>we're all happy</conclude>\n" +
     "  </happy>\n" +
     "  <isFinal>true</isFinal>\n" +
     "</data>";  
   xmlNode = new DOMParser().parseFromString(testXMLStr);
   console.log(SimpleConvertXML.getXMLAsObj(testDoc));    
   // { 
   //   data : { 
   //     price: '$15.98',
   //     happy: { 
   //       say: 'I\'m happy',
   //       respond: 'you\'re happy',
   //       conclude: 'we\'re all happy' 
   //     },
   //     isFinal: 'true' 
   //   } 
   // };   
   ```
 
 - **getObjAsXMLstr( _object_ )**           
   boolean, is the given date object a valid date object?   
      
---------------------------------------------------------
#### <a id="license">License:

(The MIT License)

Copyright (c) 2013 [Bumblehead][0] <chris@bumblehead.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
      