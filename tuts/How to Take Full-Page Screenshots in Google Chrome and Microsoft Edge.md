# How to Take Full-Page Screenshots in Google Chrome and Microsoft Edge (No Extensions Required)

Capturing full-page screenshots of websites is essential for web developers, designers, and content creators. While browser extensions can help, **Google Chrome and Microsoft Edge** allow you to take full-page screenshots natively without any extra tools. In this guide, we'll cover the best way to capture full-page screenshots while ensuring the page fully loads first.

## **Method 1: Using DevTools (Built-in Feature)**

Google Chrome and Microsoft Edge both have a **Capture full-size screenshot** option built into Developer Tools. Here's how to use it:

### **Steps to Take a Full-Page Screenshot**

1. **Open the website** you want to capture in Chrome or Edge.
    
2. Press **F12** (or `Cmd + Option + I` on Mac) to open **Developer Tools**.
    
3. Open the **Command Menu** by pressing:
    
    - `Ctrl + Shift + P` on Windows/Linux
        
    - `Cmd + Shift + P` on Mac
        
4. Type **“Capture full size screenshot”** in the search box.
    
5. Click on the option, and the browser will generate and download a full-page screenshot.
    

### **Ensuring the Page Loads Fully Before Taking a Screenshot**

By default, the browser captures a screenshot instantly, but dynamic elements or lazy-loading content may not be fully loaded. To handle this, use JavaScript to **wait for the page to load** first:

#### **Using JavaScript to Wait for Full Page Load**

1. Open **Developer Tools (`F12`)** and go to the **Console** tab.
    
2. Paste the following JavaScript snippet and press **Enter**:
    
    ```js
    setTimeout(() => {
        document.scrollingElement.scrollTop = document.scrollingElement.scrollHeight;
        setTimeout(() => {
            console.log("Page loaded, taking screenshot...");
        }, 3000);
    }, 5000); // Adjust delay as needed
    ```
    
    - This script scrolls the page to trigger lazy-loading elements.
        
    - It waits 5 seconds, then another 3 seconds to ensure the page has loaded.
        
3. Now, open the **Command Menu (`Ctrl + Shift + P`)**, type **“Capture full size screenshot”**, and hit **Enter**.
    

## **Method 2: Automating Full-Page Screenshots with Puppeteer**

For developers who need automated full-page screenshots, **Puppeteer** (a Node.js library) is an excellent choice. It allows you to programmatically open a browser, wait for a page to load, and capture screenshots.

### **Using Puppeteer to Capture a Full-Page Screenshot**

1. **Install Puppeteer** (Node.js is required):
    
    ```bash
    npm install puppeteer
    ```
    
2. **Run the following script** to take a full-page screenshot:
    
    ```js
    const puppeteer = require('puppeteer');
    
    (async () => {
        const browser = await puppeteer.launch();
        const page = await browser.newPage();
        await page.goto('https://example.com', { waitUntil: 'networkidle2' });
        await page.screenshot({ path: 'screenshot.png', fullPage: true });
        await browser.close();
    })();
    ```
    
    - **`waitUntil: 'networkidle2'`** ensures that the page fully loads before capturing.
        
    - The screenshot is saved as `screenshot.png` in the working directory.
        

## **Alternative Methods**

If you're looking for other ways to capture full-page screenshots, here are a few options:

- **Firefox’s Built-in Screenshot Tool**: Press `Ctrl + Shift + S` (`Cmd + Shift + S` on Mac) and choose **Save full page**.
    
- **Online Screenshot Services**: Use sites like [screenshot.guru](https://screenshot.guru/) or [site-shot.com](https://www.site-shot.com/).
    
- **Browser Extensions**: If you prefer an extension, try **GoFullPage** or **Fireshot** (Chrome/Edge/Firefox).
    

## **Conclusion**

Taking full-page screenshots in Chrome and Edge is simple, and you don’t need extensions. Using **Developer Tools**, JavaScript tweaks, or Puppeteer automation, you can ensure that your screenshots capture the entire webpage **only after it has fully loaded**. Try these methods and streamline your workflow today!