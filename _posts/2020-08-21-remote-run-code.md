## What I learnt when my code ran on remote client environment

1. Background
    * As part of my work, I was asked to deliver a Context based search on few contract documents.
    * I developed an Elastic Search based solution. Nothing fancy.
    * I coded the application in python, got the logic working and with few business specific tweaks, I was able to reach close to 85%+ accuracy.
        1. Observation 1 : I wrote the code, wrote very basic sanity testcases, exception handling only in the main function.
            1. Modification 1 : Basic Test cases weren't sufficient.
                1. Write validation module for your input with as much possibilities as you can think.
                1. In my case eg: check headers of the excel are in the same format as expected.
                1. Check the number of rows, columns, any extra row, extra column, missing column.
                1. If using pandas, empty values would be read as NAN, have validation rules for these.
                1. If using any server or database or 3rd party API or server, always have a healthcheck function for that. Add it in your logs.
            1. Modification 2 : Basic Exception Handling wasn't clear enough to debug the error remotely
                1. Have exception handling atleast at every IO operation. 
                1. In my case, eg: while reading / writing excel files in pandas. 
                1. while connecting to Elastic Search engine.
                1. If empty value/ overflow value occurs in any necessary datastructure throught code.
                1. Always have a backup way to handle such exceptions:
                    1. Choice 1: Any exception break the code
                        1. Break only if this is critical and without which remaining code cannot run through
                        1. Have a validation module at the beginning of the code to make sure everything is checked and then start the code.
                            1. You could generate a health log for all the external interfacing libraries. This way it is easier to troubleshoot remotely
                    1. Choice 2: If exception, is there a way that code can run through remaining input values.
                        1. Track the successful and error inputs items through
                        1. Inside the exception handling, update the error items and continue
            1. Modification 3: Log handling should be verbose and needed in such a way that you should be able to simply read and troubleshoot the issue remotely.
                1. TIP 1: Best to log summary statistics of everything that you do within a code.
                    1. In my case eg: Log the total number of input files, number of rows /cols from excel, number of result matches from Elastic Search
                    1. Number of Success / Failure is something very useful as mentioned in previous point.
                    1. You could also log what is the approx intended time to finish (If it makes sense)
                    1. Provide time based statistics: In my case eg: time to run end-end, time to run each row from excel, time to search in Elastic etc
        1. Observation 2 : Anticipate possible things that may fail
            1. Input 
                1. Size: Input file sizes can go more than what you expected. What is the plan to handle it?
                    1. In my case, I didnt anticipate and requested the remote help to break the number of rows in excel and create multiple sheets.
                1. Encoding: Assume to always expect few changes in encoding format of files if you are reading that in your code.
                    1. Make sure you have a module to identify the encoding format and use that corresponding one.
            1. Output
                1. Size: 
         1. Observation 3 : Externalize parameters as much as possible
            1. Externalize wherever you see a pattern. It helps.
            1. Tradeoff on how much config needs tweaking: So in case someone has to change configurations, they need not change at multiple places.
                1. In my case eg: any file path reading or related values like excel file path or input file path are all related to code home folder.
                1. TIP: Create folder structure for input, output, models, config, logs, src separately so it is easy to manage it configurations. 
2. Share the codebase
    * .pyc files -> to deploy code, I generated the compiled files. So original code isnt available for anyone to read and tweak [ Unless you are contributing to open source] 
    * Zip the code or create exe using pyinstaller -> I chose the former
3. Share the instructions for remote engineer to run your code
    * TIP 1: Assume the remote person has very less tech knowledge. So your instructions should be very lucid and easy to follow
    * TIP 2: Before running on client machine, replicate the same environment as far as possible and run the code.
        1. In my case eg: I replicated a conda environment. Provide an estimated time so remote person can understand how much time to wait and not think that installation isnt working.
    * TIP 3: Create a good instructions file with screenshots for installations. 
    * TIP 4: Provide a good README file or API list with definitions eg:Swagger API for python
4. Compliance check for using Open source libraries on client environment
    * TIP 5: Always check BSD / Apache / MIT etc license is agreeable for installing in client environment for commercial purpose or otherwise.
        1. It is also great to read about static and dynamic linking of libraries if you are interested to know more in depth. It will save time in license approvals. 

Disclaimer: All the above are from a very specific project that I learnt. Hope this is helpful for others and hence shared here. Would be very happy to receive feedback / suggestions / alternative better ways.

Happy Remote troubleshooting!
  
