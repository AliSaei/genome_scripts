#Lab Meeting 9/16/2015#

___
####Introduction to UNIX and Command line Bioinformatics####

___
######There are many ways to set up your Mac, here is how I would do it. (type or copy/paste commands into terminal)######

######Need to install Xcode (Developer Tools that Apple doesn’t install natively but supports):######
```xcode-select --install```

######Install HomeBrew (copy and paste this into terminal):######

```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”```

Then setup homebrew:
```brew doctor
brew tap homebrew/science```

######Install some tools (GNU tools, python, CPAN, BLAST, HMMer3):######
```brew install coreutils python cpanm blast hmmer```

######Install BioPython######
```pip install biopython```

######Install BioPerl (CPAN is a helper script to install Perl Modules)######
```sudo cpanm BioPerl```

######Install a good Text Editor, my favorite is Text Wrangler which also has command line tools that are useful######
```https://s3.amazonaws.com/BBSW-download/TextWrangler_4.5.12.dmg
http://pine.barebones.com/files/tw-cmdline-tools-4512.zip```

GitHub is a repository for programs, scripts, etc.  It is free and public.  Lots of bioinformatics scripts reside on GitHub, and it can make it easy to install/update/share software:  My github repo: `https://github.com/nextgenusfs`

Let’s say you want to install the scripts used in Kurt’s paper (download NCBI genomes), type following into terminal:
First, move into desired folder to copy the folder of scripts to – a common place is the /usr/local folder.
```cd /usr/local
git clone https://github.com/nextgenusfs/NR-PKS_ms.git```

This will download all of the scripts from the github repo into a folder named ‘NR-PKS_ms’ in your current directory.

So you could now run the script by typing the following:
```/usr/local/NR-PKS_ms/get_ncbi_genomes.py```

Since this is cumbersome and you have to type the entire path each time, there is a shortcut known as your environmental $PATH – essentially which folders the system searches for scripts (homebrew does this for you, github does not). This is controlled by a file called ~/.bash_profile.  If you have TextWrangler command line installed, type.
```edit ~/.bash_profile   #will create a new file```

Type the following into the text file and save it (will require password):
```export PATH=”/usr/local/NR-PKS_ms:$PATH”```

Now in terminal you can type (this will refresh your terminal session and load in the ~/.bash_profile)
`source ~/.bash_profile`

Now you can simply type the name of the script, i.e.:
```get_ncbi_genomes.py -h```
