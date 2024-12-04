java c
CDS532 Programming for Data Science 
Case Study Assignment 
(Due: 11th December 2024, 23:59) 
Introduction Air   pollution   refers   to   the   contamination   of   the   atmosphere   by   the   pollutants   released   into   the   air   when   industrial   and   commercial   activities   are   conducted. These   pollutants   are   harmful to   human   health   and   the   environment. Three   major sources of air   pollutants   in   Hong   Kong   are   motor vehicles,   marine   vessels,   and   power   plants.   In   this   case   study,   we would   like to   investigate the   air   pollution   problem   in   Hong   Kong. To   achieve our   objective,   we   will write   a   python   program that   can   automatically   fetch   data from the   Hong   Kong   government’s   data   portal   and visualize   the   data   into   charts.
Program Requirement 
Write a   program that   prompts the   user to   select which year’s air   quality   health   index   (AQHI)   dataset   should   be   used   for conducting air   pollution data visualization. The   program will then   fetch the dataset that correspond to the year selected by the user from the data resource in JSON format in the   data   portal   named   "Past   record   of Air   Quality Health   Index   (English Version)". The API for fetching data   is shown   as follows:https://api.data.gov.hk/v2/aggregate/hk-epd-past-record-of-aqhi-en?q={"section":
, "format":} 
This API takes a JSON string which contains the   parameter   values   for   configuring   which   data   should   be   fetched.   The   definitions of the   parameters are   listed   below:Parameter Description section This parameter defines which year of the AQHI data to be fetched with a section code. The mapping between the section code and the year is shown in the table below: Section Code Year 2 2014 3 2015 4 2016 5 2017 6 2018 Note: This API only provides complete annual AQHI data from 2014 to 2018. The table above has already covered all section codes that can be mapped to a complete annual AQHI dataset. format This parameter defines the format of the return data. There are three different options: CSV, json and xml. In this assignment, json should be used 
After the AQHI data   has   been fetched, the   program   reads the AQHI   data   in JSON format   downloaded from   the   data   portal and conducts data   preprocessing. A   preview of the   annual   AQHI   data   is   shown   below:

The annual AQHI data   is a table   where   each   row   corresponds to   16   different   AQHI   values   measured   in   16   air   quality   monitoring stations   in a   particular   hour   in a   particular day. The first   column   is   the   date   when   the   AQHI   value   is
measured. The second colu代 写CDS532 Programming for Data SciencePython
代做程序编程语言mn   is the   hour when the AQHI value   is   measured.   If   a   row   has   a value   "Daily   Max"   in   the   hour column, that   row   is   recording the   maximum AQHI values of every   air   quality   monitoring   station   in   a   particular      day.   Each of the   remaining   16 columns   represents the AQHI data   collected   by   one   of the   16   air   quality   monitoring            stations   located   in the following   16   locations:   Central/Western,   Eastern,   Kwun Tong, Sham Shui   Po,   Kwai Chung,
Tsuen Wan, Tseung   KwanO, Yuen   Long, Tuen   Mun, Tung Chung, Tai   Po, Sha Tin, Tap   Mun, Causeway   Bay,   Central,   Mong   Kok.
Some AQHI values   in the annual AQHI data   may contain   two   extra   symbols   such   as   "+"   and   "*".   These   two   symbols   provide additional contextual   information.   However, these symbols   may   interfere with our   analysis   and   have   to   be   removed. On the other   hand, some AQHI values   maybe   missing   (i.e.   empty value).   Missing values   are   handled   by            filling with   zeros.
After   performing data   preprocessing, the   program then   performs the   necessary calculations to   plot the   following   two   kinds of charts to visualize air   population   in the   monthly   scale:
The first   kind of chart   is a   bar chart   which   plots   the monthly average AQHI of16 air quality monitoring stations in  Hong Kong.
The second   kind of chart   is a   line chart   which   plot the changing trend of the AQHI averaged across 16 air quality  monitoring stations in Hong Kong.
Note: To   keep things simple, the   maximum AQHI value X measured at   monitoring   station   S   in   date   D   will   be   considered as the overall AQHI value of the   monitoring   station S   at   date   D.
Sample Input Terminal Year Data available: 2014: section code 2 2015: section code 3 2016: section code 4 2017: section code 5 2018: section code 6 
Please enter the section code corresponding to the target year: 4 
Sample output 

Assumptions 
You   may assume that every   input of the   program   is valid   in format.
Submission 
Students should submit their source code   as   (1)   a   single Jupiter   Notebook   file   (i.e. .ipynb file) OR (2)   a   zip   file   that contains standalone   Python script. files   (i.e. .py files) for answering   the   programing   questions   to   the   submission   box on the   Moodleelearning   platform. on or   before   11th      December 2024,   23:59. Students   are expected   to   name   their   file   submission   in the   name of _case_study.ipynb OR _case_study.zip and their source code should follow the following format:






         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
