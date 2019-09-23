# Introduction

Welcome to the Visit Galaxy API Reference. If you don’t have an API key, get in touch with us.

The API gives you access to some of the citybreak functionaility, enabling you to search for products, get content, search availability and use shopping baskets for booking and generating pay-later invoices. 

This documentation is too long? You can check out the Swagger UI <a href="https://galaxy.test.citybreak.com/v3/">https://galaxy.test.citybreak.com/v3/</a>. It targets test data and you can request a test API key for internal products that you can make bookings and do availability searches for. Give it a try and come back later.

The live Galaxy API endpoint is accessible at <a href="https://galaxy.citybreak.com/v3/">https://galaxy.citybreak.com/v3/</a>

<aside class="warning">These are the docs for the V4 of the Galaxy API.<br/>
The docs for the V3 version of the galaxy API are found here <a href="https://visit.github.io/galaxy-docs-v3/">https://visit.github.io/galaxy-docs-v3/</a>.<br/>
The endpoint for V3 is <a href="https://galaxy.citybreak.com/v3/">https://galaxy.citybreak.com/v3/</a></aside>

<aside class="notice">One of the first queries you should try is the Point of Sale query as you will need a valid Point of Sale Id for most of the others</aside>
  
## Point of Sales
  
A point of sales is concept widely used in the Citybreak system, implementation will guide you about which one you should use.
The following settings can be configured per point of sales:
* Suppliers
* Business Model
* Fees
* Commissions
* Payment regulation
* Payment options

If you wish different combination of those settings for different purposes, you most likely would like to use more than 1 point of sales. Talk to our implementation team <a href='https://help.citybreak.com/'>help.citybreak.com</a>, they know all there is to know on the subject. 
