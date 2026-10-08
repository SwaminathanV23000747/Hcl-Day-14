
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
<img width="1892" height="1013" alt="image" src="https://github.com/user-attachments/assets/219ce5c1-cc5e-4769-b292-8eda134f401c" />
# Task-07:
# Code:
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

# TC07: Locate input using TWO attributes with 'and'
# Matches <input id="userEmail" type="text">
email_field = wait.until(
    EC.visibility_of_element_located((By.XPATH, "//input[@id='userEmail' and @type='text']"))
)
email_field.send_keys("teststudent@example.com")
time.sleep(4)

print("✓ TC07 Passed: Input located using two attributes with 'and'")
```
# output:
<img width="1912" height="1026" alt="image" src="https://github.com/user-attachments/assets/3d8bfcde-c0bc-4749-aa0d-926a2327e62c" />
# Task-08:
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

# TC08: Locate element using alternatives with 'or'
# Matches element if EITHER @id='userName' OR @id='firstName' is true
first_name = wait.until(
    EC.visibility_of_element_located((By.XPATH, "//input[@id='userName' or @id='firstName']"))
)
first_name.send_keys("Swaminathan")
time.sleep(2)

print("✓ TC08 Passed: Element located using 'or' alternative XPath")
```
# output:
<img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/420643bd-1a5a-4333-9601-b8b38944875b" />
# Task9:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

 Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

 TC09: Locate the parent <form> element using the parent / ancestor axis
 Starts from an input field and navigates up to the parent form (#userForm)
user_form = wait.until(
    EC.presence_of_element_located((By.XPATH, "//input[@id='firstName']/ancestor::form[@id='userForm']"))
)
time.sleep(2)

print("✓ TC09 Passed: Parent form located!")
print(f"  Tag Name : {user_form.tag_name}")
print(f"  Form ID  : {user_form.get_attribute('id')}")
```
# output:
<img width="1908" height="1010" alt="image" src="https://github.com/user-attachments/assets/d52ff0a4-6e97-4405-b0e5-a6201bd64339" />
# Task 10:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

 Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

 TC10: Locate the enclosing <form> using the 'ancestor' axis starting from <input>
 Syntax: //tag[conditions]/ancestor::target_tag
form_element = wait.until(
    EC.presence_of_element_located((
        By.XPATH,
        "//input[@id='firstName']/ancestor::form[@id='userForm']",
    ))
)
time.sleep(2)

print("✓ TC10 Passed: Form located from input using ancestor axis!")
print(f"  Tag Name : {form_element.tag_name}")
print(f"  Form ID  : {form_element.get_attribute('id')}")
```
# output:
<img width="692" height="92" alt="image" src="https://github.com/user-attachments/assets/f737fef1-bd20-4d41-a5d7-23e3308aba5e" />

# Task 11:
# code:
```
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.by import By

chrome_options = Options()
chrome_options.add_experimental_option("detach", True)

driver = webdriver.Chrome(options=chrome_options)
driver.get("https://www.tutorialspoint.com/selenium/practice/login.php")

child_inputs = driver.find_elements(By.XPATH, "//form//input")
print(len(child_inputs))
```
# output:
<img width="663" height="60" alt="image" src="https://github.com/user-attachments/assets/da660faa-d8d1-4f76-aea2-f292b6b9d611" />
# Task 12:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

 Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

 TC12: Locate the next element using the following axis
 Starts at First Name and locates the following input element in document order (Last Name)
last_name = wait.until(
    EC.visibility_of_element_located((
        By.XPATH,
        "//input[@id='firstName']/following::input[@id='lastName']",
    ))
)
last_name.send_keys("V")
time.sleep(2)

print("✓ TC12 Passed: Next element located using following axis")
print(f"  Field Placeholder: {last_name.get_attribute('placeholder')}")
```
# output:
<img width="693" height="65" alt="image" src="https://github.com/user-attachments/assets/517ca39d-0f35-4b20-b625-155743ac3700" />
# Task 13:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

 Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# Scroll down slightly so the hobbies section is in view
driver.execute_script("window.scrollBy(0, 300);")
time.sleep(1)

# TC13: Locate Checkbox label using Attribute XPath [@for='hobbies-checkbox-1']
# (1 = Sports, 2 = Reading, 3 = Music)
sports_checkbox = wait.until(
    EC.element_to_be_clickable((By.XPATH, "//label[@for='hobbies-checkbox-1']"))
)
sports_checkbox.click()
time.sleep(2)

print("✓ TC13 Passed: Checkbox located and checked using Attribute XPath")
```
# output:
<img width="1917" height="1026" alt="image" src="https://github.com/user-attachments/assets/3ad84f96-3836-4a7a-a5b0-fc4751c9d840" />


# Task -14:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# TC14: Locate Radio Button using Attribute XPath
# Option 1: Click the visible <label> via @for attribute matching the radio input ID
male_radio_label = wait.until(
    EC.element_to_be_clickable((By.XPATH, "//label[@for='gender-radio-1']"))
)
male_radio_label.click()
time.sleep(2)

print("✓ TC14 Passed: Radio button selected using Attribute XPath")
```
# output:
<img width="1911" height="1017" alt="image" src="https://github.com/user-attachments/assets/62e48109-e7b5-44a7-8a27-6fc56277add1" />
# Task -15:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import Select, WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# 1. Click the Date of Birth input field to open the calendar pop-up
dob_input = wait.until(
    EC.element_to_be_clickable((By.XPATH, "//input[@id='dateOfBirthInput']"))
)
dob_input.click()
time.sleep(1)

# 2. TC15: Locate dropdown using XPath and wrap with Selenium's Select class
# Locate Month dropdown: <select class="react-datepicker__month-select">
month_dropdown_element = wait.until(
    EC.presence_of_element_located(
        (By.XPATH, "//select[@class='react-datepicker__month-select']")
    )
)
month_select = Select(month_dropdown_element)
month_select.select_by_visible_text("May")  # Select month by visible text
time.sleep(2)

# Locate Year dropdown: <select class="react-datepicker__year-select">
year_dropdown_element = driver.find_element(
    By.XPATH, "//select[@class='react-datepicker__year-select']"
)
year_select = Select(year_dropdown_element)
year_select.select_by_value("2004")  # Select year by attribute value
time.sleep(2)

# Pick day '15' to finish selection
day_15 = driver.find_element(
    By.XPATH,
    "//div[contains(@class,'react-datepicker__day--015') and not(contains(@class,'--outside-month'))]",
)
day_15.click()
time.sleep(2)

print("✓ TC15 Passed: Dropdown selected using XPath + Select class")
```
# output:
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/9d4e8fa0-1a10-490d-a0e6-6fa6816bcf65" />

# Task -16:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# TC16: Locate the second text input box using an XPath index [2]
# Wrapping the general locator in parentheses creates a node-set, then [2] picks the 2nd one
second_textbox = wait.until(
    EC.visibility_of_element_located((
        By.XPATH,
        "(//input[@type='text'])[2]",
    ))
)
second_textbox.send_keys("V")
time.sleep(2)

print("✓ TC16 Passed: Second textbox located using XPath index [2]")
print(f"  Field ID: {second_textbox.get_attribute('id')}")
print(f"  Placeholder: {second_textbox.get_attribute('placeholder')}")
```
# output:
<img width="600" height="77" alt="image" src="https://github.com/user-attachments/assets/dfdcc23a-d785-41be-b6e0-7f65e16cf6a7" />

# Task -17:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# 1. Fill mandatory fields to trigger the modal
wait.until(
    EC.visibility_of_element_located((By.XPATH, "//input[@id='firstName']"))
).send_keys("Swaminathan")

driver.find_element(By.XPATH, "//input[@id='lastName']").send_keys("V")
driver.find_element(By.XPATH, "//input[@id='userNumber']").send_keys("9876543210")

# Select Gender radio label
driver.find_element(By.XPATH, "//label[@for='gender-radio-1']").click()
time.sleep(1)

# 2. Click Submit
submit_btn = driver.find_element(By.XPATH, "//button[@id='submit']")
driver.execute_script("arguments[0].scrollIntoView(true);", submit_btn)
driver.execute_script("arguments[0].click();", submit_btn)
time.sleep(2)

# TC17: Locate and verify submitted confirmation message using text()
# HTML: <div class="modal-title h4" id="example-modal-sizes-title-lg">Thanks for submitting the form</div>
success_message = wait.until(
    EC.visibility_of_element_located((
        By.XPATH,
        "//div[text()='Thanks for submitting the form']",
    ))
)
time.sleep(2)

# Verification check
expected_text = "Thanks for submitting the form"
actual_text = success_message.text.strip()
assert actual_text == expected_text, f"Expected '{expected_text}', got '{actual_text}'"

print("✓ TC17 Passed: Submission message verified using text() XPath!")
print(f"  Verified Message: '{actual_text}'")
```
# output:
<img width="1901" height="1018" alt="image" src="https://github.com/user-attachments/assets/a39a31e8-9734-4fdf-b367-95c4bb54020f" />

# Task -18:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# Ensure the form is loaded
wait.until(
    EC.presence_of_element_located((By.XPATH, "//form[@id='userForm']"))
)

# TC18: Locate all input fields using find_elements() with XPath
# Finds every <input> tag inside the form
all_inputs = driver.find_elements(By.XPATH, "//form[@id='userForm']//input")
time.sleep(2)

print(f"✓ TC18 Passed: Found {len(all_inputs)} input fields using find_elements()")
print("-" * 50)

# Iterate and display details for each input element
for index, element in enumerate(all_inputs, start=1):
    input_type = element.get_attribute("type") or "N/A"
    input_id = element.get_attribute("id") or "N/A"
    input_name = element.get_attribute("name") or "N/A"
    placeholder = element.get_attribute("placeholder") or "N/A"
    print(f"[{index:02d}] ID: {input_id:<20} | Type: {input_type:<10} | Placeholder: {placeholder}")
```
# output:
<img width="685" height="200" alt="image" src="https://github.com/user-attachments/assets/acb42a60-9ba4-4b65-978c-8af95404d87a" />

# Task -19:
# code:
```
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 10)

# Open page
driver.get("https://demoqa.com/automation-practice-form")
time.sleep(3)

# TC19: Locate a dynamic element using contains() on an attribute
# On dynamic pages where IDs or classes have generated prefixes/suffixes,
# contains() targets the stable portion of the string.
# Example: Matches <input id="userEmail"> via substring 'Email'
dynamic_email = wait.until(
    EC.visibility_of_element_located((
        By.XPATH,
        "//input[contains(@id, 'Email')]",
    ))
)
dynamic_email.send_keys("swaminathan@example.com")
time.sleep(2)

# Another common dynamic example on DemoQA: Calendar day cells with dynamic class names
# HTML: <div class="react-datepicker__day react-datepicker__day--015 ...">
# XPath: //div[contains(@class, 'react-datepicker__day--015')]

print("✓ TC19 Passed: Dynamic element located using contains() XPath")
print(f"  Located Element ID: {dynamic_email.get_attribute('id')}")
```
# output:
<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/f1693799-0829-4656-b205-0cb67cac3ca5" />

# Task -20:
# code:
```
import os
import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import Select, WebDriverWait

driver = webdriver.Chrome()
driver.maximize_window()
wait = WebDriverWait(driver, 10)

try:
    # 1. Open DemoQA Practice Form
    driver.get("https://demoqa.com/automation-practice-form")
    time.sleep(2)

    # 2. First Name: starts-with() XPath
    first_name = wait.until(
        EC.visibility_of_element_located(
            (By.XPATH, "//input[starts-with(@id, 'firstN')]")
        )
    )
    first_name.send_keys("Swaminathan")

    # 3. Last Name: XPath following axis
    last_name = driver.find_element(
        By.XPATH, "//input[@id='firstName']/following::input[@id='lastName']"
    )
    last_name.send_keys("V")

    # 4. Email: contains() XPath
    email = driver.find_element(
        By.XPATH, "//input[contains(@id, 'userEmail')]"
    )
    email.send_keys("swaminathan@example.com")

    # 5. Gender: Attribute XPath targeting label
    male_radio = driver.find_element(
        By.XPATH, "//label[@for='gender-radio-1']"
    )
    male_radio.click()

    # 6. Mobile: Logical 'and' with two attributes
    mobile = driver.find_element(
        By.XPATH, "//input[@id='userNumber' and @type='text']"
    )
    mobile.send_keys("9876543210")

    # 7. Date of Birth: XPath + Select class
    dob_field = driver.find_element(
        By.XPATH, "//input[@id='dateOfBirthInput']"
    )
    dob_field.click()
    time.sleep(1)

    # Month Select
    month_dropdown = driver.find_element(
        By.XPATH, "//select[@class='react-datepicker__month-select']"
    )
    Select(month_dropdown).select_by_visible_text("May")

    # Year Select
    year_dropdown = driver.find_element(
        By.XPATH, "//select[@class='react-datepicker__year-select']"
    )
    Select(year_dropdown).select_by_value("2004")

    # Day selection using contains() class
    day_cell = driver.find_element(
        By.XPATH,
        "//div[contains(@class, 'react-datepicker__day--015') and not(contains(@class, 'outside-month'))]",
    )
    day_cell.click()

    # 8. Subjects: Dynamic input using text() context and ancestor axis
    subjects_input = driver.find_element(
        By.XPATH,
        "//label[text()='Subjects']/ancestor::div[@id='subjects-wrapper']//input",
    )
    subjects_input.send_keys("Computer Science")
    subjects_input.send_keys(Keys.ENTER)

    # 9. Hobbies: Alternative 'or' condition on labels
    hobby_checkbox = driver.find_element(
        By.XPATH,
        "//label[@for='hobbies-checkbox-1' or @for='hobbies-checkbox-2']",
    )
    driver.execute_script("arguments[0].click();", hobby_checkbox)

    # 10. Current Address: Textarea via Attribute XPath
    address = driver.find_element(
        By.XPATH, "//textarea[@id='currentAddress']"
    )
    address.send_keys("Saveetha Engineering College, Chennai, Tamil Nadu")

    # 11. State & City: Custom React dropdowns via XPath descendant axis
    driver.execute_script("window.scrollBy(0, 300);")
    time.sleep(1)

    # Open State dropdown
    state_box = driver.find_element(
        By.XPATH, "//div[@id='state']//input"
    )
    state_box.send_keys("NCR")
    state_box.send_keys(Keys.ENTER)
    time.sleep(1)

    # Open City dropdown
    city_box = driver.find_element(
        By.XPATH, "//div[@id='city']//input"
    )
    city_box.send_keys("Delhi")
    city_box.send_keys(Keys.ENTER)
    time.sleep(1)

    # 12. Submit Button: text() XPath
    submit_btn = driver.find_element(
        By.XPATH, "//button[text()='Submit']"
    )
    driver.execute_script("arguments[0].click();", submit_btn)

    # 13. Verify Modal: Modal verification using text() & ancestor/descendant inspection
    modal_title = wait.until(
        EC.visibility_of_element_located(
            (By.XPATH, "//div[text()='Thanks for submitting the form']")
        )
    )
    print("✓ Modal displayed:", modal_title.text)

    # Retrieve all submission table rows using find_elements()
    table_rows = driver.find_elements(
        By.XPATH, "//div[@class='table-responsive']//tbody/tr"
    )
    print("\n--- Submitted Data Summary ---")
    for row in table_rows:
        label = row.find_element(By.XPATH, "./td[1]").text
        value = row.find_element(By.XPATH, "./td[2]").text
        print(f"{label:<20} : {value}")

    print("\n✓ TC20 Passed: Complete Registration Suite executed successfully!")

finally:
    time.sleep(4)
    driver.quit()
```
# output:
<img width="1916" height="1023" alt="image" src="https://github.com/user-attachments/assets/ca7c6c3a-f9c3-4d79-b51c-07efb5e224f9" />
