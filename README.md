# Usage  
Script to read a toggl detailed report output in CSV format. The total time spent on a tag or tags is given.  
Information was obtained after recording time spent on projects using toggl (https://track.toggl.com/).  
As the free account was used only data covering one year could be reported on at a time.  This script allows data from various years to be extract and concatonated for a full summary.  

options:  
  -h, --help            show this help message and exit  
  -i, --input INPUT     toggl detailed report in CSV format  
  -t, --tag TAG         tag with which to output total time spent, multiple tags can be input as a comma delimited string, e.g.
                        tag1,tag2  

# Example command line:  
python summarise_toggl_csv.py -i TogglTrack_anonymous_test.csv -t AB_20241112,NE_20241014  


# Example toggl input as CSV:  
"Description","Duration","Member","Email","Project","Tags","Start date","Stop date","Start time","Stop time"  
"NOVASEQ6000_241112#229_SP","21:57:42","Joe","j.blogs@gmail.com","-","DNA-seq, AB_20241112","2024-12-18","2024-12-18","15:30:00","17:27:42"  
"NOVASEQ6000_241112#229_SP","1:01:32","Joe","j.blogs@gmail.com","-","DNA-seq, AB_20241112","2024-12-18","2024-12-18","14:48:50","15:50:22"  
...  


# Notes on extracting CSV from toggl  
 - go to toggl reports (https://track.toggl.com/reports) and select the Detailed tab.   
 - click on the date range (top left and enter your range, e.g. one year 01/01/2024 - 12/31/2025.  The box may initially say "This week", but click on it to edit.  Also note US date convention (MM/DD/YYYY).  
 - click on Export (top right) and select CSV.


# Example output:  
Reading toggl report: TogglTrack_anonymous_test.csv  
       Tags Total_HHH_MM_SS  
AB_20241112        30:41:46  
NE_20241014         2:07:05  
Total time on selected tags: 32:48:51  


# Notes on using git:  
git init  
git add <file>  
git commit -m "msg"  
git remote add origin git@github.com:IanCodes/toggl_summary.git  
git push -u origin main  


# TO DO:  
- Output for date ranges  
- Plot bar graphs of totals / tag  
