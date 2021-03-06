# markx

### anything => html

Markx is a command line tool for node.js to generate static sites.  It will convert markdown, jade and any code snippets into html.  It also has the ability to preview your files live with auto refresh.

Markx is great for github pages, phonegap projects and simple, static sites.

##Install

	npm install -g markx

##Usage

	Usage: markx [file]

	Options:

		-h, --help             output usage information
		-V, --version          output the version number
		-n, --nohl             Disable syntax highlighting
		-p, --preview <port>   Start a server to get a live preview
		-h, --head <file>      Custom head file
		-f, --foot <file>      Custom foot file
		-t, --template <file>  Jade template file

	Examples:

		# convert markdown and code blocks to html
		$ markx blog.md > blog.html

		# convert jade to html
		$ markx index.jade > index.html

		# convert markdown with jade template to html
		$ markx --template template.jade blog.md > blog.html

		# live preview of your markdown file
		$ markx --preview 8001 blog.md

		# live preview of your markdown file with a custom header/footer
		$ markx --preview 8001 --head head.html --foot foot.html blog.md

##Example

###Markdown
<pre>
#This is a heading

This is a paragraph

	var a = '123';
	var f = function() {
		return 4;
	}
</pre>

###Output
<pre>
&lt;h1&gt;This is a heading&lt;/h1&gt;
&lt;p&gt;This is a paragraph&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;&lt;span class="keyword"&gt;var&lt;/span&gt; a = &lt;span class="string"&gt;'123'&lt;/span&gt;;
&lt;span class="keyword"&gt;var&lt;/span&gt; f = &lt;span class="function"&gt;&lt;span class="keyword"&gt;function&lt;/span&gt;&lt;span class="params"&gt;()&lt;/span&gt; {&lt;/span&gt;
&lt;span class="keyword"&gt;return&lt;/span&gt; &lt;span class="number"&gt;4&lt;/span&gt;;
</pre>

###Set Syntax Language

If the auto detection isn't working, you can either pass in the language using --lang or you can set it in your markdown file using `[lang].  See below for an example.

<pre>
#This is a heading

This is a paragraph

	`javascript
	var a = '123';
	var f = function() {
		return 4;
	}
</pre>


##Live Preview
	
The `--preview` option lets you preview your markdown files before generating them as html.  When you open your browser to your live preview, you don't have to bother with refreshing every time you make a change to your markdown file, markx will automatically refresh your browser when it detects a change.  How cool is that?

##CSS for Syntax Highlighter

[Here](https://github.com/jgallen23/highlight.js/tree/master/src/styles) are some css files that will style the code blocks. 

##Support Languages

[Here](https://github.com/jgallen23/highlight.js/tree/master/src/languages) are the supported languages for syntax highlighting.

##History

###0.0.7
- added masher support

###0.0.6
- don't use default head/foot if jade
- convert on every refresh

###0.0.5
- jade as input file
- jade template file
- watch head/foot/template for changes

###0.0.4
- ability to set the syntax language in your markdown file using `[lang] as the first line of your code snippet

###0.0.3
- added custom headers (--head) and footer (--foot)

###0.0.2
- fixed auto refresh

###0.0.1
- initial release

##Future
- different themes for live preview
