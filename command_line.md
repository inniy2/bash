## Bash command line  
- - - -  
1. Find *.txt file but ignore hidden .txt file such as .vimrc or .data.txt file:  
```bash
$ find . -type f \( -iname "*.txt" ! -iname ".*" \)
```



