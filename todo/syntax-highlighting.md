# Syntax Highlighting

Deciding how to add syntax highlighting within code blocks on your website is no small feat. There are various different tools premised upon different architectures. The documentation below attempts to provide a guide to some currently popular approaches.

## Goals

The criteria which influenced the syntax highlighting system & theme on this website are included below for context:

* Extensive language support
    * Scala
    * Swift
    * Shell scripts
    * Many more...
* Actively-maintained, open-source code repository
* Lightweight integration & maintenance costs 
* Related dark **and** light themes
* Tasteful use of color
	* Diverse palette: easy differentiation of elements
	* Avoidance of dark hues: warmer colors are less alarming
	* Lukewarm tones: bright neons are too alarming
* Consistency across tools
	* JetBrains IDEs
	* Xcode
	* Web

## Tools

The following tools were considered for the syntax highlighting of this website:

* [highlight.js](https://highlightjs.org)
* [Prism](https://prismjs.com)
* [Linguist](https://github.com/github/linguist)
* [Pygments](https://pygments.org)
* [Rouge](https://github.com/rouge-ruby/rouge)
* [code-prettify](https://github.com/googlearchive/code-prettify)

### highlight.js

In the end, highlight.js was the simplest to integrate into the website. The [usage documentation](https://highlightjs.org/usage) clearly describes how to get started. The [demo](https://highlightjs.org/static/demo) made it easy to explore the various themes as well. It checked all the boxes.

## Prism

Compared to highlight.js, Prism proved slightly more difficult to integrate into this website due to its different naming scheme for fenced code blocks. For example, rather than "scala", Prism expects "code.language-scala". While such a modification is achievable, it was an unnecessary hurdle at the gate.

In reality, Prism looks slightly more modern and standards-compliant than highlight.js. In the future, it may be worth revisiting it for this website.  

### Linguist

According to [this StackOverflow answer](https://stackoverflow.com/a/53709148/6073927), Linguist (which was originally created & used by GitHub) is not really meant for syntax highlighting:

> Linguist only detects the language of files; [it doesn't perform the highlighting itself](https://github.com/github/linguist#theres-a-problem-with-the-syntax-highlighting-of-a-file).

Also, according to GitHub's own documentation, [Linguist delegates syntax highlighting to third-party grammars](https://docs.github.com/en/github/writing-on-github/creating-and-highlighting-code-blocks#syntax-highlighting):

> We use Linguist to perform language detection and to select third-party grammars for syntax highlighting. 

### Pygments

Pygments has been used by some major websites (i.e. Wikipedia, GitHub, etc.), lending it serious credibility. However, it seems [GitHub has moved away from it](https://www.greghendershott.com/2014/11/github-dropped-pygments.html) for performance reasons based on some online discussions. It seems to be an older solution overall. Additionally, compared to highlight.js results, Pygments produced less differentiated results; some elements which were differentiated by highlight.js were conjoined by Pygments. Obviously, the sample size of this testing was small, so account for that. Finally, it was significantly more difficult to integrate. Nonetheless, if you do want to explore the various themes, you can do so at [this website](https://stylishthemes.github.io/Syntax-Themes/pygments). If you want to experiment with it further, you can try out [the demo](https://pygments.org/demo).

The research process for this website also unveiled some interesting projects in the Pygments ecosystem. They are listed below:

* [nord-pygments](https://github.com/lewisacidic/nord-pygments)
* [nord_pygments](https://github.com/sbrisard/nord_pygments)
* [SwiftSyntaxHighlighter](https://github.com/NSHipster/SwiftSyntaxHighlighter): A syntax highlighter for Swift code that uses SwiftSyntax to generate Pygments-compatible HTML.
* [SwiftSyntax](https://nshipster.com/swiftsyntax)
* [pygments-darcula](https://github.com/kakawait/pygments-darcula): Brings the Darcula theme from JetBrains IDEs to Pygments.

### Rouge

Rouge is the least researched among the group. Its proximity to Ruby did not align with this website's goals. However, if you want to explore Rouge's available themes, you can do so [here](https://spsarolkar.github.io/rouge-theme-preview).

### code-prettify

Google's involvement lent this project some credibility at first, but it quickly became clear that it is not actively maintained.
	
## Themes

Literally dozens of themes were considered for use on this website, but these few stood up best to the criteria which led the search.

### Base16

The [Base16](https://github.com/chriskempson/base16) project drastically simplifies discovery and integration of many popular themes within a diverse set of clients (i.e. JetBrains IDEs, Xcode, etc.). [This preview tool](http://chriskempson.com/projects/base16) makes it easy to experiment with all the available themes. When you need to decide on a pleasant theme for your project, start here.

### Dracula

The [Dracula theme](https://draculatheme.com) stands out due to its remarkable website which documents how to integrate it into over 100 tools. If only all themes had such great documentation. While it was very tempting, the bright neon colors proved too distracting for this website.

### Nord

The [Nord theme](https://www.nordtheme.com) is elegant and minimalist. It even has a stunning [JetBrains IDE integration](https://plugins.jetbrains.com/plugin/10321-nord). Despite its charm, actual usage proved Nord offers too little differentiation between elements. It is also worth mentioning that [it iss not actively maintained](https://twitter.com/arcticicestudio/status/954067233067675650).

### One Dark

Of all the themes investigated for this website, Atom's One Dark theme came out on top due to its bright color palette, rich integrations, and sibling light theme.

#### References

* [One Dark JetBrains IDE Theme](https://plugins.jetbrains.com/plugin/11938-one-dark-theme)
* [xcode-one-dark](https://github.com/bojan/xcode-one-dark)
* [one-dark-syntax](https://github.com/atom/atom/tree/master/packages/one-dark-syntax)