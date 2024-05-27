# Simple Go Web Server

This Go application is a simple web server that handles static file serving and basic form processing. It includes endpoints for serving static files, handling form submissions, and a basic hello world endpoint.

## Features

- Serve static files from a directory.
- Handle POST requests with form data.   
- Handle GET requests to a simple hello endpoint.

## Requirements

- Go (version 1.16 or higher)

## Installation

1. Ensure you have Go installed. You can download it from [https://golang.org/dl/](https://golang.org/dl/).
2. Save this script to your local machine.

## Project Structure

- `main.go`: The main Go file containing the server code.
- `static/`: Directory for static files (e.g., HTML, CSS, JS).

## Usage

1. Create a directory named `static` in the same directory as the script and place your static files (e.g., HTML, CSS, JS) in it.
2. Save the script to a file, for example `main.go`.
3. Open a terminal and navigate to the directory containing `main.go`.
4. Run the program using the following command:

    ```sh
    go run main.go
    ```

5. The server will start and listen on port 3000.

## Endpoints

- `GET /`: Serves static files from the `static` directory.
- `GET /hello`: Returns a simple hello message.
- `POST /form`: Handles form submissions and echoes the submitted name and address.

## Example Form Submission

To test the form handling, create a simple HTML form in the `static` directory (e.g., `form.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form</title>
</head>
<body>
    <form action="/form" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name">
        <br>
        <label for="address">Address:</label>
        <input type="text" id="address" name="address">
        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```
## Accessing the Server
1. Open your browser and navigate to http://localhost:3000 to access the static files. 
2. Navigate to http://localhost:3000/hello to see the hello message.
3. Navigate to http://localhost:3000/form.html to see and submit the form.
## Code Explanation
`main`: The entry point of the program. Sets up HTTP handlers and starts the server. 

`formHandler`: Handles POST requests to the /form endpoint, parses form data, and responds with the submitted data.

`helloHandler`: Handles GET requests to the /hello endpoint, responds with a hello message.

`fileServer`: Serves static files from the static directory.
## Error Handling
1. If an error occurs while parsing the form, an error message will be displayed.
2. If a requested URL or method is not found or supported, a 404 error message will be returned.
