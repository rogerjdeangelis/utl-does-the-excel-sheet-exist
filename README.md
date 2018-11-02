# utl-does-the-excel-sheet-exist
Does the excel sheet exist? 
    Does the excel sheet exist?                                                                           
                                                                                                          
    github                                                                                                
    https://github.com/rogerjdeangelis/utl-does-the-excel-sheet-exist                                     
                                                                                                          
    other excel repositories                                                                              
    https://github.com/rogerjdeangelis?utf8=%E2%9C%93&tab=repositories&q=exce+in%3Aname&type=&language=   
                                                                                                          
    *                _              _       _                                                             
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _                                                      
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |                                                     
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |                                                     
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|                                                     
                                                                                                          
    ;                                                                                                     
    * just in case workbook exists - delete it;                                                           
    %utlfkil(d:/xls/class.xlsx);                                                                          
                                                                                                          
    * create workbook with sheet class;                                                                   
    libname xel "d:/xls/class.xlsx";                                                                      
    data xel.class;                                                                                       
      set sashelp.class;                                                                                  
    run;quit;                                                                                             
    libname xel clear;                                                                                    
                                                                                                          
    *          _       _   _                                                                              
     ___  ___ | |_   _| |_(_) ___  _ __                                                                   
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                  
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                 
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                 
                                                                                                          
    ;                                                                                                     
                                                                                                          
    *solution;                                                                                            
    libname xel "d:/xls/class.xlsx";                                                                      
                                                                                                          
    ods output members=have;                                                                              
    proc contents data=xel._all_;                                                                         
    run;quit;                                                                                             
                                                                                                          
    libname xel clear;                                                                                    
                                                                                                          
                                                                                                          
    data _null_;                                                                                          
      set have;                                                                                           
      if name ='class$' then put "class sheet exists";                                                    
    run;quit;                                                                                             
                                                                                                          
    308   data _null_;                                                                                    
    309     set have;                                                                                     
    310     if name ='class$' then put "class sheet exists";                                              
    311   run;                                                                                            
                                                                                                          
    class sheet exists                                                                                    
    NOTE: There were 2 observations read from the data set WORK.HAVE.                                     
    NOTE: DATA statement used (Total process time):                                                       
          real time           0.00 seconds                                                                
          cpu time            0.00 seconds                                                                
                                                                                                          
                                                                                                          
