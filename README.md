# SPA Extensions

This is an SPA middleware which serve index.html if other middleware do not satisfy the request.  
In single page applications it is common that the client handles routes instead of the MVC controllers.  



# Usage
To use the middleware add it to the configuration section.  

    public void Configure(IApplicationBuilder app)
    {

	    // Add static files
	    app.UseStaticFiles();

	    // Add MVC
	    app.UseMvc();

	    // Add SPA
	    app.UseSpa(); 

	}

To change the default behaviour initialise as follows: 
	
    app.UseSpa(new SpaOptions() {
		DefaultHtml =  new PathString("/index.html"), 
		DebugMode = true // If the index.html is changing make sure to set the flag to Debug.  
	}); 
