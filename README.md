# utl_classic_editor_pfkeys_prefix_mouse

SAS display manager editor. SAS function keys. Mapped mouse functions. Prefix araea. Best editor for SAS.

    SAS Classic Editor Prefix area, Function Keys and Mouse Actions                                                                          
                                                                                                                                             
    see also                                                                                                                                 
    https://github.com/rogerjdeangelis/utl_sas_classic_editor                                                                                
                                                                                                                                             
    SOAPBOX ON                                                                                                                               
                                                                                                                                             
    It is my belief that no 'external editor' can                                                                                            
    possibly have as much functinality as the 'Classic SAS editor'.                                                                          
    This is because all of SAS, Pyhton, R , Perl can be executed from the                                                                    
    SAS command line.                                                                                                                        
                                                                                                                                             
    However I do suspect there is some functinality perhaps 'non essential'                                                                  
    window dressing in sublime that the 'old text editor                                                                                     
    cannot duplicate.                                                                                                                        
    Although very functional, the Classic editor, does not have extensive                                                                    
    window dressing.                                                                                                                         
    SOAPBOX OFF                                                                                                                              
    Simple SAS command line and function key killer apps                                                                                     
    =====================================================                                                                                    
    xpy make data                                                                                                                            
    *                _              _       _                                                                                                
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _                                                                                         
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |                                                                                        
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |                                                                                        
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|                                                                                        
                                                                                                                                             
    ;                                                                                                                                        
                                                                                                                                             
    * line up the data;                                                                                                                      
                                                                                                                                             
     1    2       3          4                                                                                                               
        5          6     7 8                                                                                                                 
                                                                                                                                             
    Highlight and type cuth on command line                                                                                                  
                                                                                                                                             
     1 2 3 4                                                                                                                                 
     5 6 7 8                                                                                                                                 
                                                                                                                                             
    ====================================================                                                                                     
                                                                                                                                             
    Suppose you have only one hand and you want to highlight                                                                                 
    and submit code                                                                                                                          
                                                                                                                                             
     1. Hold down left mouse button                                                                                                          
     2. drag over the text you want to submit                                                                                                
     3. hight right mouse butto                                                                                                              
                                                                                                                                             
    Highlight the code you want to update                                                                                                    
                                                                                                                                             
     type c roger mary all;c yesterday today;                                                                                                
                                                                                                                                             
    =====================================================                                                                                    
                                                                                                                                             
    Middle mouse button                                                                                                                      
                                                                                                                                             
     version the current program                                                                                                             
                                                                                                                                             
    =======================================================                                                                                  
                                                                                                                                             
    Fix frozen SAS : Hit function key 12 highlight text and submit                                                                           
                                                                                                                                             
    keydef "F12" '~;;;;/*''*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;';                                               
                                                                                                                                             
    ==========================================================================================                                               
                                                                                                                                             
    Here is alist of some others (over 20 are on function keys. MX310 5 button programmable mouse)                                           
                                                                                                                                             
    /* T1004590 SAS-Forum: SAS not working (frozen SAS issue - an old text editor solution)                                                  
    This seems to work 99.99% of the time?                                                                                                   
    Hit F8 highlight the line in 'old text editor' then hit mouse RMB.                                                                       
    see                                                                                                                                      
    https://goo.gl/fQTV9q                                                                                                                    
    https://communities.sas.com/t5/SAS-Enterprise-Guide/SAS-not-working/m-p/357118                                                           
    Does not work in (EG or SAS Studio - may not work in EE), best in old text editor                                                        
    Paste the keydef command below into the old text editor 'clean' command line.                                                            
    Not the command bar or EE dual command lines?                                                                                            
    This works for me, but you may need to type into keys window.                                                                            
    If you type it in make sure you change /*''*/ to /*'*/.                                                                                  
                                                                                                                                             
    keydef "F8" '~;;;;/*''*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;';                                                
                                                                                                                                             
    Put the macro below in your autocall library.                                                                                            
    Turn on 'options cmdmac'                                                                                                                 
                                                                                                                                             
    %macro utlfix(dum);                                                                                                                      
                                                                                                                                             
    * fix frozen sas and restore to invocation ;                                                                                             
     dm "odsresults;clear;";                                                                                                                 
     options ls=171 ps=65;run;quit;                                                                                                          
     ods listing;                                                                                                                            
     ods select all;                                                                                                                         
     ods graphics off;                                                                                                                       
     proc printto;run;                                                                                                                       
     goptions reset=all;                                                                                                                     
     endsubmit;                                                                                                                              
     endrsubmit;                                                                                                                             
     run;quit;                                                                                                                               
     %utlopts;                                                                                                                               
                                                                                                                                             
    %mend utlfix;                                                                                                                            
                                                                                                                                             
    for my performance command macros(utl_perpac.sas)                                                                                                                                                                                           
    https://tinyurl.com/y9nfugth                                                               
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories 
                                                                          
                                                                                                                                             
    My function keys (requires MX310 mouse with over 20 actions)                                                                             
                                                                                                                                             
    Obs    KEY        LEN    VAL                                                                                                             
                                                                                                                                             
      1    F1          71    pgm;file &pgm..sas;file c:\ver\&pgm.&_q..sas;%let _q=%eval(0&_q +1);                                            
      2    F2          30    store;note;notesubmit '%avgha'                                                                                  
      3    F3           6    left 3                                                                                                          
      4    F4           7    right 3                                                                                                         
      5    F5          30    store;note;notesubmit '%dmpa;'                                                                                  
      6    F6          31    store;note;notesubmit '%dmpha;'                                                                                 
      7    F7          67    log;file "./&pgm..log";note zx;notesubmit "%utl_logcurchk(./&pgm);"                                             
      8    F8           5    rfind                                                                                                           
      9    F9           7    rchange                                                                                                         
     10    F11         33    store;note;notesubmit '%debugha;'                                                                               
     11    F12         73    ~;;;;/*'*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;                                       
     12    SHF F1      24    note;notesubmit '%dmpa;'                                                                                        
     13    SHF F2      25    note;notesubmit '%lsala;'                                                                                       
     14    SHF F6      67    ~n ? "hil";n=*"PFil Mason";n gt:"Phil";n le:"Phim"; sql - eqt    */                                             
     15    SHF F7      67    ~libname x excel ".xls";proc sql;update x;set y=2;where n="Roger"*/                                             
     16    SHF F8      12    :a;copy box;                                                                                                    
     17    SHF F9      12    :a:copy hdr;                                                                                                    
     18    SHF F10     70    ~options minoperator;%macro t(x=a)/minoperator;%if &x in (a b c) %then                                          
     19    SHF F11     24    note;notesubmit '%cona;'                                                                                        
     20    SHF F12     31    store;note;notesubmit '%frqva;'                                                                                 
     21    CTL F1      31    store;note;notesubmit '%dmpha;'                                                                                 
     22    CTL F2      32    store;note;notesubmit '%lsalha;'                                                                                
     23    CTL F3      10    ~available                                                                                                      
     24    CTL F11     31    store;note;notesubmit '%conha;'                                                                                 
     25    CTL F12     31    store;note;notesubmit '%cntva;'                                                                                 
     26    ALT F1      30    store;note;notesubmit '%vuha;'                                                                                  
     27    ALT F2      28    vt _last_ colheading=names;"                                                                                    
     28    ALT F3      64    ~proc report data=c nowd named list wrap;columns _all_;run;quit;                                                
     29    ALT F11     31    store;note;notesubmit '%xlsha;'                                                                                 
     30    ALT F12     30    store;note;notesubmit '%unva;'                                                                                  
     31    CTL B        3    :tf                                                                                                             
     32    CTL D       10    ~available                                                                                                      
     33    CTL E       10    ~available                                                                                                      
     34    CTL G        8    note g.g                                                                                                        
     35    CTL H        8    note h.h                                                                                                        
     36    CTL I        3    :lc                                                                                                             
     37    CTL J        3    :uc                                                                                                             
     38    CTL K        4    :mcu                                                                                                            
     39    CTL L        4    :mcl                                                                                                            
     40    CTL M       79    ~proc format;value $a;proc catalog cat=work.formats;modify a.formatc(desc=dea);                                 
     41    CTL Q        9    ~aailable                                                                                                       
     42    CTL R       11    wattention;                                                                                                     
     43    CTL T       73    ~proc tabulate data=class;class sex age;table age,sex*(n pctn<age>)/rts=8                                       
     44    CTL U       80    ~do until(last.s);set c;by s;a+ag;end;do until(last.s);set c;by s;output;end;a=0                                
     45    CTL W       10    ~available                                                                                                      
     46    CTL Y       34    ~where name like "B_B" "%B%" "B%B"                                                                              
     47    RMB         53    log;clear;out;clear;pgm;submit;home;rec;home;log;z;z;                                                           
     48    SHF RMB     25    note;notesubmit '%ls40a;'                                                                                       
     49    CTL RMB     32    store;note;notesubmit '%ls40ha;'                                                                                
     50    MMB         13    ~mapped to F1                                                                                                   
     51    SHF MMB     17    ~mapped to shf F1                                                                                               
     52    CTL MMB     17    ~mapped to ctl F1                                                                                               
     These three classic commands do not work consitently or at all?                                                                         
     CURSOR                                                                                                                                  
     ======                                                                                                                                  
     The CURSOR assignment statement sets or retrieves the column number of the                                                              
     cursor location within the data and either the relative line number or label.                                                           
     These values are placed in variables.                                                                                                   
     TF ( prefix area text flow)                                                                                                             
     ============================                                                                                                            
      Flows beyond the first blank line (intermittent)                                                                                       
     ===                                                                                                                                     
     Chages within a highlighted block of code does not shidt code right on insert                                                           
     STORE                                                                                                                                   
     =====                                                                                                                                   
       Works in classic editor but not EE (or any of the new flavors)                                                                        
    I have contacted SAS but these commands are not strategic?                                                                               
       T002790 SAS DISPLAY MANAGER COMMANDS AND SCRIPTS OLD EDITOR */                                                                        
       Very fast point and shoot editing and code submit in the old text editor.                                                             
       suppose you have submit on the right mouse key                                                                                        
       Use the ALT key as you hold down the mouse button and drag the mouse                                                                  
       to select a rectangular block (or column) of te                                                                                       
       After the highlight above hit the right mouse button and the highlighted code will                                                    
       be executed.                                                                                                                          
       type change x y on the command line                                                                                                   
       then x will be changed to y only in the highlighted area.                                                                             
       Simple actions like typing 860 on the command line will take to line                                                                  
       860. On long programs I sometimes jot down the location of                                                                            
       keta lines.                                                                                                                           
     USEFUL EDITIING COMMANDS                                                                                                                
     *************************                                                                                                               
      The prefix area  Many of these commands can be put on function keys using a ':', ie :ts.                                               
      SAS is slowly removing some of these functions from the old simple text editor.                                                        
      D        Delete current line                                                                                                           
      I        Insert a line here                                                                                                            
      C        Copy current line                                                                                                             
      D99----  Delete next 99 lines (also could cut with mouse)                                                                              
      I999---  Insert 999 blank lines useful when autoadd is set                                                                             
      IB55---  Insert 55 lines before                                                                                                        
      C3-----  Copy next three lines to some target                                                                                          
      A000102  Target for line copy or include file (copy after)                                                                             
      B000102  Target for line copy or include file (copy before)                                                                            
      M------  Move this line somewhere                                                                                                      
      M3-----  Move next 3 lines somewhere                                                                                                   
      O3-----  Move source lines over these lines                                                                                            
      R3-----  Replicate the next 3 lines                                                                                                    
      DD00103  Block delete   CC00103  Block Copy    MM00103  Block Move                                                                     
      0000104                 0000104                0000104                                                                                 
      DD-----                 CC-----                MM-----                                                                                 
      OO00103  Target Over    RR3----  Block Replicate                                                                                       
      0000104                 0000104                                                                                                        
      OO-----                 RR-----                                                                                                        
      (4-----  Shift left first 4 columns into bit bucket (distructive shift)                                                                
      )4-----  Shift right first 4 columns (distructive shift)                                                                               
      >5-----  Nondistructive shift right                                                                                                    
      <5-----  Nondistructive shift left                                                                                                     
      >>5----  Non distructive shift right of a block of commands                                                                            
      0000101                                                                                                                                
      0000102                                                                                                                                
      >>-----                                                                                                                                
      <<,)),(( Similar to single character versions                                                                                          
      UC----- Upper case line  - more useful on function key as :UC                                                                          
      UC26--- Upper case next 26 lines                                                                                                       
      LC----- Lower case line                                                                                                                
      LC26    Lower case next 26 lines                                                                                                       
      LLC---- Block of lines -lower caSE                                                                                                     
      UUC                                                                                                                                    
      TF----- Text flow lines until blank line                                                                                               
      TS----- Text split at cursor better on function key as :tf                                                                             
      MASK - BUILD TEMPLATE FOR ENTERING DATA                                                                                                
       no need to look up a P-Value                                                                                                          
       put this on any command line                                                                                                          
       %put %sysfunc(probnorm(1.96)); /* try this on command line */                                                                         
       ?          - previous command history                                                                                                 
       subtop     - submit top line of editor                                                                                                
       icon                                                                                                                                  
       rchange    - change on function key hit                                                                                               
       rfind      - find on function key hit                                                                                                 
       save  prg       /# save program in your profile  ie pgm.source #/                                                                     
       copy  prg       /# recalls program from your profile #/                                                                               
       change     - c today yesterday ic all   ( ignore case all)                                                                            
       cols                                                                                                                                  
       reset                                                                                                                                 
       keys                                                                                                                                  
       top                                                                                                                                   
       bot                                                                                                                                   
       n           - go to line n                                                                                                            
       left  n                                                                                                                               
       right  n                                                                                                                              
       spell all - check spelling of all words in editor                                                                                     
       autoadd   - add aline at a time to editor ( usewith mask and bounds )                                                                 
       vscroll 25 - set scroll amounts for forward and backward                                                                              
       hscroll 10                                                                                                                            
       backward max n                                                                                                                        
       forward max  n                                                                                                                        
       bounds                                                                                                                                
       mask                                                                                                                                  
       copy                                                                                                                                  
       paste                                                                                                                                 
       find - f 'data' first last next prev prefix suffix word                                                                               
       find 'Mac' prefix                                                                                                                     
       change - c todat yesterday ic all                                                                                                     
       rchange - change on function key hit                                                                                                  
       rfind   - find on function key hit                                                                                                    
       mark - highlight string, lines for submit or edit                                                                                     
       mark block - highlight rectangle within editor                                                                                        
                    does not have to be full lines                                                                                           
       JR                                                                                                                                    
       JL                                                                                                                                    
       JJR                                                                                                                                   
       JJL                                                                                                                                   
    Mastering a few more commands greatly increases the complexity of what you can do within the text editor.                                
    Several commands enable you to justify text. Specify the JL (justify left) command to                                                    
    left justify, the JR (justify right) command to right justify, and the JC (justify center)                                               
    command to center text. To justify blocks of text, use the JJL, JJR, and JJC commands. For example, if you want to center the following t
       store                                                                                                                                 
       zoom z                                                                                                                                
       up 2                                                                                                                                  
       down 4                                                                                                                                
       CAPS on/off                                                                                                                           
       home                                                                                                                                  
       cursor                                                                                                                                
       nums on/off                                                                                                                           
       %let                                                                                                                                  
       vt                                                                                                                                    
       pmenu off /# functon key #/                                                                                                           
       pmenu on                                                                                                                              
       end                                                                                                                                   
       print                                                                                                                                 
       submit                                                                                                                                
       unmark unmark all                                                                                                                     
       tabs                                                                                                                                  
       redo                                                                                                                                  
       nums on/off                                                                                                                           
       fse                                                                                                                                   
       fsv                                                                                                                                   
       fsb                                                                                                                                   
       libn                                                                                                                                  
       filen                                                                                                                                 
       fslist                                                                                                                                
       vt                                                                                                                                    
       print                                                                                                                                 
       Example 1 -- Just a dumb script                                                                                                       
       --------------------------------                                                                                                      
       1;F ' ';MARK;HOME;2;HOME;MARK;HOME;STORE;HOME;UNMARK;                                                                                 
       If the first line in active editor contains                                                                                           
       000001 %Macro MyLongMacroName                                                                                                         
       This script will put MyLongMacroName into the paste buffer.                                                                           
       You can then paste MyLongMacroName anywhere you want.                                                                                 
       (This only works on windows). Try it, just copy                                                                                       
       the one line script to the command line.                                                                                              
                                                                                                                                             
