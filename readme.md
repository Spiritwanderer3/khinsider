# khinsider-fixed.py

`khinsider-fixed.py` is a maintained fork of the original khinsider.py downloader script for khinsider soundtracks. this fork improves reliability by adding user-agent headers to every HTTP request, helping prevent the script from being blocked by the site and restoring its functionality.
usage from the command line is simple:

```cmd
khinsider-fixed.py pesterquest-ost-2019
```

or as a python module:

```python
import khinsider-fixed
khinsider-fixed.download('pesterquest-ost-2019')
# you now have the pesterquest soundtrack!
```

## About this fork
this repo is maintained by someone very new to programming who fixed the downloader to work again by adding user-agent headers. thank you obskyr for making the original!!!

if you find bugs or want to help improve it, contributions and feedback are very welcome! you can contact me at https://twitter.com/stranger_to_be . (the rest of this description is the same as the original, only slightly edited.) 

## Usage

just run khinsider-fixed.py from the command line with the sole parameter being the soundtrack you want to download. you can either use the soundtrack’s id, or simply copy its entire url. easy!

if you want, you can also add another parameter as the output folder, but that’s optional.

you can also download other file formats (if available), like flac or ogg, as following:

khinsider-fixed.py --format flac mother-3

if you don’t want to go to the actual site to look for soundtracks, you can also just type a search term as the first parameter(s), and provided it’s not a valid soundtrack, khinsider-fixed.py will give you a list of soundtracks matching that term.

you’re going to need python (if you don’t know which version to get, choose the latest version of python 3 - khinsider-fixed.py works with both 2 and 3), so install that (and add it to your path) if you haven’t already.

you will also need to have pip installed (if you have python 3, it is most likely already installed - otherwise, download get-pip.py and run it) if you don’t already have requests and beautiful soup 4. the first time khinsider-fixed.py runs, it will install these two for you.

for more detailed information, try running khinsider-fixed.py --help!

## As a module

khinsider-fixed.py requires two non-standard modules: requests and beautifulsoup4. just run a pip install on them (with pip), or just run khinsider-fixed.py on its own once and it'll install them for you.

here are the main functions you will be using:
khinsider_fixed.download(soundtrackName[, path="", makeDirs=True, formatOrder=None, verbose=False])

download the soundtrack soundtrackName. this should be the name the soundtrack uses at the end of its album url.

if path is specified, the soundtrack files will be downloaded to the directory that path points to.

if makeDirs is true, the directory will be created if it doesn’t exist.

you can specify formatOrder to download soundtracks in specific formats. formatOrder=['flac', 'mp3'], for example, will download flacs if available, and mp3s if not.

if verbose is true, it will print progress as it is downloading.
khinsider_fixed.search(term)

search khinsider-fixed for term. return a list of soundtracks matching the search term. you can then access soundtrack.id or soundtrack.url.

### More

there’s a lot more detail to the api - more than would be sensible to write here. if you want to use khinsider-fixed.py as a module in a more advanced capacity, have a look at the soundtrack, song, and file objects in the source code! they’re documented properly there for your reading pleasure.
