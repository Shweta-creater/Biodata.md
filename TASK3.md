
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
    <li> Conclusion  </li>
    <li> download files links </li>
  </ul>
  </details>

<details>
  <summary> Test Cases </summary>
  
|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|Output|
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
|1|**Published Url** |Spread sheet link published by using publish to web option from file of spreadsheet and select the .csv format |Url should be published|**PASS** |![Webpublish](https://user-images.githubusercontent.com/82143335/116895216-94476480-ac50-11eb-9466-18a10936a60e.PNG)|
|2|**The path of commands  is declared in Variable** |I declared the path of commands in variables in the configuration file which i used in the script file. |Path of command should be declare in the variable |**PASS**|![variables](https://user-images.githubusercontent.com/82143335/116895709-1cc60500-ac51-11eb-8d94-fbb9faf237a5.PNG)|
|3|**Google spread sheet downloaded in CSV format** |I used wget with -q option with url of the google spread sheet to download in csv format -q option is used for silently downloaded <br/> I used this $WGET $WGETOPT1 $MYURL01 and $MYURL02 the value of these variable extracting from the configuration file |Google spreadsheet in csv format should be downloaded |**PASS** |![download spreadsheet](https://user-images.githubusercontent.com/82143335/116896072-7cbcab80-ac51-11eb-9828-6bb1f0caf055.PNG)|
|4|**Rename downloaded file**|Renamed  files by using mv command  <br/> I used this $MV $OLDFILENAME1 $NEWFILENAME1  the value of these variable extract from the configuration file |Files should be renamed|**PASS** |--|
|5 |**Rename downloaded file** |Renamed  files by using mv command  <br/> I used this $MV $OLDFILENAME2 $NEWFILENAME2 the value of these variable extract from the configuration file |Files should be renamed|**PASS** |--|
|6 |**DISPLAY THE OUTPUT using configuration file** | I used the source of configuration file in the script and run the script  <br/> I used  this to extract the required column (awk -F "," '{print "Name :",$name1, "\n", "Sum :",$average1* m "\n", "Average :",$average1, "\n"}') |Script should be run and display the output |**PASS** |![outpu2](https://user-images.githubusercontent.com/82143335/116898853-872c7480-ac54-11eb-92b5-81bcc2a41a1c.PNG)|
|7 |**Adding the column in the spreadsheet** |Add the column in the spreadsheet and gives the word to all students |Output should be updated |**PASS** | |
|8 |**Adding the row in the spreadsheet** |Add the row in the spreadsheet and gives the word in all the columns |Output should be updated |**PASS** | |
|9 |**log file** |when script run all logs genrate in log file |log should be genrated successfully in log file |**pass** |![log](https://user-images.githubusercontent.com/82143335/116899357-12a60580-ac55-11eb-822a-faa3d25cfff6.PNG)|

  
  </details>
  
  <details>
  <summary> Implementation </summary>
  
In this script, first of all I copied the spreadsheet link to csv link through web publish option.
After that I downloaded the link to the spreadsheet with the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details>
  
  <details>
  <summary> Script </summary>
