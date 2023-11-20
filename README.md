# RESTapi

## 1. API(**A**pplication **P**rogramming **I**nterface)
* We already have used API.
* For example, Using methods from other Java classes is also using APIs.
```
		public class Calculator {
			public int add(int a, int b) {
				return a + b;
			}
		}

		public class TestCalculator {

			private Calculator calculator;

			@Befor
			public void setUp() {
				calculator = new Calculator();
			}

			@Test
			public voic testAdd() {
				int a = 5;
				int b = 10;
				assertThat(calculator.add(a, b), is(5));
			}
		}
```
<br>


* Compare METHOD, CRUD, SQL

<table class="table table-bordered">
<thead>
<tr>
	<th>Method</th>
    <th>CRUD</th>
    <th>SQL</th>
</tr>
</thead>
<tbody>
<tr>
	<td>POST</td>
    <td>Create</td>
    <td>INSERT</td>
</tr>
<tr>
	<td>GET</td>
    <td>Read</td>
    <td>SELECT</td>
</tr>
<tr>
	<td>PUT</td>
    <td>Update</td>
    <td>UPDATE</td>
</tr>
<tr>
	<td>DELETE</td>
    <td>Delete</td>
    <td>DELETE</td>
</tr>
</tbody>
</table>

* REST API
  - Unlike SOAP, which is a service-oriented structure, REST is a resource-oriented architecture (ROA: 
    Resource Oriented Architecture) that recognizes all website content (text, images, video) and DB 
    content as one resource and provides unique information for each resource. A URI (Uniform Resource 
    Identifier) is assigned, and CRUD (Create, Read, Update, Delete) operations for the resource are 
    processed through HTTP's basic commands: POST, GET, PUT, and DELETE.
  - A Web API suitable for the REST structural style is called a REST API.
  - A web service that provides a ‘REST API’ can be called ‘RESTful’.

* REST API information provision method
  - XML
  - JSON
  - RSS
 
## URI(Uniform Resource Identifier) identifier design
 * The only thing an identifier can do is represent an object. Unless we are doing a dereference, we 
   should not look into the contents of the URI to obtain other information.
 *  When creating a URI, the REST API resource model must be able to be passed to the client model.

### 1) URI form
   * The slush delimiter (/) is used to indicate hierarchical relationships.
   * Do not include a slash (/) as the last character of the URI.
   * Hyphens (-) are used to improve URI readability.
   * Underscores (_) are not used in URIs.
   * Lowercase letters are appropriate for URI paths.
   * File extensions (ex: .json, .xml) are not included in the URI.

### 2) Resource modelling
  - The URI that is the basis of the web service becomes a resource of the REST API.

### 3) Resource Archetype
   * Document: Similar concept to object instance or database record
   * Collection: A resource called a directory managed by the server
   * Store: Resource store managed by the client

### 4) URI path design
   * A singular noun must be used as the document name.
   * Plural nouns must be used as collection names.
   * We must use plural nouns for name of storage.
   * Changed parts of the path are replaced with unique values.
   * Things that represent CRUD functions should not be used in URIs.

## 2. Request Method (GET/POST/PUT/DELETE)
 * GET: Used to obtain an expression of resource status
 * POST: Used when we create a new resource in the collection or execute a controller
 * PUT: Used when we add new resources to the storage or update existing resources
 * DELETE: Remove resource

## 3. Response status code
  * 1xx : Information exchange at transport protocol level
  * 2xx : Client request completed successfully
  * 3xx : Client must take additional action to complete request
  * 4xx : Invalid request from client
  * 5xx : Status code due to server-side error

## 4. REST Advantages/Disadvantages
  ### 1) Advantages
  + The existing web infrastructure can be used.
  + EASY

  ### 2) Disadvantages
  - Management is difficult due to lack of standards
