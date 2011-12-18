Zeus - A RESTful Bundle for Zend Framework 1.x
==============================================

The main purpose of *Zeus* is to help you easily create hierarchical 
routes to RESTful controllers.  

The initial code base for Zeus was created by @weierophinney over a 
series of articles on his blog, http://mwop.net/blog  

Allow me to give credit where credit is due:  

* Building RESTful Services with Zend Framework [1]  
* Responding to Different Context Types in RESTful ZF Apps [2]  

 [1]: http://mwop.net/matthew/archives/228-Building-RESTful-Services-with-Zend-Framework.html  
 [2]: http://mwop.net/blog/233-Responding-to-Different-Content-Types-in-RESTful-ZF-Apps  

Why Zeus?
---------

 > There are so many different RESTful implementations for Zend 
 > Framework, why bother creating another one?

The great majority of Zend Framework RESTful implementation require 
you to use *Zend_Rest_Route*. By default, *Zend_Rest_Route* creates
these routes:  

      /product/ratings/  
      /product/ratings/:id  

I find this kind of route to be ambiguous in a RESTful setting. Does 
the :id refer to the product or the rating? I would much rather see
routes that look like this:  

      /products/:id  
      /products/:id/ratings  
 
This is precisely what Zeus allows you to do.   

Benefits
--------

Coming soon...  

Using Zeus
----------

### Setting up Zeus

Add these lines to your application.ini files:  

#### Initialization

      autoloaderNamespaces[] = Zeus_  
      
      pluginpaths.Zeus_Application_Resource = "Zeus/Application/Resource"  
      pluginPaths.Zeus_Controller_Plugin = "Zeus/Controller/Plugin"  

#### Configuration

      resources.zeus[] =  

### RESTful Routes

There are two ways that you can create RESTful  

#### Using PHP

      $route = new Zeus_Rest_Route(  
          'products/:id/ratings',  
          array(  
              'module' => 'products',  
              'controller' => 'ratings',  
              'action' => 'index',  
              'id' => '',  
          )  
      );  
    
    
#### Using an .ini file 
 
      routes.productRatings.type = "Zeus_Rest_Route"  
      routes.productRatings.route = "products/:id/ratings"  
      routes.productRatings.defaults.module = "products"  
      routes.productRatings.defaults.controller = "ratings"  
      routes.productRatings.defaults.action = "index"  
    
### RESTful Controllers

Coming soon...  

### RESTful Views

Coming soon...  

