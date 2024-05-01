# Selenium_demo

## Getting started with Selenium using JavaScript: Tutorial
Selenium offers great flexibility when it comes to testing. Whether it is platforms like Windows, Linux, Solaris, or the browsers like Chrome, Firefox, Edge, IE, or Safari, Selenium allows platform-independent, cross-browser test functionality with no licensing costs. Here’s how to get started with the Automated UI testing of an application using Selenium WebDriver and JavaScript:

### Prerequisites of the Setup Configuration
1. Node.js (comes bundled with npm, i.e. Node package manager). For those comfortable with using Maven in Java, consider this to be the equivalent package manager for JS.
2. Any IDE to write the code. The example in this article uses Visual Studio Code. 

### Step 1: Install Node.js npm
One can download Node.js and npm, and then check that it is installed by running the following commands in the terminal.
(https://nodejs.org/en/download)

To check Node.js is installed
```
node -v
```
To check npm is installed
```
npm -v
```
Once the user has installed Node.js, they will get access to the npm, an inbuilt package manager which will be used to install Selenium for JS.

### Step 2: Install Selenium WebDriver
One can download Selenium WebDriver, and install it by running the following command in the terminal by using the Node’s built-in package manager (NPM) to get the package.
```
npm install --save selenium-webdriver
```
(–-save creates a new package. This would be saved to the project’s package.json file.)

![image](https://github.com/quanggv1/selenium_demo/assets/22222802/8db0b319-8a01-4c6b-86da-01695e9814cc)


### Step 3: Install Visual Studio Code
https://code.visualstudio.com/download

### Step 4: Install Selenium Webdriver and Client language bindings
Selenium WebDriver and client language bindings are important to establish a connection between the WebDriver and the client and perform testing. Here are the links to install the Selenium WebDriver and client language bindings:

Download JavaScript Language Bindings

https://www.npmjs.com/package/selenium-webdriver

chrome driver: https://googlechromelabs.github.io/chrome-for-testing/

Selenium WebDriver v4.6+ (which you can download here). Note that you'll need to download the browser driver separately for Selenium WebDriver versions below 4.6; however, for version 4.6 and above, Selenium WebDriver uses a service object to render a browser window.


### Step 5: Run the test script

create file js test.js
```
const { Builder, By, until } = require("selenium-webdriver");
const assert = require("assert");

async function titleTest() {

  // launch the browser
  let driver = await new Builder().forBrowser("chrome").build();

  try {
    //navigate to google page
    await driver.get("https://www.google.com/");

    //Check page title, to confirm login was successful
    const pageTitle = await driver.getTitle();

    //assert using node assertion
    assert.strictEqual(pageTitle, "Google");
  } finally {
    await driver.quit();
  }
}

titleTest();
```

To run the test file, you use node and the following command in your terminal:
```
node test.js
```

If the test fails (such as when you enter the wrong credentials), the test will still run to completion. The following will be logged in the terminal:

Script exited with code 1.

This means that the test script returned a value of 1, which indicates that the test failed. In addition, the page title will not change.

![image](https://github.com/quanggv1/selenium_demo/assets/22222802/15453b54-f721-4d0e-97e5-06a5ff77a426)




