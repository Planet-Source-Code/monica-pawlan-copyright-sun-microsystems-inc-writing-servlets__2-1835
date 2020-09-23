<div align="center">

## Writing Servlets


</div>

### Description

A servlet is an extension to a server that enhances the server's functionality. The most common use for a servlet is to extend a web server by providing dynamic web content. Web servers display documents written in HyperText Markup Language (HTML) and respond to user requests using the HyperText Transfer Protocol (HTTP). HTTP is the protocol for moving hypertext files across the internet. HTML documents contain text that has been marked up for interpretation by an HTML browser such as Netscape.

Servlets are easy to write. All you need is the Java® 2 Platform software, and JavaServerTM Web Development Kit (JWSDK). You can download a free copy of the JWSDK.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Monica Pawlan \(Copyright Sun Microsystems Inc\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/monica-pawlan-copyright-sun-microsystems-inc.md)
**Level**          |Intermediate
**User Rating**    |4.5 (18 globes from 4 users)
**Compatibility**  |Java \(JDK 1\.1\)
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__2-57.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/monica-pawlan-copyright-sun-microsystems-inc-writing-servlets__2-1835/archive/master.zip)





### Source Code

<p><font face="verdana,arial" size="4"><b>Servlets</b></font>
<p><font face="verdana,arial">A servlet is an extension to a server that
enhances the server's functionality. The most common use for a servlet is to
extend a web server by providing dynamic web content. Web servers display
documents written in HyperText Markup Language (HTML) and respond to user
requests using the HyperText Transfer Protocol (HTTP). HTTP is the protocol for
moving hypertext files across the internet. HTML documents contain text that has
been marked up for interpretation by an HTML browser such as Netscape.</font></p>
<p><font face="verdana,arial">Servlets are easy to write. All you need is the
Java® 2 Platform software, and JavaServer<font size="-2"><sup>TM</sup></font>
Web Development Kit (JWSDK). You can download a free copy of the <a href="http://java.sun.com/products/servlet/index.html" target="_blank">JWSDK</a>.</font>
<p><font face="verdana,arial">This lesson shows you how to create a very simple
form that invokes a basic servlet to process end user data entered on the form.</font>
<ul>
 <li><a href="#about"><font face="verdana,arial">About the Example</font></a>
 <li><a href="#html"><font face="verdana,arial">HTML Form</font></a>
 <li><a href="#serv"><font face="verdana,arial">Servlet Backend</font></a>
 <li><a href="#more"><font face="verdana,arial">More Information</font></a></li>
</ul>
<font face="Verdana, Arial, Helvetica, sans-serif">
<hr>
<a name="about"></a></font>
<h3><font face="verdana,arial">About the Example</font></h3>
<font face="verdana,arial">A browser accepts end user input through an HTML
form. The simple form used in this lesson has one text input field for the end
user to enter text and a Submit button. When the end user clicks the Submit
button, the simple servlet is invoked to process the end user input.</font>
<p><font face="verdana,arial">In this example, the simple servlet returns an
HTML page that displays the text entered by the end user.</font>
<p><font face="verdana,arial"><img src="http://www.planet-source-code.com/vb/tutorial/java/images/overview.gif">
<a name="html"></a></font>
<h3><font face="verdana,arial">HTML Form</font></h3>
<font face="verdana,arial">The HTML form is embedded in this <a href="http://www.planet-source-code.com/vb/tutorial/java/samples/simpleHTML.htm">HTML
file</a>. The diagram shows how the HTML page looks when it is opened in a
browser.</font>
<p><font face="verdana,arial"><img align="left" src="http://www.planet-source-code.com/vb/tutorial/java/images/form.gif" width="291" height="203">
The HTML file and form are similar to the simple application and applet examples
in <a href="http://exhiisprod01/vb/tutorial/java/default.asp?lngWId=2&txtTutorialName=BuildingUserInterface.asp">Lesson
4</a> so you can compare the code and learn how servlets, applets, and
applications handle end user inputs.</font>
<p><font face="verdana,arial">When the user clicks the <code>Click Me</code>
button, the servlet gets the entered text, and returns an HTML page with the
text.</font>
<p><font face="verdana,arial">The HTML page returned to the browser by the <a href="http://www.planet-source-code.com/vb/tutorial/java/samples/ExampServlet.java">ExampServlet.java</a>
servlet is shown below. The servlet code to retrieve the user's input and
generate the HTML page follows with a discussion.</font><font face="Verdana, Arial, Helvetica, sans-serif">
<p> </font>
<table border="2" cellPadding="0">
 <tbody>
 <tr>
  <td><font face="verdana,arial"><img src="http://www.planet-source-code.com/vb/tutorial/java/images/serv.gif" width="221" height="86"></font></td>
 </tr>
 </tbody>
</table>
<font face="Verdana, Arial, Helvetica, sans-serif">
<blockquote>
 <hr>
</font><font face="verdana,arial"><strong>Note:</strong> To run the example, you
have to put the servlet and <code>HTML</code> files in the correct directories
for the Web server you are using. For example, with Java WebServer 1.1.1, you
place the servlet in the <code>~/JavaWebServer1.1.1/servlets</code> and the <code>HTML</code>
file in the <code>~/JavaWebServer1.1.1/public_html</code> directory.</font><font face="Verdana, Arial, Helvetica, sans-serif">
<hr>
</blockquote>
<a name="serv"></a></font>
<h3><font face="verdana,arial">Servlet Backend</font></h3>
<font face="verdana,arial"><a href="http://www.planet-source-code.com/vb/tutorial/java/samples/ExampServlet.java">ExampServlet.java</a>
builds an HTML page to return to the end user. This means the servlet code does
not use any Project Swing or Abstract Window Toolkit (AWT) components or have
event handling code. For this simple servlet, you only need to import these
packages:</font>
<ul>
 <li><font face="verdana,arial"><code>java.io</code> for system input and
 output. The <code>HttpServlet</code> class uses the <code>IOException</code>
 class in this package to signal that an input or output exception of some
 kind has occurred.</font><font face="Verdana, Arial, Helvetica, sans-serif">
 <p> </p>
 </font>
 <li><font face="verdana,arial"><code>javax.servlet</code>, which contains
 generic (protocol-independent) servlet classes. The <code>HttpServlet</code>
 class uses the <code>ServletException</code> class in this package to
 indicate a servlet problem.</font><font face="Verdana, Arial, Helvetica, sans-serif">
 <p> </p>
 </font>
 <li><font face="verdana,arial"><code>javax.servlet.http</code>, which contains
 HTTP servlet classes. The <code>HttpServlet</code> class is in this package.</font></li>
</ul>
<pre><font face="verdana,arial">import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
public class ExampServlet extends HttpServlet {
 public void doPost(HttpServletRequest request,
	 HttpServletResponse response)
  throws ServletException, IOException
 {
 response.setContentType("text/html");
 PrintWriter out = response.getWriter();
 out.println("<title>Example</title>" +
  "<body bgcolor=FFFFFF>");
 out.println("<h2>Button Clicked</h2>");
 String DATA = request.getParameter("DATA");
 if(DATA != null){
  out.println(DATA);
 } else {
  out.println("No text entered.");
 }
 out.println("<P>Return to
	<A HREF="../simpleHTML.html">Form</A>");
 out.close();
 }
}
</font></pre>
<h3><font face="verdana,arial">Class and Method Declarations</font></h3>
<font face="verdana,arial">All servlet classes extend the <code>HttpServlet</code>
abstract class. <code>HttpServlet</code> simplifies writing HTTP servlets by
providing a framework for handling the HTTP protocol. Because <code>HttpServlet</code>
is <code>abstract</code>, your servlet class must extend it and override at
least one of its methods. An <code>abstract</code> class is a class that
contains unimplemented methods and cannot be instantiated itself.</font>
<pre><font face="verdana,arial">public class ExampServlet extends HttpServlet {
 public void doPost(HttpServletRequest request,
   HttpServletResponse response)
   throws ServletException, IOException
 {
</font></pre>
<font face="verdana,arial">The <code>ExampServlet</code> class is declared <code>public</code>
so the web server that runs the servlet, which is not local to the servlet, can
access it.</font>
<p><font face="verdana,arial">The <code>ExampServlet</code> class defines a <code>doPost</code>
method with the same name, return type, and parameter list as the <code>doPost</code>
method in the <code>HttpServlet</code> class. By doing this, the <code>ExampServlet</code>
class overrides and implements the <code>doPost</code> method in the <code>HttpServlet</code>
class.</font>
<p><font face="verdana,arial">The <code>doPost</code> method performs the <code>HTTP
POST</code> operation, which is the type of operation specified in the HTML form
used for this example. The other possibility is the <code>HTTP GET</code>
operation, in which case you would implement the <code>doGet</code> method
instead.</font>
<p><font face="verdana,arial">In short, <code>POST</code> requests are for
sending any amount of data directly over the connection without changing the
URL, and <code>GET</code> requests are for getting limited amounts of
information appended to the URL. <code>POST</code> requests cannot be bookmarked
or emailed and do not change the Uniform Resource Locators (URL) of the
response. <code>GET</code> requests can be bookmarked and emailed and add
information to the URL of the response.</font>
<p><font face="verdana,arial">The parameter list for the <code>doPost</code>
method takes a <code>request</code> and a <code>response</code> object. The
browser sends a request to the servlet and the servlet sends a response back to
the browser.</font>
<p><font face="verdana,arial">The <code>doPost</code> method implementation
accesses information in the <code>request</code> object to find out who made the
request, what form the request data is in, and which HTTP headers were sent, and
uses the <code>response</code> object to create an HTML page in response to the
browser's request. The <code>doPost</code> method throws an <code>IOException</code>
if there is an input or output problem when it handles the request, and a <code>ServletException</code>
if the request could not be handled. These exceptions are handled in the <code>HttpServlet</code>
class.</font>
<h3><font face="verdana,arial">Method Implementation</font></h3>
<font face="verdana,arial">The first part of the <code>doPost</code> method uses
the <code>response</code> object to create an HTML page. It first sets the
response content type to be <code>text/html</code>, then gets a <code>PrintWriter</code>
object for formatted text output.</font>
<pre><font face="verdana,arial">response.setContentType("text/html");
 PrintWriter out = response.getWriter();
 out.println("<title>Example</title>" +
  "<body bgcolor=#FFFFFF>");
 out.println("<h2>Button Clicked</h2>");
</font></pre>
<font face="verdana,arial">The next line uses the <code>request</code> object to
get the data from the text field on the form and store it in the <code>DATA</code>
variable. The <code>getparameter</code> method gets the named parameter, returns
<code>null</code> if the parameter was not set, and an empty string if the
parameter was sent without a value.</font>
<pre><font face="verdana,arial"> String DATA = request.getParameter("DATA");
</font></pre>
<font face="verdana,arial">The next part of the <code>doPost</code> method gets
the data out of the <code>DATA</code> parameter and passes it to the <code>response</code>
object to add to the HTML response page.</font>
<pre><font face="verdana,arial"> if(DATA != null){
  out.println(DATA);
 } else {
  out.println("No text entered.");
 }
</font></pre>
<font face="verdana,arial">The last part of the <code>doPost</code> method
creates a link to take the end user from the HTML response page back to the
original form, and closes the response.</font>
<pre><font face="verdana,arial"> out.println("<P>Return to
  <A HREF="../simpleHTML.html">Form</A>");
 out.close();
 }
</font></pre>
<font face="Verdana, Arial, Helvetica, sans-serif">
<blockquote>
 <hr>
</font><font face="verdana,arial"><strong>Note:</strong> To learn how to use the
other methods available in the <code>HttpServlet</code>, <code>HttpServletRequest</code>,
and <code>HttpServletResponse</code> classes, see <a href="http://java.sun.com/docs/books/tutorial/index.html" target="_blank">The
Java Tutorial</a> trail on <a href="http://java.sun.com/docs/books/tutorial/servlets/index.html" target="_blank">Servlets</a>.</font><font face="Verdana, Arial, Helvetica, sans-serif">
<hr>
</blockquote>
<a name="more"></a></font>
<h3><font face="verdana,arial">More Information</font></h3>
<font face="verdana,arial">You can find more information on servlets in the <a href="http://java.sun.com/docs/books/tutorial/servlets/index.html" target="_blank">Servlets</a>
trail in <a href="http://java.sun.com/docs/books/tutorial" target="_blank">The
Java Tutorial</a>.<br>
</font>
<hr>
<!--BEGIN READER SURVEY-->
<font size="2">
<p><font face="verdana,arial"><b>Reprinted with permission from the <a href="http://developer.java.sun.com/developer/" target="_blank">Java
Developer Connection(SM)</a><br>
Copyright <a href="http://www.sun.com" target="_blank">Sun Microsystems Inc</a>.</b></font></p>
</font>

