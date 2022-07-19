# Intercepting traffic with Burp Proxy

Intercepting a request -
  
  - Burp proxy lets you intercept HTTP requests and responses sent between Burp's browser and the target server
  - This enables you to study how the website behaves when you perform different actions.

### Step 1

  - Go to the Proxy > Intercept tab

  - Click the `intercept is off` button, so it toggles to `intercept on`
  
  - Click `open browser`. This launches Burps browser. which is preconfigured to work with Burp right out of the box.

### Step 2. Intercept a Request

  - Using Burp's browser, try to visit https://portswigger.net and observe that the site doesn't load. 
  
  - Burp Proxy has intercepted the HTTP request that was issued by the browser before it could reach the server. You can see this intercepted request on the Proxy > Intercept tab.
  
  - The request is held here so that you can study it, and even modify it, before forwarding to the target server

### Step 3. Forward the Request 

  - Click the forward button several times to send the intercept request, and any subsequent ones, until the page loads in Burp's browser.
  
### Step 4. Switch off the interception

  - Due to the number of requests browsers typically send, you often won't want to intercept every single one of them.
  - click the incercept is on button so that it now says Intercept is off.

  - Go back to the browser and confirm that you can now interact with the site as normal.

### Step 5. View the HTTP history

  - In Burp, go to the Proxy > HTTP history tab. Here, you can see the history of all HTTP traffic that has passed through Burp Proxy, even while interception was switched off.

  - Click on any entry in the history to view the raw HTTP request, along with the corresponding response from the server.

  - This lets you explore the website as normal and study the interactions between Burp's browser and the server afterward, which is more convenient in many cases.


