# Code-test-2
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class ChromeBrowserTest {
public static void main(String[] args) {
       
System.setProperty("webdriver.chrome.driver", "C://Users//RAJU//OneDrive//Desktop//Jar files//chromedriver_win32//chromedrive.exe");

WebDriver driver = new ChromeDriver();

 driver.get("https://www.selenium.dev/");

WebElement downloadsLink = driver.findElement(By.linkText("Downloads"));
downloadsLink.click();

WebDriverWait wait = new WebDriverWait(driver, 10);
  wait.until(ExpectedConditions.urlToBe("https://www.selenium.dev/downloads/"));

WebElement javaTab = driver.findElement(By.cssSelector(".download-tab-java.active"));
        if (javaTab != null) {
System.out.println("Java tab is selected by default");
        }

WebElement pythonTab = driver.findElement(By.cssSelector(".download-tab-python"));
        pythonTab.click();

  wait.until(ExpectedConditions.presencOfElementLocated(By.cssSelector(".download-tab-python.active")));

WebElement downloadButton = driver.findElement(By.linkText("Download latest stable release"));
 downloadButton.click();

driver.quit();
    }
}

