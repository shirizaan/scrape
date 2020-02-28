# scrape
A wrapper for Skyscraper that allows for parallel scraping from all online sources.

This is a CLI wrapper for Skyscraper by Lars Muldjord.

Skyscraper can be obtained from https://github.com/muldjord/skyscraper or by installing it through the RetroPie-Setup script which can be found at https://github.com/RetroPie/RetroPie-Setup.

Skyscraper is already very powerful on it's own, and while it supports mutlithreaded scraping from a single online source, there is no supported way to scrape from all sources at the same time. This wrapper solves that. This wrapper also adds two "pseudo" systems that are not supported by Skyscraper natively: PCEngined-CD and Neo Geo CD.

### Requirements

#### Linux

scrape needs Python 3.7 or later to run. It should already be installed on most Linux distros, but if it isn't, you can install it by typing:
```
sudo apt update
sudo apt install python3
```

scrape also requires jdupes as it hard links files that are identical in the Skyscraper cache to save as much space as possible. You can install it by typing:
```
sudo apt update
sudo apt install jdupes
```

Finally, install scrape itself by typing:
```
git clone https://github.com/shirizaan/scrape.git
```

### Configuration


## How to use scrape
IMPORTANT!! Because scrape is just a wrapper for Skyscraper, you must exit EmulationStation before running it or else the changes made to your gamelist.xml files will be overwritten when the RetroPie is restarted.

### Simple Mode
At it's simplest, run scrape by typing:
```
cd scrape
scrape <system>
```
Then just sit back and relax. scrape will launch 8 copies of Skyscraper, each pulling from a different online source. Once all online sources have been polled, it will then clean up the Skyscraper cache before rebuilding the gamelist.xml file and media folder from the local files.

### Advanced Options