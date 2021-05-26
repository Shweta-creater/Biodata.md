<h2 align="center">Task-4</h2>

<h2 align="center"> OBJECTIVE: </h2>

 <p align="center"> Create a test script that checks the reliability of the evaluation script. <p>


<details>
  <summary> Summary of Task </summary>
  <ul>
    <br>
    <li> Write a script in Shell.</li>
    <li> This script has been used to download 2 google sheets. </li>
    <li> Both of those Google sheets will have the formate csv file. </li>
    <li> Only the name, Average and Sum columns and their values should be printed. </li>
     <li>After that we get the downloaded seat compaired from our existing seat.</li>
  </ul>
</details>

<details>
<summary> INDEX </summary>
  <ul>
    <br>
    <li> Test cases</li>
    <li> Implementation </li>
    <li> Script </li>
   <li> Configuration </li>
    <li> Log file </li>
    <li> Conclusion </li>
  </ul>
  </details>
  
<details>
<summary> Details </summary>
  <ul>
    
<details>
  <summary> Test Cases </summary>
  
|S.NO|Test Cases|Test Case Description|Expected Result|Test Status
|:----:|:-----:|:-----:|:-----:|:-----:|
|1|**Comparing Output**|Comparing outputs of both the file without any changes in the spreadsheet |Match of both the files|**PASS**| 
|2|**Adding row**|Comparing outputs after adding an extra row |Match of both the files|**PASS** |
|3|**Adding Column**|Comparing outputs after adding extra column  |Match of both the files|**PASS** |
|4|**The path of commands  is declared in Variable** |I declared the path of commands in variables in the configuration file which i used in my script file. |Path of command should be declare in the variable |**PASS**|
|5|**Google spread sheet downloaded in CSV format** |I used wget with -q option with url of the google spread sheet to download in csv format -q option is used for silently downloaded <br/> I used this $WGET $WGETOPT1 $MYURL111 and $MYURL222 the value of these variable extracting from the configuration file |Google spreadsheet in csv format should be downloaded |**PASS** |
|6|**Rename downloaded file**|I rename the file   by using mv command  <br/> I used this $MV $OLDFILENAME1 $NEWFILENAME1  the value of these variable extracted from the configuration file |Files should be renamed|**PASS**
|7 |**DISPLAY THE OUTPUT using configuration file** | I used the source of configuration file in the script and run the script  <br/> I used  this to extract the required column (awk -F "," '{print "Name :",$name1, "\n", "Sum :",$average1* m "\n", "Average :",$average1, "\n"}') |Script should be run and display the output |**PASS** |
|8 |**log file** |when script run all logs genrate in log file |log should be genrated successfully in log file |**pass**|
 
  </details>
    <details>
      <summary> Script </summary>
    </details>
   <details>
   <summary> Configuration </summary>
    #configuration file 

MV=/usr/bin/mv
CP=/usr/bin/cat
WGET=/usr/bin/wget
CAT=/usr/bin/cat
AWK=/usr/bin/awk
TAIL=/usr/bin/tail
TR=/usr/bin/tr
WC=/usr/bin/wc
GREP=/usr/bin/grep
ECHO=/usr/bin/echo
DIFF=/usr/bin/diff

#wget command is a Linux command line utility that helps us to download the files from the web.
    
#echo command in linux is used to display line of text/stringon terminal.
    
#mv command renames a file or folder and moves a group of files to a different directory

#cat command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files.

 #awk command searches files for text containing a pattern. When a line or text matches, awk performs a specific action on that line/text.
#tail commandprint the last N number of data of the given input.
  
    
#tr is a command for translating or deleting characters.
    
#The grep command in unix or linux system is used to print the lines that match a given pattern.
    
#wc Command in Linux Count Number of Lines, Words, and Character.
    
#pwd command prints the path of the working directory
    
#cp command is used to copy files or group of files or directory.
#date command is used to display the system date and time.
    
#wget command option
    
#The download output is not visible so -q is used
    
#tr command option
    
#-cd option used for delete the character.
    
#wc command option
    
#-c is used ko count the character
    
#grep command option
    
#-i option used for displays both uppercase and lowercase results.

#awk command option

#-F used for the input field separator.

    URL1=https://docs.google.com/spreadsheets/d/e/2PACX-1vRpppfbIt8hE4xJYHJrvUFtDN22PotSOgvmKjYluc5sm97RBw6cOmuWSxpaiiiWp1pGthVTJqQ_egkE/pub?output=csv

#URL222=https://docs.google.com/spreadsheets/d/e/2PACX-1vRpppfbIt8hE4xJYHJrvUFtDN22PotSOgvmKjYluc5sm97RBw6cOmuWSxpaiiiWp1pGthVTJqQ_egkE/pub?output=csv
URL2=https://docs.google.com/spreadsheets/d/e/2PACX-1vQGXHMKyNswx1p927YNRP2_ypb8NduJbI9qbzvRoSsjVKJ914n_sqWyQ34gz2qHdWwNxKs84B6102vG/pub?output=csv


#WGETOPT1=-q

#GREPOPT1=-i
    
#AWKOPT1=-F
    
 #TROPT1=-cd
#WCOPT1=-c
    
OLDFILENAME1=/home/shweta/task3/"pub?output=csv"
    
NEWFILENAME1=/home/shweta/task3/sheet1.csv

OLDFILENAME2=/home/shweta/task3/"pub?output=csv.1"
    
NEWFILENAME2=/home/shweta/task3/sheet2.csv

COLUMNFORNAME=name
    
COLUMNFORINTERNNAME=Intern
    
COLUMNFORAVERAGE=Average
    
COLUMNFORPUNCTUALITY=punctuality

#this is the path of log file
    
log=/home/shweta/task3/file.log
    
COMPAIR_FILE1_PATH=/home/shweta/task3/Value/Sheet1
    
COMPAIR_FILE2_PATH=/home/shweta/task3/Value/Sheet2
    
CURRENT_FILE1_PATH=Output1
    
CURRENT_FILE2_PATH=Output2                                                                                                                            
                
   </details>
    <details>
   <summary> log </summary>
     Wednesday 26 May 2021 12:15:06 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 12:15:06 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 12:15:06 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 12:15:06 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 12:15:06 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 12:16:48 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 12:16:48 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 12:16:48 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 12:16:48 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 12:16:48 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 12:16:48 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 12:16:48 AM IST [commas for extract the average column]
Wednesday 26 May 2021 12:16:48 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 12:52:20 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 12:52:20 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 12:52:21 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 12:52:21 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 12:52:21 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 12:52:21 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 12:52:21 AM IST [commas for extract the average column]
Wednesday 26 May 2021 12:52:21 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 12:52:31 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 12:52:31 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 12:52:31 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 12:52:31 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 12:52:31 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 12:52:31 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 12:52:31 AM IST [commas for extract the average column]
Wednesday 26 May 2021 12:52:31 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 12:54:25 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 12:54:25 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 12:54:25 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 12:54:25 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 12:54:25 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 12:54:25 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 12:54:25 AM IST [commas for extract the average column]
Wednesday 26 May 2021 12:54:25 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 06:54:54 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 06:54:54 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 06:54:54 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 06:54:54 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 06:54:54 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 06:54:54 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 06:54:54 AM IST [commas for extract the average column]
Wednesday 26 May 2021 06:54:54 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 07:08:27 AM IST sheet1 downloaded succesfully
Wednesday 26 May 2021 07:08:27 AM IST [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/shweta/task3/pub?output=csv /home/shweta/task3/sheet1.csv
Wednesday 26 May 2021 07:08:27 AM IST [count commas] count the no of commas before the Intern name
Wednesday 26 May 2021 07:08:27 AM IST [add 1 in the previous result of commas]
Wednesday 26 May 2021 07:08:27 AM IST [total commas for extract the Intern name column ]
Wednesday 26 May 2021 07:08:27 AM IST [count commas] count the no of commas before the Average
Wednesday 26 May 2021 07:08:27 AM IST [commas for extract the average column]
Wednesday 26 May 2021 07:08:27 AM IST [output for sheet 1] successfully print sheet1 the required output
Wednesday 26 May 2021 07:08:29 AM IST sheet1 downloaded succesfully

   </details>
    <details>
      <summary> Implementation </summary>
      We already have an output and when running the script when the new output is downloaded, then compare to it.  What is the difference between the two and  then we tested our script successfully.
</details>

   
   
   <details>
      <summary> Conclusion </summary>
      I want to share this when i worked in this script.So i got to learn many new things and this script was working right.
    </details>     
  
  
  ```
     Thank You
```  
  
  

 



