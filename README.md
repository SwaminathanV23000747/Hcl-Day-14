
# Task-1:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# TC01: Open page using get() and verify using XPath
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)  # Pause to let the page load

header = wait.until(
    EC.visibility_of_element_located((
        By.XPATH,
        "//h1[text()='Practice Form'] | //div[text()='Practice Form']",
    ))
)
time.sleep(4)  # Pause to view verified page

print(f"✓ TC01 Passed: {header.text}")
```
# output:
<img width="1912" height="1027" alt="image" src="https://github.com/user-attachments/assets/7c49aa75-db41-468d-a4fe-fd1efab7a097" />

# Task-2:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

 1. Open the page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

 2. TC02: Locate First Name using Attribute XPath [@id='firstName']
first_name = wait.until(EC.visibility_of_element_located((By.XPATH, "//input[@id='firstName']")))
first_name.send_keys("Swaminathan")
time.sleep(2)

 3. Locate Last Name using Attribute XPath [@id='lastName']
last_name = driver.find_element(By.XPATH, "//input[@id='lastName']")
last_name.send_keys("V")
time.sleep(2)

print("✓ TC02 Passed: Username fields located using Attribute XPath")

```
# output:
<img width="1917" height="1025" alt="image" src="https://github.com/user-attachments/assets/d4bb352f-f54f-4198-9da4-3590d472e8ea" />

# Task-3:
# Code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# 1. Open DemoQA Login Page
driver.get("https://demoqa.com/login")
time.sleep(3)

# 2. Locate Username via Attribute XPath
wait.until(
    EC.visibility_of_element_located((By.XPATH, "//input[@id='userName']"))
).send_keys("testuser")
time.sleep(2)

# 3. Task: Locate & Enter Password using Attribute XPath [@id='password']
password_field = driver.find_element(
    By.XPATH, "//input[@id='password' and @type='password']"
)
password_field.send_keys("SecretPassword123!")
time.sleep(2)

print("✓ TC03 Passed: Password entered using Attribute XPath")
```
# output:
<img width="1917" height="1022" alt="image" src="https://github.com/user-attachments/assets/a1704b24-5b76-4be8-b38a-545639f4da25" />

# Task-4:

# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# TC04: Locate Submit button using text() method
# Note: On this form, scrolling or using a JS click prevents ad overlays from blocking the button
submit_btn = wait.until(
    EC.presence_of_element_located((By.XPATH, "//button[text()='Submit']"))
)
driver.execute_script("arguments[0].scrollIntoView(true);", submit_btn)
time.sleep(2)

driver.execute_script("arguments[0].click();", submit_btn)
time.sleep(2)

print("✓ TC04 Passed: Submit button located using text() XPath")
```
# output:
<img width="1915" height="1021" alt="image" src="https://github.com/user-attachments/assets/79975213-d69b-4fea-8c58-0be0a651b4a5" />

# Task-5:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# TC06: Locate element using starts-with() prefix matching
# Matches <input id="userNumber"> or <input id="userEmail"> starting with 'user'
mobile_input = wait.until(
    EC.visibility_of_element_located((By.XPATH, "//input[starts-with(@id, 'userN')]"))
)
mobile_input.send_keys("9876543210")
time.sleep(2)

print("✓ TC06 Passed: Element located using starts-with() XPath")
```
# output:
<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/a8d09ec4-c340-4f6f-a58d-2aac56dd2019" />

# Task-6:
# code:
```

```
# output:

