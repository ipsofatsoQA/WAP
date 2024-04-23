import time
import unittest
from selenium.webdriver.support import expected_conditions as EC
from selenium import webdriver
from selenium.webdriver import Keys
from selenium.webdriver.common.by import By
from selenium.webdriver.support.wait import WebDriverWait


class TestClass01(unittest.TestCase):
    def setUp(self):
        options = webdriver.ChromeOptions()
        mobile_emulation = {"deviceName": "Nexus 5"}
        options.add_experimental_option("mobileEmulation", mobile_emulation)
        driver = webdriver.Chrome(options=options)
        self.driver = driver
        print("\nIn setUp()...")

    def tearDown(self):
        print("\nIn tearDown")
        self.driver.close()
        self.driver.quit()

    def test_case01(self):
        print("\nIn test_case01()...")
        self.driver.get("https://m.twitch.tv/")
        WebDriverWait(self.driver, 20).until(
            EC.element_to_be_clickable((By.CSS_SELECTOR, ".ScCoreButtonPrimary-sc-ocjdkq-1"))).click()
        self.driver.find_element(By.CSS_SELECTOR, ".hSqeuh > a:nth-child(1)").click()
        WebDriverWait(self.driver, 20).until(
            EC.element_to_be_clickable((By.CSS_SELECTOR, ".ScInputBase-sc-vu7u7d-0"))).send_keys("StarCraft II",
                                                                                                 Keys.RETURN)
        scrollMouse= WebDriverWait(self.driver, 20).until(EC.element_to_be_clickable(
            (By.CSS_SELECTOR, 'section.Layout-sc-1xcs6mc-0:nth-child(4) > div:nth-child(1) > p:nth-child(1)')))
        self.driver.execute_script('arguments[0].scrollIntoView(true);', scrollMouse)
        WebDriverWait(self.driver, 20).until(EC.element_to_be_clickable(
            (By.CSS_SELECTOR, "div.kVcxNv:nth-child(3) > a:nth-child(1) > div:nth-child(1)"))).click()
        time.sleep(5)
        self.driver.get_screenshot_as_file('screenshot2.png')
