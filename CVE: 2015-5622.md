#Codepathwriteup
## CVE: 2015-5622

CVE-2015-5622

Cross-site scripting (XSS) vulnerability in WordPress before 4.2 allows authenticated users to inject arbitrary web script by leveraging the Author or Contributor role to place a crafted shortcode inside an HTML element.

1. Create a new post in wordpress by clicking on the + in the top left.
2. Make sure to switch to text, from the visual editor, in the top right corner of the window.
3. Enter sample code that triggers alert when you move your mouse over the link
    <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>
4. I got this prompt.

![CVE2015-5622](/wordpressbroke2.JPG)
