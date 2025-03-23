# Homework 10. Server-side attacks. Part 3

## Task 1. SSRF

The target web application requests third-party stocks to get product number.  
The stock url is passed as request parameter, so it  can be changed to:

```bash
http://localhost/admin
```

![lab1-request-1](lab1-request-1.png)

The server responded with admin page:

![lab1-response-1](lab1-resposne-1.png)

From the page source take `Delete` button url:

![lab1-path](lab1-path.png)

And execute `stock` request again with this path:

![lab1-request-2](lab1-request-2.png)

The lab is solved 🎉

![lab1-solved](lab1-solved.png)
