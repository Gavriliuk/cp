# crashportal utilities

These scripts allow to download a single crashreport or a set of crashreports from crashportal


Installation

- place all these files to any folder listed in $PATH
- add the line 'machine crashportal login YOURLOGIN password YOURPASSWORD' to your ~/.netrc


Usage

Single report:

    cp-rep 1234567890                # Download report with id 1234567890 to the folder ./cp/1234567890 (default)
    cp-rep 1234567890 .              # Download report with id 1234567890 to the folder ./1234567890 (current folder)
    cp-rep 1234567890 ~/reports      # Download report with id 1234567890 to the folder ~/reports/1234567890

Number of reports:

    cp-list 'app=Receiver&reason=SIGFPE&max=10&days=5'                       # Download reports to ./cp/NNNNNNNNNN (default)
    cp-list 'signature=operationLinkDirectCall' cp-$(date +%y%m%d)           # Download reports to ./cp-YYMMDD/NNNNNNNNNN


Files cp-session, cp-setenv, cp-signin, cp-text are being used internally (sourced)


Bonus

Analyze logs in a folder with one report or few reports:

    an-logs                          # analyze reports in the current folder and write to ../result-DIRNAME.txt
    an-logs cp/1234567890            # analyze report in the folder ./cp/1234567890 and write to ./cp/result-1234567890.txt


Enjoy!
