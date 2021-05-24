<h2 align="center">Task-4</h2>


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
    <li> Log file </li>
    <li> download files link  </li>
    <li> Conclusion </li>
  </ul>
  </details>
  
<details>
<summary> Details </summary>
  <ul>
    
<details>
  <summary> Test Cases </summary>
  
|S.NO|Test Cases|Test Case Description|Expected Result|Test Status
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
|1|**Published Url** |First of all, i used publish to the web option to publish a spreadsheet link and select the .csv format |Url should be published|**PASS** |
|2|**The path of commands  is declared in Variable** |I declared the path of commands in variables in the configuration file which i used in my script file. |Path of command should be declare in the variable |**PASS**|
|3|**Google spread sheet downloaded in CSV format** |I used wget with -q option with url of the google spread sheet to download in csv format -q option is used for silently downloaded <br/> I used this $WGET $WGETOPT1 $MYURL111 and $MYURL222 the value of these variable extracting from the configuration file |Google spreadsheet in csv format should be downloaded |**PASS** |
|4|**Rename downloaded file**|I rename the file   by using mv command  <br/> I used this $MV $OLDFILENAME1 $NEWFILENAME1  the value of these variable extracted from the configuration file |Files should be renamed|**PASS**
|5 |**Rename downloaded file** |I rename the file by using mv command  <br/> I used this $MV $OLDFILENAME2 $NEWFILENAME2 the value of these variable extracted from the configuration file |Files should be renamed|**PASS** 
|6 |**DISPLAY THE OUTPUT using configuration file** | I used the source of configuration file in the script and run the script  <br/> I used  this to extract the required column (awk -F "," '{print "Name :",$name1, "\n", "Sum :",$average1* m "\n", "Average :",$average1, "\n"}') |Script should be run and display the output |**PASS** |
|7 |**Adding the column at the top of the spreadsheet** |When i add add a column from the top to my google spreadsheet,it shows in the csv file |--|**PASS**|--|
|8 |**On updating a value below in the spreadsheet** |When i add a value from below in the spreadsheet,it shows in my output. |Output should be updated |**PASS** | |
|9 |**log file** |when script run all logs genrate in log file |log should be genrated successfully in log file |**pass**|

  
  </details>
    <details>
      <summary> Script </summary>
    </details>
    <details>
      <summary> Implementation </summary>
    </details>
    <details>
      <summary> Conclusion </summary>
      I want to share this when i worked in this script.So i got to learn many new things and this script was working right.
    </details>     
  </ul>
  
  ```
     Thank You
```  
  
  </details>

 



