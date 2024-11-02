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
 
<h2>Connecting Service with Angular</h2><br>
we want to call the service within our application.<br>
so we need to create backendservice/backendapi/dataservice in angular.<br>
cmd: ng generate service service/data/welcomeData<br>
create a method in service<br>
declare it in constructor of our required page<br>
call it in the button clcik function <br>

If we call an HttpService, it may take a long time to execute. some service takes 3 to 5 seconds to execute.if we do it synchronously,we call the service and wait for response.The entire browser will hang. so we call all the http services asynchronously.observable is one of the approach for asynchronous communication. angular use extensive use of observables as the interface most of the asynchronolous operations. if we want to use of ajax request using http module angular in tern use of this observables( it is declarative).<br>
So we use Subscribe() - we can call the same service again and again.<br><br>
http request we sent, it return the observable.so when we subscribe it execute the http  request and return backs the response<br>
when we get the response from the subscribe call the success method is called.<br>

<h2>Managing Todos From Backend- Getting Data From Backend And Invoke From Frontend</h2><br>
Retreive all Tasks for a user -GET   /users/{username}/todos   ( methods and resources associated with each operations) <br>
Delete a Task of a user-DELETE  /users/{username}/todos/{todo_id} <br>
Edit a Task - PUT   /users/{username}/todos/{todo_id} <br>
Create a new Task - POST  /users/{username}/todos<br>

<h2>Retrieve All Tasks</h2><br>
<h3>Backend</h3><br>
create a seperate package for tasks<br>
Create the getters setters,constructor in another file<br>
create a service. And write the static data to it and it act as database. Also the function returning these data.<br>
Then call this service and aslo set the path  in main class.<br>
<h3>Frontend</h3><br>
create the service and write the function for returnig the url.<br>
call the retreive function in listaskcomponent<br>
<h2>delete a Todo</h2><br>
Restlet Client :Rest API Testing - RestAPI Client called Restlet .<br>
Then give the delete method and url and then click on send button. now the task is deleted<br>
<h3>Each time the application is restart the data is refreshed again and show the tasks again</h3><br>
<h3>Delete From UI</h3><br>
<h2>Update, it goes to another page and show the details to update</h2><br>
<h2>Create A Task</h2><br>
<h2>Security of Application</h2><br>
if somebody knows the url they can easily get the data . we are not using any login or creditionals to get the data. so it is not secure.<br>
So if we use username adn password also along with , its also not secure. Therefore we need temporoary token named jwt (jason web token).<br>



























