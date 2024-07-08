---
tags:
  - Keep/Label/Visual-Studio
---

___________________________________________________________________________

Short Description:   How to create custom code snippets for VS in C#_


--------------------------------------------------------------------------------------------------------------------------
                                                         Overview
                            --------------------------------------------------------------------

- Learn to create custom code snippets
- Speed up your code development in Visual Studio




--------------------------------------------------------------------------------------------------------------------------
                                                Create Code Snippet
--------------------------------------------------------------------------------------------------------------------------

1) Here is a quick procedure for creating code snippet
             a) It's not meant to be used in visual studio
             b) Will include steps to add alias to windows $PROFILE 
             c)  We will use VSCODE so make sure it's installed

           procedure:                                                                       create snippet
---------------------------------------
1. create a new text file to store your custom snippets 
       -  I named mine visual studio snippets and stored them in the visual    
           studio folder in documents
       - note: this is not required, you can store it anywhere

location: 
C:\Users\Keylan Shannon\OneDrive\Documents\Visual Studio 2019\Code Snippets


2. Use the following Snippet template to start writing your vscode snippets. Copy and paste this code into the text file: 

                                                 Code Snippet Template
                            --------------------------------------------------------------------

<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title></Title>
        </Header>
        <Snippet>
            <Code Language="<add language>">
                <![CDATA[]]>    
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>



3. Modify the template. Below will be an example of what to fill in: 

<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Console Read Line</Title>
             <Author>Keylan Shannon</Author>
            <Description>Creates a Console.Readline() statement</Description> 
            <Shortcut>cr</Shortcut>
        </Header>
        <Snippet>
            <Code Language="CSharp">
                <![CDATA[Console.ReadLine();]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>


• Shortcut: is the command you will type in to perform the snippet

• Code Language:  write the language you will use this snippet for. Here is some languages: 
                CSharp       -c#_
                VB               -visual basic 
                CPP            -c++
                HTML         -HTML templates
           - see the rest on step 4

• <![CDATA[ <paste code here]]>  - paste your code where its stated, no spaces.


4) Add the snippet to visual studio 

tools - code snippet manager - CSharp - import - <choose snippet file> - store 
• by default, store in "My Code Snippets" 




  ----- Remove this after this section is finished ----- 
--------------------------------------------------------------------------------------------------------------------------
                                                Create Code Snippet
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