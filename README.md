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

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6531f194-37ee-4d22-b364-461e4189eddf" />
