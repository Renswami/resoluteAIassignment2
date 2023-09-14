# resoluteAIassignment2
public class resolutionAIassignment2 {

WebDriver driver;	
	
	@BeforeTest
	public void setup() throws InterruptedException
	{
		System.setProperty("webdriver.chrome.driver","C:\\Users\\santosh\\Desktop\\selenium with jar\\chromedriver-win64\\chromedriver.exe");
		ChromeOptions option=new ChromeOptions();
		option.addArguments("--remote-allow-origins=*");
		  driver = new ChromeDriver(option);
		 
		driver.manage().window().maximize();
		
		driver.navigate().to("https://facegenie-ams-school.web.app/");
		Thread.sleep(1000);
	}

	@Test
	public void login()throws InterruptedException
	{
		WebElement email1 = driver.findElement(By.id("email"));
		email1.sendKeys("testbams@gmail.com");
	    Thread.sleep(2000);
	    
	    WebElement password1 = driver.findElement(By.id("password"));
		password1.sendKeys("facegenie");
	    Thread.sleep(2000);
	    
	    WebElement login= driver.findElement(By.xpath("//button[@type='submit']"));
		login.click();
	    Thread.sleep(18000);
	    
	}

	@AfterTest
	public void teardown()
	{
		driver.quit();	
	}

	
}	
	
	
	
	

