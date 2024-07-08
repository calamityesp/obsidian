

Short Description:   Use semicolon to separate code 


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

- Seperate commands with a semicolon to ensure they will get executed
- statement following semicolon will execute regardless of the exit code of the previous statement 

 
      code/statement:                                                                    example
---------------------------------------

cp test.txt /tmp/bak ; cp test.txt /tmp

// SAME AS 

cp test.txt /tmp/bak/
cp test.txt /tmp


- note: personally don't think its good practice for writing shell scripts, but this is useful when you are u are using the command line