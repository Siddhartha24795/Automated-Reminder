import datetime
import os
import bs4
import time
import requests
import pandas as pd
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
url="https://web.whatsapp.com/"
driver=webdriver.Chrome()
driver.get(url)
time.sleep(40)
#res=requests.get(url)
target="Siddarth Misha Iit Ism"

now=datetime.datetime.now()
h=int(now.strftime("%H"))
m=int(now.strftime("%M"))
timedelay=( ((22*60)+43)*60 - ((h*60)+m)*60  )

time.sleep(timedelay)

search=driver.find_element_by_xpath('//*[@id="side"]/div[1]/div/label/input')
search.send_keys(target)
search.send_keys(Keys.ENTER)
time.sleep(5)
textmsg=driver.find_element_by_xpath('//*[@id="main"]/footer/div[1]/div[2]/div/div[2]')
textmsg.send_keys(" HAPPY BIRTHDAY ")
textmsg.send_keys(Keys.ENTER)

time.delay(5)

driver.close()

os.system("shutdown /s /t 5")







