//////////////////////////////////////////////////////////////////////////////////
//						
//						Identity User Role Management
//						
//////////////////////////////////////////////////////////////////////////////////


1. Introduction
==================================================================================

Thank you for installing Identity User Role Management. This NuGet package 
provides UI based User and Role Management for ASP.NET MVC applications using 
ASP.NET Identity.


2. Initilization Instructions
==================================================================================
	1. Install the NuGet package 
	2. Configure the DefaultConnection of the web.config file to point to the 
	   desired database
	3. Run the application and call the InitAdmin controller
	   EX: localhost:1234/InitAdmin
	4. Enter the desired email and password for the administrator and submit

*********************************************************************************
*********************************************************************************
*****																		*****
*****								WARNING									*****
*****																		*****
*********************************************************************************
*********************************************************************************

It is highly recommended that you delete or lock down the InitAdmin controller 
and views before deployment due to security issues. The InitAdmin functions
can be used to create additional Admin accounts even after initialization. 


3. Usage Instructions
==================================================================================

	1. To manage users call the UsersAdmin index view (domain.com/UsersAdmin)

	2. To manage roles call the RolesAdmin index view (domain.com/RolesAdmin)

	3. Add the following code to your main navigation menu to easily provide secured
	   access to the UsersAdmin and RolesAdmin

		@if (Request.IsAuthenticated && User.IsInRole("Admin"))
		{
				<a href="@Url.Action("Index","UsersAdmin")">Users Admin</a>
				<a href="@Url.Action("Index","RolesAdmin")">Rules Admin</a>
		}

==================================================================================

Happy Coding!

Jason Presley
http://www.jasonpresley.me