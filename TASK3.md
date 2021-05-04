
<h2 align="center">Task-3</h2>

<details>
  <summary> Summary of Task </summary>
  <ul>
    <br>
    <li> Write a script in Shell.</li>
    <li> This script has been used to download 2 google sheets. </li>
    <li> Both of those Google sheets will have the formate csv file. </li>
    <li> Only the name, Average and Sum columns and their values should be printed. </li>
  </ul>
</details>

<details>
<summary> INDEX </summary>
  <ul>
    <br>
    <li> Test cases</li>
    <li> Implementation </li>
    <li> Script </li>
    <li> Configuration File </li>
    <li> Log file </li>
    <li> download files link  </li>
    <li> Conclusion </li>
  </ul>
  </details>

<details>
  <summary> Test Cases </summary>
  
|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|Output|
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
|1|**Published Url** |First of all, i used publish to the web option to publish a spreadsheet link and select the .csv format |Url should be published|**PASS** |![webpubleshed](https://user-images.githubusercontent.com/82143335/117056330-d26c8300-ad39-11eb-8232-a9609f1167f8.PNG)|
|2|**The path of commands  is declared in Variable** |I declared the path of commands in variables in the configuration file which i used in my script file. |Path of command should be declare in the variable |**PASS** |![variables](https://user-images.githubusercontent.com/82143335/117057021-95ed5700-ad3a-11eb-9253-faa5df8ca109.PNG)|
|3|**Google spread sheet downloaded in CSV format** |I used wget with -q option with url of the google spread sheet to download in csv format -q option is used for silently downloaded <br/> I used this $WGET $WGETOPT1 $MYURL01 and $MYURL02 the value of these variable extracting from the configuration file |Google spreadsheet in csv format should be downloaded |**PASS** | ![csv formate](https://user-images.githubusercontent.com/82143335/117057486-24fa6f00-ad3b-11eb-8236-6796b3b96303.PNG) |
|4|**Rename downloaded file**|I rename the file   by using mv command  <br/> I used this $MV $OLDFILENAME1 $NEWFILENAME1  the value of these variable extracted from the configuration file |Files should be renamed|**PASS**
|5 |**Rename downloaded file** |I rename the file by using mv command  <br/> I used this $MV $OLDFILENAME2 $NEWFILENAME2 the value of these variable extracted from the configuration file |Files should be renamed|**PASS** 
|6 |**DISPLAY THE OUTPUT using configuration file** | I used the source of configuration file in the script and run the script  <br/> I used  this to extract the required column (awk -F "," '{print "Name :",$name1, "\n", "Sum :",$average1* m "\n", "Average :",$average1, "\n"}') |Script should be run and display the output |**PASS** | ![output](https://user-images.githubusercontent.com/82143335/117057924-a6ea9800-ad3b-11eb-8577-5bfdddeadd6a.PNG) |
|7 |**Adding the column at the top of the spreadsheet** |When i add add a column from the top to my google spreadsheet,it shows in the csv file |--|**PASS**|--|
|8 |**On updating a value below in the spreadsheet** |When i add a value from below in the spreadsheet,it shows in my output. |Output should be updated |**PASS** | |
|9 |**log file** |when script run all logs genrate in log file |log should be genrated successfully in log file |**pass** |![log](https://user-images.githubusercontent.com/82143335/117058350-25473a00-ad3c-11eb-97a4-e4acc19efe6b.PNG)|

  
  </details>
  
  <details>
  <summary> Implementation </summary>
  
In this script, first of all I used publish to the web option to copy the link to the spreadsheet. into the csv format
After that  downloaded the link of the spreadsheet using the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details>
  
  <details>
  <summary> Script </summary>
  !/bin/bash
#Here the exact column Intern Name is found.
  
#Here $CAT is used to show the contents of a file.

#GREP is used to find the row with a specific name.

#-i is used to find letters whether the letter is in upercase or in lowercase.

#Here tr command is used to translate and delete characters.

#Here wc -c command is used to count commas.

#Here wget command is used to download spreadsheet 1 with the help of url

#Here mv command is used to rename the file

#Here the exact column Average is found.

#Here $CAT is used to show the contents of a file.

#GREP is used to find the row with a specific name.

#-i is used to find letters whether the letter is in upercase or in lowercase.

#Here tr command is used to translate and delete characters.

#Here wc -c command is used to count commas.

#Here $ cat is used to show the contents of a file.

#$TAIL -n + 4 is used to not show the beginning 4 line of the file.

#$AWK is used to extract the required column and print the Name Sum and Average.

name=shweta

source /home/shweta/task3/script3.conf

if [ $URL111 = $name ]

then

$ECHO "This error for sheet 1"

else

echo "==================My first sheet output===================" 
#$ECHO "==================My first sheet output===================" > $log

        $WGET $WGETOPT1 $URL111

$ECHO "$(date) $pwd [wget command] download sheet1 csv file using wget command $WGET $OPTION1 $URL111" >> "$log"

$MV $OLDFILENAME1 $NEWFILENAME1

$ECHO "$(date) $pwd [mv command] download sheet1 csv file using mv command $MV $OLDFILENAME1 $NEWFILENAME1" >> "$log"

The below command shows the total number of commas.

#a1=$($CAT $NEWFILENAME1 | $GREP -i  NAME | $AWK -F "Intern Name" '{print $1}' | $TR -cd , | $WC -c)

a1=$($CAT $NEWFILENAME1 | $GREP $GREPOPT1 $COLUMNFORNAME | $AWK $AWKOPT1 "$COLUMNFORINTERNNAME" '{print $1}' | $TR $TROPT1 , | $WC $WCOPT1)

$ECHO "$(date) $pwd [count comma for intername] download sheet1 csv file using this command $a1" >> "$log"


b1=1

$ECHO "$(date) $pwd [add 1 for intername] download sheet1 csv file using this command $b1" >> "$log"

c1=$((a1+b1))

$ECHO "$(date) $pwd [total commas for intername] download sheet1 csv file using this command $c1" >> "$log"


#$ECHO "commas after adding 1 in intern name $c1"

#The below command shows the total number of commas.

#d1=$($CAT $NEWFILENAME1 | $GREP -i  average | $AWK -F "Average" '{print $1}'|$TR -cd , | $WC -c)

d1=$($CAT $NEWFILENAME1 | $GREP $GREPOPT1 $COLUMNFORAVERAGE | $AWK $AWKOPT1 "$COLUMNFORAVERAGE" '{print $1}' | $TR $TROPT1 , | $WC $WCOPT1)

$ECHO "$(date) $pwd [count comma for Average] download sheet1 csv file using this command $a1" >> "$log"

e1=1

$ECHO "$(date) $pwd [add 1 for Average] download sheet1 csv file using this command $b1" >> "$log"

     f1=$((d1+e1))

$ECHO "$(date) $pwd [total commas for Average ] download sheet1 csv file using this command $c1" >> "$log"

#============================================================================================================================

#sum  is used to store the value of total no of commas in row of specific name

sum=`$CAT $NEWFILENAME1 |$GREP $GREPOPT1 $COLUMNFORPUNCTUALITY | $TR $TROPT1 , | $WC $WCOPT1`

#$ECHO "$(date) $PWD [value of total no of commas in a row] $sum" >> "$LOG" #storing logs in the specified file

#total is used to store the value of total commas minus 2 commas

minus=2

TOTAL=`expr $sum - $minus`

$ECHO "multiply value $TOTAL"


#$ECHO "commas after adding 1 in average $f1"
#=======================================================================================================================================#


#cat result99.csv | tail -n+4 | awk -F "," '{print "Name : ",$name1, "\n", "SUM : ",$average1*8 "\n", "Avg : ",$average1, "\n"}' 

name1=$c1 average1=$f1 x=$valxue1

$CAT $NEWFILENAME1 | tail -n+4 | awk -F "," '{print "Name : ",$name1, "\n", "SUM : ",$average1*x "\n", "Avg : ",$average1, "\n"}' 

name1=$c1 average1=$f1 x=$TOTAL

$ECHO "$(date) $pwd"[output for sheet 1] successfully print sheet1 the required output >> "$log"


fi

###############################################################################################

if [ $URL222 = $name ]

then

$ECHO "This error for sheet 2"

else
     echo "==================My Second sheet output===================" 
#$ECHO "==================My Second sheet output===================" > $log

$WGET $WGETOPT1 $URL222

$ECHO "$(date) $pwd [wget command] download sheet1 csv file using wget command $WGET $OPTION1 $URL111" >> "$log"

$MV $OLDFILENAME2 $NEWFILENAME2

$ECHO "$(date) $pwd [mv command] download sheet1 csv file using mv command $MV $OLDFILENAME1 $NEWFILENAME1" >> "$log"


#a1=$($CAT $NEWFILENAME2 | $GREP -i  NAME | $AWK -F "Intern Name" '{print $1}' | $TR -cd , | $WC -c)

a11=$($CAT $NEWFILENAME2 | $GREP $GREPOPT1 $COLUMNFORNAME | $AWK $AWKOPT1 "$COLUMNFORINTERNNAME" '{print $1}' | $TR $TROPT1 , | $WC $WCOPT1)

$ECHO "$(date) $pwd [count comma for intername] download sheet1 csv file using this command $a1" >> "$log"


b11=1

$ECHO "$(date) $pwd [add 1 for intername] download sheet1 csv file using this command $b1" >> "$log"

c11=$((a11+b11))

$ECHO "$(date) $pwd [total commas for intername] download sheet1 csv file using this command $c1" >> "$log"


#$ECHO "commas after adding 1 in intern name $c1"

#d1=$($CAT $NEWFILENAME1 | $GREP -i  average | $AWK -F "Average" '{print $1}'|$TR -cd , | $WC -c)

d11=$($CAT $NEWFILENAME2 | $GREP $GREPOPT1 $COLUMNFORAVERAGE | $AWK $AWKOPT1 "$COLUMNFORAVERAGE" '{print $1}' | $TR $TROPT1 , | $WC $WCOPT1)

$ECHO "$(date) $pwd [count comma for Average] download sheet1 csv file using this command $a1" >> "$log"

e11=1

$ECHO "$(date) $pwd [add 1 for Average] download sheet1 csv file using this command $b1" >> "$log"

f11=$((d11+e11))

$ECHO "$(date) $pwd [total commas for Average ] download sheet1 csv file using this command $c1" >> "$log"



#$ECHO "commas after adding 1 in average $f1"

#======================================================================================================================================#
#sum  is used to store the value of total no of commas in row of specific name

sum=`$CAT $NEWFILENAME2 |$GREP $GREPOPT1 $COLUMNFORPUNCTUALITY | $TR $TROPT1 , | $WC $WCOPT1`

#$ECHO "$(date) $PWD [value of total no of commas in a row] $sum" >> "$LOG" #storing logs in the specified file

#total is used to store the value of total commas minus 2 commas

minus=2

TOTAL1=`expr $sum - $minus`

$ECHO "multiply value $TOTAL1"

#=======================================================================================================================================#

#cat result99.csv | tail -n+4 | awk -F "," '{print "Name : ",$name1, "\n", "SUM : ",$average1*8 "\n", "Avg : ",$average1, "\n"}' name1=$c1 average1=$f1 x=$valxue1

$CAT $NEWFILENAME2 | tail -n+4 | awk -F "," '{print "Name : ",$name1, "\n", "SUM : ",$average1*y "\n", "Avg : ",$average1, "\n"}' name1=$c11 average1=$f11 y=$TOTAL1

$ECHO "$(date) $pwd"[output for sheet 1] successfully print sheet1 the required output >> "$log"


fi
                                                                                                                                                                                                                                    
  </details>
  
 <details>
  <summary> Configuration file </summary>
  
configuration file 

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
                                                                                                                            1,1           
URL111=https://docs.google.com/spreadsheets/d/e/2PACX-1vQjSvAMnKpqXy4p1ZCwoBl3OT4YAC3V8p-YKnciBTuPg-GDlVTJkCRNxYQqG_V99d7r6qTYL8OVrW2E/pub?output=csv

URL222=https://docs.google.com/spreadsheets/d/e/2PACX-1vRpppfbIt8hE4xJYHJrvUFtDN22PotSOgvmKjYluc5sm97RBw6cOmuWSxpaiiiWp1pGthVTJqQ_egkE/pub?output=csv

WGETOPT1=-q

GREPOPT1=-i

AWKOPT1=-F

TROPT1=-cd

WCOPT1=-c

OLDFILENAME1=/home/shweta/task3/"pub?output=csv"

NEWFILENAME1=/home/shweta/task3/sheet1.csv

OLDFILENAME2=/home/shweta/task3/"pub?output=csv"

NEWFILENAME2=/home/shweta/task3/sheet2.csv

COLUMNFORNAME=name

COLUMNFORINTERNNAME=Intern

COLUMNFORAVERAGE=Average

COLUMNFORPUNCTUALITY=punctuality

#this is the path of log file

log=/home/shweta/task3/file.log
  
  </details>

<details>
<summary> Log file </summary>
  
  ==================My first sheet output===================
Tuesday 04 May 2021 11:33:08 AM IST  [mv command] download sheet1 csv file using mv command /usr/bin/mv  

Tuesday 04 May 2021 11:33:08 AM IST  [count comma for intername] download sheet1 csv file using this command 1

Tuesday 04 May 2021 11:33:08 AM IST  [add 1 for intername] download sheet1 csv file using this command 1

Tuesday 04 May 2021 11:33:08 AM IST  [total commas for intername] download sheet1 csv file using this command 2

Tuesday 04 May 2021 11:33:08 AM IST  [count comma for Average] download sheet1 csv file using this command 1

Tuesday 04 May 2021 11:33:08 AM IST  [add 1 for Average] download sheet1 csv file using this command 1

Tuesday 04 May 2021 11:33:08 AM IST  [total commas for Average ] download sheet1 csv file using this command 2

Tuesday 04 May 2021 11:33:08 AM IST [output for sheet 1] successfully print sheet1 the required output

==================My second sheet output===================

Tuesday 04 May 2021 11:33:10 AM IST  [wget command] download sheet2 csv file using wget command /usr/bin/wget option1 

https://docs.google.com/spreadsheets/d/e/2PACX-1vRpppfbIt8hE4xJYHJrvUFtDN22PotSOgvmKjYluc5sm97RBw6cOmuWSxpaiiiWp1pGthVTJqQ_egkE/pub?output=csv

Tuesday 04 May 2021 11:33:10 AM IST  [mv command] download sheet2 csv file using mv command /usr/bin/mv /home/shweta/my_presentation
/pub?output=csv /home/shweta/my_presentation/result2222.csv

Tuesday 04 May 2021 11:33:10 AM IST  [count comma for intername] download sheet2 csv file using this command 1

Tuesday 04 May 2021 11:33:10 AM IST  [add 1 for intername] download sheet1 csv file using this command 1

Tuesday 04 May 2021 11:33:10 AM IST  [total commas for intername] download sheet2 csv file using this command 2

Tuesday 04 May 2021 11:33:10 AM IST  [count comma for Average] download sheet2 csv file using this command 11

Tuesday 04 May 2021 11:33:10 AM IST  [add 1 for Average] download sheet2 csv file using this command 1

Tuesday 04 May 2021 11:33:10 AM IST  [total commas for Average ] download sheet2 csv file using this command 12

Tuesday 04 May 2021 11:33:10 AM IST [outputfor sheet 2] successfully print the required output

  
  </details>

<details>

<summary> Download files link</summary>

URL111=https://docs.google.com/spreadsheets/d/e/2PACX-1vQjSvAMnKpqXy4p1ZCwoBl3OT4YAC3V8p-YKnciBTuPg-GDlVTJkCRNxYQqG_V99d7r6qTYL8OVrW2E/pub?output=csv
  

#URL222=https://docs.google.com/spreadsheets/d/e/2PACX-1vRpppfbIt8hE4xJYHJrvUFtDN22PotSOgvmKjYluc5sm97RBw6cOmuWSxpaiiiWp1pGthVTJqQ_egkE/pub?output=csv

</details>

<details>

<summary> Conclusion</summary>
  I want to share this when i worked in this script.So i got to learn many new things and this script was working right

</details>
  
  ```
     Thank You
```
