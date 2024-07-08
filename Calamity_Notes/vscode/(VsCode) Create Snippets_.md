---
aliases:
  - "(VsCode) Create Snippets "
tags:
  - Keep/Label/Visual-Studio-Code
---

Short Description:  Create custom snippets vs code 


--------------------------------------------------------------------------------------------------------------------------

      procedure:                                                                       create code snippet
---------------------------------------
1.  File > Preferences (Code > Preferences on macOS) > User Snippet Conf 
2. select language (by language identifier) for which snippet should appear
3. select "New Global Snippets File"
4. Use following as template (for loop snippet for Javascript): 

// in file 'Code/User/snippets/javascript.json'
{
  "For Loop": {
    "prefix": ["for", "for-const"],
    "body": ["for (const ${2:element} of ${1:array}) {", "\t$0", "}"],
    "description": "A for loop."
  }
}


In the example above:

- "For Loop" is the snippet name. It is displayed via IntelliSense if no description is provided.

- prefix:  defines one or more trigger words that display the snippet in IntelliSense. Substring matching is performed on prefixes, so in this case, "fc" could match "for-const".

- body:  is one or more lines of content, which will be joined as multiple lines upon insertion. Newlines and embedded tabs will be formatted according to the context in which the snippet is inserted.
description is an optional description of the snippet displayed by IntelliSense.

- Additionally, the body of the example above has three placeholders (listed in order of traversal): ${1:array}, ${2:element}, and $0. You can quickly jump to the next placeholder with Tab, at which point you may edit the placeholder or jump to the next one. The string after the colon : (if any) is the default text, for example element in ${2:element}. Placeholder traversal order is ascending by number, starting from one; zero is an optional special case that always comes last, and exits snippet mode with the cursor at the specified position.




















<remove when finished- reference only> 
--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

- example overview statement
<write overview section here> 



--------------------------------------------------------------------------------------------------------------------------
                                                      Section title
--------------------------------------------------------------------------------------------------------------------------



                            --------------------------------------------------------------------
                                                         Sub Title
                            --------------------------------------------------------------------




                                                  Procedure : [Title]
                            --------------------------------------------------------------------

- (basic text)

1) [used to start alphabetized instructions for a procedure]  
             a) [used to insert comments or additional instructions]
             b)  Some more proc
             c)  another proc

 
      code/statement:                                                                       < small notes>
---------------------------------------

<add statement to be copied and pasted here> 


2) [Example of letter with a command]
 
      cmd:          
                       [command] [options] [file name] [etc]
                       [used as spacing for additional commands]
                            [ nested commands ]   
                                 [ nested commands 2 ]   
                                      [ nested commands 3 ] 
                                           [ nested commands 4 ] 

              • [add notes about the command here]             
              • [more comments]

- Second Part explanation ...