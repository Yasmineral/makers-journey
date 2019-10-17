* **Sinatra** is built on a technology called Rack. Rack provides Sinatra with a built-in variable, ENV. It's available anywhere in Sinatra. You will set up a basic web framework with Sinatra, that can receive and respond to HTTP requests and you will run from within your own computer. Use params to extract extra information from a client request. Allow users to interact with your app via forms. Sinatra::Base is the base class for all Sinatra applications.

* **erb** - provides an easy to use but powerful templating system for Ruby. Using ERB, actual Ruby code can be added to any plain text document for the purposes of generating document information details and/or flow control. erb within a Sinatra route enables lots of cool features e.g <%= %> interpolation 

* **Selenium** - by default, Capybara uses the :rack_test driver which is fast but limited: it does not support JavaScript, nor is it able to access HTTP resources outside of your Rack application, such as remote APIs and OAuth services. 

* **config.ru** - default configuration file for a rackup command with a list of instructions for Rack. Rack is an interface and architecture that provides a domain specific language (DSL) and connects an application with a world of web.

* **Capybara** - use to write and pass feature tests. Almost every Capybara feature test involves this process: 1. What does the user have to do? 2. What does the user expect to see? Note that we are using Capybara's feature and scenario syntax. These work just like ‘describe’ and ‘it’, and we can use them interchangeably. This is because Capybara-RSpec is simply a bunch of helpful methods on top of RSpec. Capybara itself is simply a way of driving devices, like browsers, in a programmatic way.

* **Post/redirect/get** - allows for the page shown to the user after a form submission to be reloaded, shared or bookmarked without certain ill effects such as submitting the form another time.

* **Rack** - standardised API. Any new app that you build, as long as its Rack compatible, works on any server and any server just needs to implement a Rack handler and it can run any Rack application. Rack provides a library to wrap HTTP requests in ruby objects. Rack is a library that provides a simplified interface between your ruby application and your server. Rack utilises polymorphism to pass a request through multiple layers of middleware.  
