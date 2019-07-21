# CSV Dedupe Workshop

Prepared July 2019 for a [Helena Civic Data meetup](https://www.meetup.com/Helena-Civic-Data-Group/events/263183604/).

Presentation: https://docs.google.com/presentation/d/1YB7A2X1ImZR7343JgjvqhWCv3cNtvUb-MD-U872u1n4/edit?usp=sharing

Google sheet: https://docs.google.com/spreadsheets/d/1Smv_txuwLdTcBg_SRBpGyxPCEfaRA0qj8SSC70P0db8/edit?usp=sharing

## Resources/background reading:
- Installing Python & pipenv (Mac or Windows): https://bit.ly/ire-install-python
- What the hell is Git?
    - https://hackernoon.com/understanding-git-fcffd87c15a3
    - https://hackernoon.com/a-gentle-introduction-to-git-and-github-the-eli5-way-43f0aa64f2e4
- Using the terminal on Mac: https://mac.appstorm.net/how-to/utilities-how-to/how-to-use-terminal-the-basics/ 
- Git bash (recommended way to get a Mac-like terminal on Windows): https://gitforwindows.org/
- Dedupe.io company website: https://dedupe.io/
- csvdedupe on Github: https://github.com/dedupeio/csvdedupe

## What's in this repo(sitotory)

- Simple .csv example file: `csv-demo.csv`
- Source data files of several sizes:
    - `mtleg-2018-individual-contributions-abbreviated-at-33.csv`
    - `mtleg-2018-individual-contributions-abbreviated-at-500.csv`
    - `mtleg-2018-individual-contributions-abbreviated-at-2500.csv`
    - `mtleg-2018-individual-contributions-full.csv`
- Example config files for csvdedupe:
    - `config-abbreviated.json`
    - `config-full.json`
    - `config-skip-training.json`

## Workshop commands

**Install Python & pipenv on your machine per first link above.

### Navigation in Mac/Linux-style terminals

Show current file path (Present Working Directory): `pwd`

LiSt contents of current directory: `ls`

Change Directory: `cd new-directory-or-file-path`

### Set up a Python virtual environment with csvdedupe

From your project directory
`pipenv install csvdedupe`

_Note: This is slightly different than recommendation in csvdedupe docs_

### Download this repo

If Git is installed on your computer (`brew install git` first if not)



OR: Download zipfile using Github interface

### Run csvdedupe

On small (500 row) sample of data - recommended for initial attempt for sake of speed
`sh
pipenv run csvdedupe mtleg-2018-individual-contributions-abbreviated-at-500.csv --config_file config-abbreviated.json
`

On complete (16,000 row) data set - make take several minutes to process, depending on your computer
`sh
pipenv run csvdedupe mtleg-2018-individual-contributions-full.csv --config_file config-full.json
`

## About the data used here

This is individual contribution data for 2018 Montana Legislative candidates, obtained from the Montana Commissioner of Political Practices office web registry using a web scraping script in Feb. 2019. Includes primary and general election contributions, with most non-individual and in-kind contributions removed.

Data hasn't been thouroughly checked for completeness or errors and contains some known head-scratchers. If you want to use this for something other than a tutorial exercise, contact me at edietrich@montanafreepress.org.