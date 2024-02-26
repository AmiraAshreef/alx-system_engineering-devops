A user searches for "foobar" on their browser. Behind the scenes, a series of interactions take place to deliver your website:

User's Request: The user types "www.foobar.com [invalid URL removed]" into their browser.
DNS Lookup: The browser asks the Domain Name System (DNS) for the IP address associated with "www.foobar.com [invalid URL removed]." In this case, the DNS returns the server's IP address (8.8.8.8).
Connection Establishment: The browser establishes a network connection with the server at 8.8.8.8.
HTTP Request: The browser sends an HTTP request to the server, specifying the resource it wants (e.g., the homepage).
Web Server (Nginx): The web server receives the request. Its job is to serve static content like HTML, CSS, and images directly.
Dynamic Content: If the request needs dynamic content, the web server forwards it to the application server.
Application Server: The application server, running your code base, retrieves data from the database (MySQL) if needed and generates the dynamic content.
Response Sent: The application server sends the generated content back to the web server.
Delivery to User: The web server combines the static and dynamic content into a single HTTP response and sends it back to the user's browser.
Website Display: The browser receives the response, interprets the HTML, and displays the website to the user.
