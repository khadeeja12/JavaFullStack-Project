# JavaFullStack-Project
Full Stack project using Angular, Springboot and Restful APIs

<p>Angular: Frontend</p><br>
<p><h3>Web Service : </h3>Software system designed to support interoperable machine-to-machine interaction over a network , Not Platform independent, should allow communication over network</p>

<h4>ApplicationA request to Webservice , webservice receive it and process it and return back to Application A as response <br></h4>
input-request and output-response to webservice<br>
request and response should be independent .Therefore Format for it is : XML , JSON <br>
Every Webservice offers Service definition : RRformat-is it json,xml or any other format ,Request structure: how can be the request by customer,Response structure:how can be the response by webservice,Endpoint: how to call service and where the service available<br><br>
Service Provider :WebService<br>
Service Consumer :Applications<br>
Service Definition : Contract between them.<br>
Transport: HTTP (over the web-url), MQ(communication over the queue-queue)<br>

<h3>REST- </h3><h4>Completely built on top of HTTP and assign URI to each resource</h4><br>
when we enter the url in browser , a request send to server and server gives back the response <br>
The format of this request and response is defined by HTTP(Hypertext transfer Protocol):- get request , http response containing html = browser look the response and takes the html and displays it on the screen<br>
HTTP:request- methods :get,post,put.., response- status codes :200,404...<br>
We using the HTTP to develop the Webservices as well<br>
<h4>RESOURCE: </h4>user, todos, specific todo.......<br>
it has an URI<br>

<h3>Spring Boot</h3><br>
START.SPRING.IO<BR>

<h4>Spring Boot starter projects : convenient dependency descriptors.Dependencies are Predefined.Variety of starter projects-web,mvc,...</h4>
<h4>Spring Boot Auto Configuration :Tomcat configurations, Error Configurations..</h4>
<h4>Spring Boot DevTools:increase developer productivity. It automatically reloads the changes to page.</h4>
<h4>Configuration Using profiles: for environments- dev, trace ,info ,prod,warning,error,off</h4>
<h4>Complex Configurations</h4><br>

<h1>Restful Api & SpringBoot as Backend</h1>
<h2>web,devtools,jpa,h2</h2>
<h2>Sample Hello World Restful Service</h2>
//Controller
@RestController // this handles rest request. so we tell to spring that this is rest controller.
public class HelloWorldController {

	//Get
	//URI - /hello-world   request
	//method-"Hello World" response
	
//	@RequestMapping(method = RequestMethod.GET,path="/hello-world")   map the get request to the uri <br>
	@GetMapping(path="/hello-world")<br>
	public String helloWorld() {<br>
		return "Hello World , Its me Kaija";<br>
	}	
}<br>

@GetMapping(path="/hello-world-bean")<br>
	public HelloWorldBean helloWorldBean() {<br>
		return new HelloWorldBean("Hello World");<br>
	}

<h3>Dispatcher Servlet</h3><br>
Request goes to dispatcher servelet. it knows all the mappings present in the application.so it mapped to specific method and controller.it executes and return backs the bean. And the dsipatcher servlet says to the jackson do the conversion to json and returns the response back.<br>

<h3>Path Variable</h3><br>
we are using path variable and giving the value and getting the response as this value<br>
http://localhost:8080/hello-world/path-variable/khadeeja<br>
@GetMapping(path="/hello-world/path-variable/{name}") // accept the path variable here <br>
	public HelloWorldBean helloWorldPathVariable(@PathVariable String name) {<br>
		return new HelloWorldBean(String.format("Hello World %s", name));<br>
	}
 

















