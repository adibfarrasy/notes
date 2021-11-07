### What is DNS and how does it work

DNS = Domain Name System

DNS translates domain name to an IP address.
Domain Name is any text that is entered in the web browser URL field.
IP address is a set of numbers that represents where the request is sent to.

DNS resolver acts as a phonebook on the Internet. The DNS resolver search the name and match it to the IP address.

### DNS Lookup
1. User enters a website address/ domain name. The cache memory in the web browser checks if it has the address that the user is looking for. If it doesn't have it, it will forward the name to the DNS resolver.
2. The DNS resolver looks at its own cache. If it doesn't have the name, the request will be routed to the root server.
3. The root server (managed by 12 organizations worldwide) sends back the address of Top Level Domain (TLD) server to the DNS resolver.
4. The DNS resolver sends the request to the TLD server. The TLD is the back part of the website name (.com, .org, etc.). 
5. TLD server sends back the IP address of the Authority Name server to the DNS resolver.
6. The DNS resolver sends the request to the Authority Name server.
7. The Authority Name server sends back the requested IP address of the website to the DNS resolver, which is passed back to the browser.
8. The browser sends the request to the IP address.

source: https://www.youtube.com/watch?v=nyH0nYhMW9M