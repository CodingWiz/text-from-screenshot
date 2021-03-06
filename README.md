![](https://media.giphy.com/media/yuRlgieRkywwV6YhN2/giphy.gif)

# Text From Screenshot
This is a tool for copying text directly from a screenshot on macOS, using the built-in macOS screencapture tool and pytesseract. If you have any suggestions for improving the OCR, or have any feature requests, feel free to submit a Pull Request or open an Issue.

## Getting Started
To install the necessary packages, run:
```
pip install -r requirements.txt
```
The script is located in `text-from-screenshot` and can be run using  `./text-from-screenshot`. If you run into permission errors, run `chmod +x text-from-screenshot` to make the script executable.

## Setting up Automator Application
To create an Automator application so that you can just click and start the script automatically, open up Automator (it is installed by default on macOS), choose "Application" as the document type, then in the search bar on the left side of the screen search for "run" and double-click "Run Shell Script". Now, drag `text-from-screenshot` (the executable file) into the box. Hit save and save the application as "Text From Screenshot" (or whatever you want to name it) and you're good to go!

If the script works by itself, but you're running into an error along the lines of "tesseract file not found" when running the Automator application, that most likely means the path to tesseract is not correct (see [this Stack Overflow post](https://stackoverflow.com/questions/35609773/oserror-errno-2-no-such-file-or-directory-using-pytesser) for more information). You'll need to open up `pytesseract.py` (the path to your copy of `pytesseract.py` is given in the error message), and change the line `tesseract_cmd = 'tesseract'` to `tesseract_cmd = '/usr/local/bin/tesseract'`. The Automator application should now work.
