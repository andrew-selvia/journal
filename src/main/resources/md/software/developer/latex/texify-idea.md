# TeXiFy-IDEA

If you are accustomed to writing code in a JetBrains IDE like IntelliJ IDEA and would like to utilize the same editor for writing LaTeX documents, you should take advantage of [TeXiFy-IDEA](https://github.com/Hannah-Sten/TeXiFy-IDEA). This plugin provides syntax highlighting and other deep integrations into the LaTeX ecosystem. Importantly, you can continue to leverage your experience with JetBrains IDEs (i.e. keyboard shortcuts, appearance, etc.).

TeXiFy-IDEA also supports [BibTeX](https://github.com/Hannah-Sten/TeXiFy-IDEA/wiki/Features#bibtex). For usage details, refer to [the documentation](https://github.com/Hannah-Sten/TeXiFy-IDEA/wiki/BibTeX). One word of advice if you're just adding a BibTeX bibliography to an existing document you've been compiling already with TeXiFy-IDEA in IntelliJ IDEA: wipe out the existing Run Configuration, then select the **Run**/**Play** button in the gutter of the main tex file to create the necessary Run Configurations now that your project uses BibTeX. TeXiFy-IDEA knows how to automatically create the 4 Run Configurations required to make this workflow work properly.    



If your bibliography citations show up as question marks, you may need to alter the bibtex run configuration. Specifically, the BibTeX run configuration has a **Working directory for bibtex** setting which needs to be assigned to the same path that's used for the **Directory for auxiliary files** setting of the main LaTeX run configuration.
