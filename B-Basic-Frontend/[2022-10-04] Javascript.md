### Concepts

JavaScript is a scripting language that enables you to create dynamically updating content, control multimedia, animate images, and pretty much everything else.

### How does JavaScript run behind the scene?

- A computer system which we call a machine understand only machine code that is typically in a binary form. Our machine doesn’t understand any human readable i.e. high level programming language like Java, C#, JavaScript, Python etc. but understand only machine code.

- Now the question is how does the high level language like Java, C# code converts into machine language and execute the program. At this point Interpreter and Compiler comes into the picture. Both compiler and interpreters do the same job which is converting higher level programming language to machine code. However, a compiler will convert the code into machine code before program run which we call compilation phase. Interpreters convert code into machine code when the program is run.

- JavaScript executed by web browser. Each browser has a built-in interpreter that reads the JavaScript code in its original text form and runs the script from that. All modern JavaScript interpreters use a technique called just-in-time compilation to improve performance, the JavaScript source code gets compiled into a faster, binary format so that it can be run as quickly as possible. However, JavaScript is still considered an interpreter language, since the compilation is handled at run time, rather than ahead of time.

#### JavaScript Engine

- A browser program that read and execute JavaScript code behind the scene is called JavaScript Engine. Different web browser has different JavaScript Engine like V8 is uses by Google for google chrome, Chakra is uses by Microsoft for IE, JavaScriptCore is uses by Apple for safari, SpiderMoney uses by Mozilla for FireFox.

- “In earlier days JavaScript executed only by web browser.Today, JavaScript can execute not only in the browser, but also on the server or on any device that has a JavaScript engine.”

### How do we add JavaScript to web page?

JavaScript code inserted into web page inside <script> tag. We can write JavaScript code in HTML head and/or body tag or can refer an external file which contains JavaScript code. is in it very simple?

- Internal JavaScript-Write JavaScript code with HTML content inside <script> tag.
- External JavaScript-Write JavaScript code in external .js file and refer this file inside HTML page.