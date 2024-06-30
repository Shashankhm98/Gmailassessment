ackage demolish;

import java.util.List;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class Gmail {

	
		public WebDriver driver;
		public static  void main(String[] args) throws InterruptedException
		{
			System.setProperty("webdriver.chrome.driver", "C:\\Users\\User\\eclipse-workspace\\Selenium\\Software\\chromedriver.exe");
			WebDriver driver = new ChromeDriver();
			driver.manage().timeouts().implicitlyWait(8,TimeUnit.SECONDS);
			driver.get("https://google.com");
			
		
			
			driver.findElement(By.xpath("//a[.='Sign in']")).click();
			driver.findElement(By.xpath("//input[@type='email']")).sendKeys("hmshashank04@gmail.com");
			driver.findElement(By.xpath("//span[.='Next']")).click();
			Thread.sleep(3000);
			driver.findElement(By.xpath("//input[@type='password']")).sendKeys("sHASHANK@7098");
			driver.findElement(By.xpath("//span[.='Next']")).click();
			driver.findElement(By.xpath("//a[@aria-label=\"Gmail \"]")).click();
			driver.findElement(By.xpath("//div[.='Compose']/div/div")).click();
			Thread.sleep(4000);
			driver.findElement(By.xpath("(//input[@aria-label='To recipients'])[1]")).sendKeys("hmshashank04@gmail.com");
					Thread.sleep(2000);
			driver.findElement(By.xpath("(//b[.='hmshashank04@gmail.com'])[1]")).click();
		WebElement	test = driver.findElement(By.xpath("(//input[ @placeholder='Subject'])[1]"));
		if (test.isDisplayed()) 
		{
			test.sendKeys("Test Mail");
		    System.out.println("Test Mail is verified");
		}
			WebElement Email = driver.findElement(By.xpath("(//div[ @aria-label=\"Message Body\"])[1]"));
			if (Email.isDisplayed())
			{
				Email.sendKeys("Test Email Body");
				System.out.println("Test Email Body is verified");
			}
			Thread.sleep(2000);
			driver.findElement(By.xpath("(//div[ @data-tooltip=\"More options\"])[1]")).click();
			driver.findElement(By.xpath("(//div[@role='menuitem'])[12]")).click();
			
	
			
		
		
		
			
			
		
			
			
		//driver.findElement(By.xpath("//div[@title='Social']")).click();
			Thread.sleep(3000);
			driver.findElement(By.xpath("//input[@aria-label=\"Label-as menu open\"]/../../div[5]")).click();
			WebElement  social = driver.findElement(By.xpath("//div[@title='Social']"));
			
			social.click();
			if (social.isSelected()) 
			{
				
				System.out.println("social is not verified");
			
			}
			else {
				
				System.out.println("social is  verified");
			}
			//driver.findElement(By.xpath("(//div[.='Apply'])[1]")).click();
			driver.findElement(By.xpath("(//div[.='Send'])[1]")).click();
			Thread.sleep(2000);
		driver.findElement(By.xpath("(//div[.='Primary'])[1]")).click();
			
			
		List<WebElement> unreademail = driver.findElements(By.className("zE"));



		System.out.println("Total No. of Unread Mails: " + unreademail.size());

		// real logic starts here

		for(int i=0;i<unreademail.size();i++){

		System.out.println(unreademail.get(i).getText());

		}

		unreademail.get(0).click();
		}
		//hmshashank04@gmail.com
	
	//shashankhms757@gmail.com
		

	}


