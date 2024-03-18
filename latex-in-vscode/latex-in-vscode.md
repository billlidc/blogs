# Writing LaTeX with LaTeX Workshop in VS Code




### Steps



1. Download & Install ```MacTex```: [Downloading MacTeX 2024](https://tug.org/mactex/mactex-download.html)


2. Install the extension ```LaTeX Workshop``` in VS Code
    * PDF reading in VS Code is enabled once the extension is installed


3. Press ```Cmd``` + ```Shift``` + ```P``` (macOS) in VS Code to show all commands and type in ```Open User Settings JSON```


4. Copy and paste the snippets into the json file (inside the brackets {}).


    ```
    {
    "workbench.colorTheme": "Visual Studio Dark",
    "latex-workshop.latex.path": "/Library/TeX/texbin/pdftex",
    "latex-workshop.latex.tools": [
        {
         "name": "latexmk",
         "command": "latexmk",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "-pdf",
          "-outdir=%OUTDIR%",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "xelatex",
         "command": "xelatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "pdflatex",
         "command": "pdflatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "bibtex",
         "command": "bibtex",
         "args": [
          "%DOCFILE%"
         ],
         "env": {}
        }
       ],
       "latex-workshop.latex.recipes": [
        {
         "name": "pdfLaTeX",
         "tools": [
          "pdflatex"
         ]
        },
        {
         "name": "latexmk 🔃",
         "tools": [
          "latexmk"
         ]
        },
        {
         "name": "xelatex",
         "tools": [
          "xelatex"
         ]
        },
        {
         "name": "pdflatex ➞ bibtex ➞ pdflatex`×2",
         "tools": [
          "pdflatex",
          "bibtex",
          "pdflatex",
          "pdflatex"
         ]
        },
        {
        "name": "xelatex ➞ bibtex ➞ xelatex`×2",
        "tools": [
          "xelatex",
          "bibtex",
          "xelatex",
          "xelatex"
         ]
        }
       ]       
    }
    ```


5. Troubleshooting ```Recipe terminated with fatal error: spawn pdflatex ENOENT```

    * Check install path on macOS with ```$ which pdftex```; If it doesn't, you'll have to re-install MacTeX.


        ```
        (base) maverick@Daochens-MacBook-Pro ~ % which pdftex
        /Library/TeX/texbin/pdftex
        ```

    * Check LaTeX version: ```latex -v```; Sample output is shown below.


        ```
        (base) maverick@Daochens-MacBook-Pro ~ % latex -v
        pdfTeX 3.141592653-2.6-1.40.26 (TeX Live 2024)
        kpathsea version 6.4.0
        Copyright 2024 Han The Thanh (pdfTeX) et al.
        There is NO warranty.  Redistribution of this software is
        covered by the terms of both the pdfTeX copyright and
        the Lesser GNU General Public License.
        For more information about these matters, see the file
        named COPYING and the pdfTeX source.
        Primary author of pdfTeX: Han The Thanh (pdfTeX) et al.
        Compiled with libpng 1.6.43; using libpng 1.6.43
        Compiled with zlib 1.3.1; using zlib 1.3.1
        Compiled with xpdf version 4.04
        ```

    * Relaunch VS Code after copying the snippets in step 4.


6. Compile the file using ```option``` + ```Cmd``` + ```B``` (macOS)

* To uninstall MacTex: [Uninstalling](https://tug.org/mactex/uninstalling.html#:~:text=In%20the%20Finder)



### References
* [A Fast Guide on Writing LaTeX with LaTeX Workshop in VS Code](https://mathjiajia.github.io/vscode-and-latex/)
* [LaTeX install path on OS X](https://tex.stackexchange.com/questions/79463/latex-install-path-on-os-x)
* [LaTeX via VS Code, macOS, solving 'Recipe terminated with fatal error: spawn latexmk ENOENT.' error](https://stackoverflow.com/questions/72834326/latex-via-vs-code-macos-solving-recipe-terminated-with-fatal-error-spawn-lat)