# Task 1: Java REST API Example

This project implements a Java application providing a REST API with endpoints for searching, creating, and deleting "task" objects. Each "task" object contains the following properties:

- **name**: Task name (string)
- **id**: Task ID (string)
- **assignee**: Task assignee (string)
- **project**: Project name (string)
- **startTime**: Task start date/time (date)
- **special property**: Based on the candidate's name. For example, if the candidate name is Rajesh Singh, the property name will be "rajeshSinghProperty". The value of this property is generated programmatically and consists of 5 random characters from the string "RajeshSingh". In my case, it is SandhiyaProperty

Here's a sample task object encoded as JSON:

```
jsonCopy code{
  "name": "Pass Kaiburr assessment",
  "id": "123",
  "assignee": "John Smith",
  "project": "Kaiburr",
  "startTime": "2023-04-21 15:51:42.276Z",
  "SandhiyaProperty": "sndia"
}
```

### Endpoints

- **GET /tasks**: Returns all tasks if no parameters are passed. 
- **GET /tasks/{id}:** If a task ID is passed as a parameter, returns a single task or 404 if no such task exists.
- **POST /tasks**: Adds a new task. The task object is passed as a JSON-encoded message body.
- **DELETE /task/{id}**: Deletes a task by ID.
- **GET /tasks/{name}**: Finds tasks by name. Returns one or more tasks if the name contains the specified string. Returns 404 if nothing is found.
- **GET /tasks/assignee/{name}**: Finds the first 10 tasks by assignee, sorted by startTime. Returns one or more tasks found, but not more than 10. Returns 404 if nothing is found.

Tasks are stored in a MongoDB database.

**POST /tasks**: Adds a new task. The task object is passed as a JSON-encoded message body.

![image-20240313220056398](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220056398.png)	

Data created

![image-20240313220133285](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220133285.png)

Data in MongoDB

![image-20240313220310866](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220310866.png)

**GET /tasks**: Returns all tasks if no parameters are passed. 

Postman

![image-20240313220446787](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220446787.png)



**GET /tasks/{id}:**If a task ID is passed as a parameter, returns a single task or 404 if no such task exists.

![image-20240313220525684](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220525684.png)

Returns 404 error if no tasks found

![image-20240313220614399](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313220614399.png)

MongoDB

![image-20240313221130097](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313221130097.png)

**GET /tasks/{name}**: Finds tasks by name. Returns one or more tasks if the name contains the specified string. Returns 404 if nothing is found.

![image-20240313222248491](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313222248491.png)

Returns 404 if not found

![image-20240313222325474](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313222325474.png)

**GET /tasks/assignee/{name}**: Finds the first 10 tasks by assignee, sorted by startTime. Returns one or more tasks found, but not more than 10. Returns 404 if nothing is found.

![image-20240313223010004](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313223010004.png)

Returns 404 if no data

![image-20240313223210011](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313223210011.png)

**DELETE /task/{id}**: Deletes a task by ID.

![image-20240313223313718](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313223313718.png)

MongoDB data deleted

![image-20240313223511038](C:\Users\Angel\AppData\Roaming\Typora\typora-user-images\image-20240313223511038.png)