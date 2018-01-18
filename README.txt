I did this project with Sunayan Shaik.
The complete User part was done by me. Complete Admin part was handled by her. 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
To run this project I have made changes in my .profile, setting correct url for oracle and mysql so that I could run it with URL = http://topcat.cs.umb.edu:51460/music3
while in university network. The context.xml file is setup accordingly. You will find the project here.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------


Project work done by me:
-------------------------
1. MusicSystemConfig was setup to get the connection and objects of service layer(sales and catalog). context.xml was altered.
2. CatalogDispatcherServlet is used for doing work related to product, track,cart and download 
3. SalesDispatcherServlet is used for doing work related to invoices,Lineitems and site_user 
4. Becareful It's totaly Independent of each other I mean catalogService is accessable only through CatalogDispatcherServlet and salesService is accessable only through SalesDispatcherServlet.
they call each other internally if needed.
5.The whole projects works Properly.  
6. Implemented cookies. Please be exctra carefull but I have tried my best to avoid pitfalls due to it. To erase the cookie the browser has to be closed and restarted.
Please take care when you change database as cookie might still hold user data.    

*******************************************************************************************************************************************************************************************
Dispacters
---------------
CatalogDispatcherServlet: It receives the request then accordingly goes to different controller and return. 
SalesDispatcherServlet: It receives the request then accordingly goes to different controller and return.

Controlle: Interface
-----------------------
Controller Interface was made for the controllers.


Catalog Controllers
--------------------
CartViewController: implements all the task related to cart.
	-cartPageBuild: build the cart page
	-DeleteCart: delete the cart
	-handleRequest: creates cart also product is added to the cart
	-InvoicetoSales: for genarating invoices I do Total cost calculation and save attribute in the session.
	-UpdateCart: it updates the quantity of the product in the cart.
	-CalculateTotal: does BigDecimal Calculations

CatalogViewController: it is used to build catalog.
	-handleRequest: gets data from catalogservice and build the Catalog page via jsp.
	
InvoiceViewController: called after user Checkout from cart
	-handleRequest : updates Invoice table 
	
ListenViewController: get you the song you had selected.
	-handleRequest: it saves necessary Information about selected track then call SalesDispatcherServlet for user Validation 
	-listenRequest: updates the download table and gets you the selected song(buffering of the browser).

ProductViewController: gets you details of the product after you select it in the catalog page.
	-handleRequest
	
RegisterUserController: Validates User 
	-CheckUser: checks three condition user could be in the session, in the cookie(1. in the cookie and also in the databse 2.in the cookie but not in database) or totally new user.
	-handleRequest: updates the user in the database.
	
TrackViewController: 
	-handleRequest: 
	
UserViewController:
	-handleRequest: gets user detail if in the cookie or check whether cookie there but user not ther in the database(whens if we reload the database but didn't close the browser)

	******************************************************************************************************************************************************************************************

	WebContent\WEB-INF\jsp
	--------------------------
	cart.jsp: cart page
	catalog.jsp : catalog page
	checkOutRegister.jsp : checkout user validation page
	invoice.jsp : invoice page
	product.jsp : product page
	register.jsp : user validation while downloading
	track.jsp : tracklist page
	welcome.jsp : home page
	
	
	WebContent/include
	------------------
	header.jsp
	footer.jsp
	sidebar.jsp
	
	
	WebContent/styles
	------------------
	header.css
	main.css
	sidebar.css
	
	
	WebContent/error
	-----------------
	error_404.jsp
	java_error.jsp
	
	
	
option implemented as seen on the welcome page
-----------------------------------------------
Catalog: home page
cart: home page
home button : home page


	
	
	
	
 
