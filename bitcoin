#You can get the price of bitcoin 
from bs4 import BeautifulSoup
import urllib.request as req

#get HTML
url = "https://jpbitcoin.com/markets"
res = req.urlopen(url)
#analyze HTML
soup = BeautifulSoup(res, "html.parser")
#choose the data you want
price = soup.find('div', class_="price_ticker_container")
price_in_japan = price.find('span', class_="price").text
print("price of bitcoin in Japan        :", price_in_japan)
price2 = soup.find('div', class_="price_ticker_sub")
priceofbitcoin = price2.find_all('td')
for i, j in enumerate(priceofbitcoin):
    if i == 1:
        print("high price of bitcoin in 24 hours:", j.text)
    elif i == 3:
        print("low price of bitcoin in 24hours  :", j.text)
    elif i == 5:
        print("up/down",j.text, "from the dey before")
    elif i ==7:
        print("trade volume:", j.text)
    
