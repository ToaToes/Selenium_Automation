Python script that uses Selenium to automate a web browser. 
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# Set up the WebDriver (make sure you have the right driver for your browser)
driver = webdriver.Chrome()  # or webdriver.Firefox() for Firefox

try:
    # Open Google
    driver.get("https://www.google.com")

    # Find the search box
    search_box = driver.find_element(By.NAME, "q")

    # Type the search query
    search_box.send_keys("Selenium Python")
    search_box.send_keys(Keys.RETURN)  # Press Enter

    # Wait for results to load
    time.sleep(2)

    # Find the search result titles
    results = driver.find_elements(By.XPATH, "//h3")

    # Print the titles of the first few results
    for result in results[:5]:  # Adjust the slice as needed
        print(result.text)

finally:
    # Close the browser
    driver.quit()

```
