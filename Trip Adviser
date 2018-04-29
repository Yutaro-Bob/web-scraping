#This code can get the famous sightseeing spots in Seattle and use Trip Adviser.
import urllib.request
from bs4 import BeautifulSoup
from time import sleep
import urllib
#This function can extract name and value
def tripadvisor(x):
    html = urllib.request.urlopen(url)
    soup = BeautifulSoup(html, "html.parser")
    sleep(1) #not to damage server(1second or more)
    sight = soup.find('div', class_='attraction_list attraction_list_short ')
    name = sight.find_all('div', class_='attraction_element')
    
    for i in name:
        name1 = i.find('div', class_='listing_title')
        name2 = name1.find('a')
        #name of spot
        name3 = name2.text
        #extract spot's URL
        href = name2.attrs["href"]
        
        if i.find('div', class_='rs rating') is not None:
            rate = i.find('div', class_='rs rating')
            rate2 = rate.find('span')
            #extract value
            rate1 = rate2.attrs.get('alt')
            
            if  x+1 > int(rate1[12]) >= x:
                print(name3)
                print(rate1)
                
#URL
x = input("5段階中幾つの観光地に行きたいですか？　1から5の整数で入力してください")#Which spots do you want to go? Enter the integer number from 1 to 5. to 
print("評価が", x,"点以上の観光地です")# These are the spots which is higher than x.
url = "https://www.tripadvisor.jp/Attractions-g60878-Activities-Seattle_Washington.html#FILTERED_LIST"
tripadvisor(int(x))
for i in range(300, 480, 30):
    url = "https://www.tripadvisor.jp/Attractions-g60878-Activities-oa"+ str(i) +"-Seattle_Washington.html#ATTRACTION_SORT_WRAPPER"
    sleep(1)


    
    

