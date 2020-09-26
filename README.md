# Automation-testing-
All testing with java, Selenium, Automation, Jquery UI, 

package selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class dragdrop {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub

		System.setProperty("webdriver.chrome.driver", "C:\\Users\\bolatunj\\Desktop\\selenium\\chromedriver_win32\\chromedriver.exe");
		WebDriver chrome=new ChromeDriver();
		chrome.navigate().to("http://www.jqueryui.com");
		chrome.manage().window().maximize();
		
		chrome.findElement(By.linkText("Draggable")).click();
		Actions action=new Actions(chrome);
		action.sendKeys(Keys.PAGE_DOWN).perform();
		
		
		
		chrome.switchTo().frame(0);
		WebElement drag=chrome.findElement(By.id("draggable"));
		Thread.sleep(5000);
		
		action.moveToElement(drag).clickAndHold().moveByOffset(80, 80).perform();
		
		
	}
