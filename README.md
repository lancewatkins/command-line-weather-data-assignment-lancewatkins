# SOS593 RDM Command Line Exercise
## Background
We have is some daily average weather data from [AzMet](https://cals.arizona.edu/AZMET/) in a csv file per weather station. There is some [meta data documentation](https://cals.arizona.edu/AZMET/raw2003.htm) explaining what each filename means and what each column represents.

## Goal
Use command line tools to subset the data for all sites for just one day.

*Bonus Goal*: Do some Quality Control on the original data, document any oddities that you find.

# Tools you'll need

## grep
Search tool:
```
  grep <needle> <files>
```
## sed
String Processing, eg: to find and replace text per line:
```
  sed "s/<needle>/<replacement>/g"
```

## wc
Count lines of file(s)
```
  wc -l filename.txt
```


# Submission Instructions
You should have cloned this repository from a link provided. After you have created the requested files you will want to add them and commit them. From this folder you should run:
`git add -all` and `git commit -m "your commit message"` After this you should see a listing of what files have been changed, now you need to push these changes up to Github by running `git push origin master` (it may ask you to login with your github account). You should see your changes on [Github.com](https://github.com) now.
