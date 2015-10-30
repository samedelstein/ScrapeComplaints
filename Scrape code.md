
Complaints


```python
import urllib2
from bs4 import BeautifulSoup

f = open('CityLine.txt', 'w')

for number in range (1,50):
    link = 'http://ipsweb.ci.syracuse.ny.us/viewtranscomplaint.aspx?id=' + str(number)
    page = urllib2.urlopen(link)
    soup = BeautifulSoup(page)
    
    complaintRecord = soup.find("span", {"id": "content_headerrecordnumber_lblRecord"}).string
    address = soup.find("span", {"id": "content_headeraddress_lblAddress"}).string
    complaintType = soup.find("span", {"id": "content_line1description_lblType"}).string
    status = soup.find("span", {"id": "content_line2description_lblStatus"}).string
    description = soup.find("span", {"id": "content_descriptiondescription_lblDescription"}).string
    action = soup.find("td", {"colspan": "2"})


    tags = soup.select('tr td[colspan,rowspan]')
    x = str(complaintRecord) + "|" + str(address) + "|" + str(complaintType) + "|" + str(status) + "|" + str(description) + "\n"
    
    for s in x:
        f.write(s)

```

Permit Application


```python
import urllib2
from bs4 import BeautifulSoup

f = open('PermitApplication.txt', 'w')

for number in range (1,50):
    link = 'http://ipsweb.ci.syracuse.ny.us/viewtranspa.aspx?id=' + str(number)
    page = urllib2.urlopen(link)
    soup = BeautifulSoup(page)
    
    permitApp = soup.find("span", {"id": "content_headerrecordnumber_lblRecord"}).string
    address = soup.find("span", {"id": "content_headeraddress_lblAddress"}).string
    date = soup.find("span", {"id": "content_headerdate_lblDate"}).string
    permitType = soup.find("span", {"id": "content_line2description_lblType"}).string
    description = soup.find("span", {"id": "content_descriptiondescription_lblDescription"}).string
    
    x = str(permitApp) + "|" + str(address) + "|" + str(date) + "|" + str(permitType) + "|" + str(description) + "\n"
    
    for s in x:
        f.write(s)
```

Permit


```python
import urllib2
from bs4 import BeautifulSoup

f = open('Permit.txt', 'w')

for number in range (1,50):
    link = 'http://ipsweb.ci.syracuse.ny.us/viewtranspermit.aspx?id=' + str(number)
    page = urllib2.urlopen(link)
    soup = BeautifulSoup(page)
    
    permitNum = soup.find("span", {"id": "content_headerrecordnumber_lblRecord"}).string
    address = soup.find("span", {"id": "content_headeraddress_lblAddress"}).string
    date = soup.find("span", {"id": "content_headerdate_lblDate"}).string
    permitType = soup.find("span", {"id": "content_line2description_lblType"}).string
    status = soup.find("span", {"id": "content_line3description_lblStatus"}).string
    description = soup.find("span", {"id": "content_descriptiondescription_lblDescription"}).string
    
    x = str(permitApp) + "|" + str(address) + "|" + str(date) + "|" + str(permitType) + "|" + str(status) + "|" + str(description) + "\n"
    
    for s in x:
        f.write(s)
```
