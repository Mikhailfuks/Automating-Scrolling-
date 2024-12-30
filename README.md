from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver_path = "/path/to/chromedriver" 
driver = webdriver.Chrome(executable_path=driver_path)

try:
    driver.get("https://www.example.com/longpage")


    driver.execute_script("window.scrollBy(0, 500);")

   
    driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")


    element = driver.find_element(By.TAG_NAME, "body") 
    element.send_keys(Keys.PAGE_DOWN) #Scroll down one page. Repeat as needed.

except Exception as e:
    print(f"An error occurred: {e}")
finally:
    driver.quit()

import pyautogui
import time

x, y = 100, 100 
scroll_amount = 50 #Adjust based on the scroll bar

try:

    for i in range(10): # Scroll 10 times
        pyautogui.moveTo(x, y)
        pyautogui.dragRel(0, scroll_amount, duration=0.25) #
        time.sleep(1) #Give some time for the application to update
except Exception as e:
    print(f"An error occurred: {e}")

