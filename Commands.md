# Lab Commands

## Password List Analysis
```bash
# View password list
cat /usr/share/john/password.lst

# Count total passwords
cat /usr/share/john/password.lst | wc -l

# Filter passwords with numbers and lowercase letters
cat /usr/share/john/password.lst | pw-inspector -n -l

# Count passwords with length ≥5, numbers and lowercase
cat /usr/share/john/password.lst | pw-inspector -m 5 -nl | wc -l
