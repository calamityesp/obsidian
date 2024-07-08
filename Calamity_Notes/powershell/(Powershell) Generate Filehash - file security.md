---
tags:
  - Keep/Label/PowerShell
---

Short Description: Generate md5 and more filehash using windows powershell 



 Generate Filehash for a file (md5 in this example) 

1) open powershell
2) use the command: 
                  
                           get-filehash <filename> -a <hash> 

eg.         get-filehash Release.zip -a md5 

- this will generate a file hash. 


View filehash

1) open powershell 
2) use the command: 
  
                             get-content <file-name>



compare hash

"<filehash"  -eq "<filehash2>"