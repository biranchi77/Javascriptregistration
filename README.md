# Javascriptregistration
Register using java script in selenium (when necessary)
package web_driver;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Register_javascript {

	public static void main(String[] args) throws Throwable {
		// TODO Auto-generated method stub
		System.setProperty( "webdriver.chrome.driver","E:\\Chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.manage().deleteAllCookies();
        driver.get("https://demo.opencart.com/");
        JavascriptExecutor js =(JavascriptExecutor)driver;
        Thread.sleep(5000);

        
        driver.findElement(By.xpath("//span[normalize-space()='My Account']")).click();
        driver.findElement(By.linkText("Register")).click();
        driver.findElement(By.name("firstname")).sendKeys("biranchi");
        driver.findElement(By.name("lastname")).sendKeys("sadangi");
        driver.findElement(By.name("email")).sendKeys("biranchi00@gmail.com");
        driver.findElement(By.name("password")).sendKeys("badal@123");
        Thread.sleep(2000);
        js.executeScript("windows.scrollBy(0,400)");
        js.executeScript("document.querySelector(\"#input-newsletter-yes\").click()");
        js.executeScript("document.querySelector(\"input[value='1'][name='agree']\").click()");
        js.executeScript("document.querySelector(\"button[type='submit']\").click()");
        driver.quit();
        
        
        
        

	}

}
