## GREP  
- - - -  
- [Find files containing text](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux)  
```bash
  grep -rnw '/path/to/somewhere/' -e 'pattern'
  
  grep -rl './' -e 'pattern' | xargs sed -i '' 's/pattern/replace/g'
```


Example:
```bash
  grep -rnw --exclude-dir=.git './' -e 'AAA\|BBB\|CCC'

  grep -rnw './' -e 'AAA'

  grep -rl --exclude-dir=.git './' -e 'AAA'      | xargs sed -i '' 's/AAA/XXXXX/g'
  grep -rl --exclude-dir=.git './' -e 'BBB'      | xargs sed -i '' 's/BBB/XXXXX/g'
  grep -rl --exclude-dir=.git './' -e 'CCC'      | xargs sed -i '' 's/CCC/XXXXX/g'
```

Example2:  
```
grep -rnw --exclude-dir={.git,boxes} './' -e 'pattern1\|pattern2\|pattern3'
```

Example3: pattern replace  
```
grep -rl --exclude-dir={.git,boxes} './' -e 'pattern'      | xargs sed -i '' 's/pattern/XXXXX/g'
```

- Replace string in OSX
```bash
  sed -i '' '/192.168.33/d' ~/.ssh/known_hosts
```
