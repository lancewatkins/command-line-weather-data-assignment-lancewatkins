# SOS593 RDM Command Line Exercise
## Background
We have is some daily average weather data from [AzMet](https://cals.arizona.edu/AZMET/) in a csv file per weather station. There is some [meta data documentation](https://cals.arizona.edu/AZMET/raw2003.htm) explaining what each filename means and what each column represents.

## Goal
Use command line tools to subset the data for all sites for just the 43rd day of the year.

*Bonus Goal*: (For you over achievers) Do some simple Quality Control on the original data, document any oddities that you find in a new `data/QualityControlIssues.md` file.

# Tools you'll need

## grep
Search tool:
```
  grep searchfor filename.txt
```
## sed
String Processing, eg: to find and replace text per line:
```
  sed "s/searchfor/replacewith/g"
```

## wc
Count lines of file(s)
```
  wc -l filename.txt
```

# Instructions
 - Search for just the data collected on the 43rd day of the year, here is a starting point:
 `grep 43 data/*.txt` Once your happy with your search results write them to a file:

 `grep 43 data/*.txt > results/new.txt`

 *(If your reading these instructions and paying attention in our class lectures carefully then don't call your file new.txt, name it something better so that its clear what that file is or contains.)*
 - Now your search results are not quite right, they have the filename that the search match came from as the first thing on the line. It would be much more useful if that were in its own column. Since this is a CSV file we can do that with some simple find/replace sed magic! This should get you close:

 `sed "s/.txt:/,/g" results/new.txt`

 When your happy with your find and replacement command, output the results to another file ` > new-final.txt` *(again new-final.txt is the almost the worst name ever, please think of something better.)*
 - The first few lines of your final file should look something like this (but for the 43rd day of the year):
 ```
 01,2016,200,1,38.3,24,29.5,72.8,19.3,45.9,2.37,25.63,.76,36.8,23.8,28.9,26.8,26.1,26.3,1.9,.7,134,63,9.2,15.5,7.2,7.1,1.82,15.9
02,2016,200,2,41.1,26,33.5,64.5,13.7,34.2,3.73,27.77,0,26.8,25,25.9,26.4,26.2,26.3,2.2,1.5,173,45,7.5,16.3,8.8,8.3,1.61,13.8
04,2016,200,4,37.7,19.6,28.8,86.8,21,49.1,2.3,27.08,.51,36.2,29.2,32.5,29.6,29.4,29.5,3,.5,217,73,13.6,13.6,7.5,8,1.8,15.8
 ```
 - One last thing, as a log of what your did you can save your command history to a file and include that file along with your data by running this command:

 `history > results/captanslog-stardate-20170203.txt`

  *(20170203 is just a common date format, Year followed by Month and then Day. It sorts easier in this format, you'll thank me later)*


# Submission Instructions
You should have cloned this repository from a link provided. After you have created the requested files from the above instructions (and maybe the extra bonus goal as well) you will want to add them and commit them to git. From this folder you should run:
`git add -all` (to add all new files to the git repository) and `git commit -m "your commit message"` After this you should see a listing of what files have been changed, now you need to push these changes up to Github by running `git push origin master` (it may ask you to login with your github account). You should see your changes on [Github.com](https://github.com) now.
