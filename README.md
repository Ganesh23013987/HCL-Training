# HCL Training

## Manual Testing:

### Flipkart Testing Report:
https://docs.google.com/spreadsheets/d/1oqbQ1LGoaTKGryhhj43RrWJwRJk5ILJUMcS9z1sCQms/edit?usp=sharing

## Manual Testing Exercises:

### Date: 22/09/2026
https://docs.google.com/spreadsheets/d/1vXriuxRbOWr7nEhyCtD0dYGzM2cE6bt4jiBJ8_SzGUI/edit?usp=sharing

## Basic Python Programs
### Date: 23/09/2026
Github link: https://github.com/Ganesh23013987/HCL_Training_23.09.2026.git

## RailOne Application Testing metrics report:
### Date: 24//09/2026

https://1drv.ms/x/c/6BBA4D598AA71114/IQATSjjoiODiTKUPI1uwMlWiAb-rGE8QD_Xm0gki2NYp78I?e=fQuAbM

## Python Problems:
### Date: 25/09/2026


Python Programs: https://colab.research.google.com/drive/1wrB5S8mjn-gQ4NrEPJCweQKk32RLusYz?usp=sharing

## Numpy and Python programs Assignment:
### Date: 29/09/2026

https://colab.research.google.com/drive/1P7GT-ZsnWW6_D-eIPE_XLVW9dQJ2LTqm?usp=sharing

## Automation testing
### Date: 05/10/2026

### Task1: saucedemo.com website to login

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()


driver.get("https://www.saucedemo.com")

username = driver.find_element(By.ID, "user-name")
password = driver.find_element(By.NAME, "password")
login = driver.find_element(By.ID, "login-button")

username.send_keys("standard_user")
password.send_keys("secret_sauce")

print(username.get_attribute("placeholder"))
print(login.is_enabled())
print(username.is_displayed())

login.click()

time.sleep(20)

driver.quit()
```

<img width="869" height="93" alt="image" src="https://github.com/user-attachments/assets/509d8554-f977-439e-a09c-1d499ca6d4b2" />


### Task2: saucedemo.com website to list the products

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()

# Open the website
driver.get("https://www.saucedemo.com")

# Locate the elements
username_field = driver.find_element(By.ID, "user-name")
password_field = driver.find_element(By.NAME, "password")
login_button = driver.find_element(By.ID, "login-button")

# Enter login details
username_field.send_keys("standard_user")
password_field.send_keys("secret_sauce")


# Login
login_button.click()

time.sleep(3)

# Find all products
products = driver.find_elements(By.CLASS_NAME, "inventory_item_name")

# Print product list
print("\nProduct List:")

for product in products:
    print(product.text)

time.sleep(30)

driver.quit()
```
<img width="866" height="242" alt="image" src="https://github.com/user-attachments/assets/2cd27cfa-1218-414f-8322-e3fc7c7531ca" />

## Task3: Flipkart Website to login with user OTP verification

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Edge()
driver.maximize_window()

wait = WebDriverWait(driver, 20)

# Open Flipkart
driver.get("https://www.flipkart.com")

# Click Login
login = wait.until(
    EC.presence_of_element_located(
        (By.XPATH, "//span[normalize-space()='Login']")
    )
)
driver.execute_script("arguments[0].click();", login)

# Enter phone number
phone = wait.until(
    EC.visibility_of_element_located(
        (By.CSS_SELECTOR, "input.jwCbxy[type='number']")
    )
)

phone.clear()
phone.send_keys("7810048370")

print("Phone number entered")

# Click Continue
continue_btn = wait.until(
    EC.element_to_be_clickable(
        (By.XPATH, "//button[normalize-space()='Continue']")
    )
)

driver.execute_script("arguments[0].click();", continue_btn)

print("Continue clicked")
print("OTP page opened")

# Wait for OTP page
input("Enter OTP in terminal when you receive it: ")

```

### After otp verification login successful in flipkart website
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6531f194-37ee-4d22-b364-461e4189eddf" />


## Date: 06/10/2026
### Today Task:
```
rom selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Edge()

driver.maximize_window()

driver.get("https://vinothqaacademy.com/demo-site/")

time.sleep(5)

first_name = driver.find_element(By.ID, "vfb-5").send_keys("Ganesh")
time.sleep(2)

last_name = driver.find_element(By.ID, "vfb-7").send_keys("D")
time.sleep(2)

gender = driver.find_element(By.ID, "vfb-31-1").click()
time.sleep(2)

course_interest = driver.find_element(By.ID, "vfb-20-0").click()
time.sleep(2)

street_address = driver.find_element(By.ID, "vfb-13-address").send_keys("Navalar street, ullagaram")
time.sleep(2)

apt_suite = driver.find_element(By.ID, "vfb-13-address-2").send_keys("Apt 1")
time.sleep(2)

city = driver.find_element(By.ID, "vfb-13-city").send_keys("Chennai")
time.sleep(2)

postal_code = driver.find_element(By.ID, "vfb-13-zip").send_keys("600061")
time.sleep(2)

email = driver.find_element(By.ID, "vfb-14").send_keys("ganeshd2026@gmail.com")
time.sleep(15)

input("Press ENTER to close the browser...")

driver.quit()
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f9ea8647-8a7c-442e-87a2-1a18ba3ae659" />

