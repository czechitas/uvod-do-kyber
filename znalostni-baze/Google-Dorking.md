# Google Dorks / Google Dorking

>[!TIP]
> Google Dorking je název techniky upravování vyhledávacích dotazů pro dosažení co nejpřesnějších výsledků vyhledávání. <br />
> Jako "Google Dorks" se označují funkční kombinace vyhledávacích parametrů.

## Vyhledávací filtry
>[!NOTE]
> aktuální a udržovaný zdroj: https://gist.github.com/sundowndev/283efaddbcf896ab405488330d1bbc06

| Filtr          | Popis                                        | Příklad                              |
| :-------------- |:---------------------------------------------------| :------------------------------------|
| allintext      | Searches for occurrences of all the keywords given. | `allintext:"keyword"` |
| intext      | Searches for the occurrences of keywords all at once or one at a time. | `intext:"keyword"` |
| inurl      | Searches for a URL matching one of the keywords. | `inurl:"keyword"` |
| allinurl      | Searches for a URL matching all the keywords in the query. | `allinurl:"keyword"` |
| intitle      | Searches for occurrences of keywords in title all or one. | `intitle:"keyword"` |
| allintitle      | Searches for occurrences of keywords all at a time. | `allintitle:"keyword"` |
| site      | Specifically searches that particular site and lists all the results for that site. | `site:"www.google.com"` |
| filetype      | Searches for a particular filetype mentioned in the query. | `filetype:"pdf"` |
| link      | Searches for external links to pages. | `link:"keyword"` |
| numrange      | Used to locate specific numbers in your searches. | `numrange:321-325` |
| before/after      | Used to search within a particular date range. | `filetype:pdf & (before:2000-01-01 after:2001-01-01)` |
| allinanchor (and also inanchor)      | This shows sites which have the keyterms in links pointing to them, in order of the most links. | `inanchor:rat` |
| allinpostauthor (and also inpostauthor)      | Exclusive to blog search, this one picks out blog posts that are written by specific individuals. | `allinpostauthor:"keyword"` |
| related      | List web pages that are “similar” to a specified web page. | `related:www.google.com` |
| cache      | Shows the version of the web page that Google has in its cache. | `cache:www.google.com` |

## Příklady Google Dorking
```text
site:pastebin.com intext:"@gmail.com"
intitle:"index of" "robots.txt"
filetype:xml sitemap.xml
intitle:"index of" ".js"
intitle:"index of" "backup"
inurl:admin filetype:php
intitle:"login page"
inurl:wp-content/uploads/ filetype:pdf
site:*.gov filetype:xls intext:"password"
inurl:/phpinfo.php
intext:"index of /"
Nina Simone intitle:”index.of” “parent directory” “size” “last modified” “description” I Put A Spell On You (mp4|mp3|avi|flac|aac|ape|ogg) -inurl:(jsp|php|html|aspx|htm|cf|shtml|lyrics-realm|mp3-collection) -site:.info
Bill Gates intitle:”index.of” “parent directory” “size” “last modified” “description” Microsoft (pdf|txt|epub|doc|docx) -inurl:(jsp|php|html|aspx|htm|cf|shtml|ebooks|ebook) -site:.info
parent directory DVDRip -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
parent directory MP3 -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
parent directory Name of Singer or album -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
filetype:config inurl:web.config inurl:ftp
“Windows XP Professional” 94FBR
ext:(doc | pdf | xls | txt | ps | rtf | odt | sxw | psw | ppt | pps | xml) (intext:confidential salary | intext:"budget approved") inurl:confidential
```

## Příklady - Ostatní
### GitHub Dorking
```text
filename:.env
filename:id_rsa
filename:credentials AWS_ACCESS_KEY_ID
filename:.ftpconfig password
extension:json api_key
filename:config db_password
path:/config/ password
extension:sql "INSERT INTO"
filename:.npmrc _auth

```
### Shodan Dorking
```text
"Server: SQUID"
org:"Amazon.com" port:22
product:"MongoDB" port:27017
country:"US" "default password"
http.title:"webcamXP 5"
ssl:"expired"
net:"192.168.1.0/24" port:80
os:"Windows 7"
```
### Censys Dorking
```text
services.service_name: HTTP AND services.http.response.body: "index of"
services.banner: "OpenSSH" AND location.country: "Germany"
services.tls.certificates.leaf_data.subject.common_name: "example.com"
services.http.response.headers.server: "nginx"
```
### ZoomEye Dorking
```text
app:"Apache httpd"
os:"Windows Server 2012 R2"
title:"login"
service:"ftp"
country:"CN" port:6379
```
---
zdroje:
* https://gist.github.com/sundowndev/283efaddbcf896ab405488330d1bbc06
* https://www.imperva.com/learn/application-security/google-dorking-hacking/
* https://cdn-cybersecurity.att.com/blog-content/GoogleHackingCheatSheet.pdf
* https://www.yeswehack.com/learn-bug-bounty/recon-hackers-guide-google-dorking
* https://www.maltego.com/blog/using-google-dorks-to-support-your-open-source-intelligence-investigations/
* https://www.scribd.com/document/944176646/Dorking-Cheat-Sheet
