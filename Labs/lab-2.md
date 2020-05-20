# Lab 2 - Lets get RESTful :dancer: 

In this lab you are going to create a web app with some routes. To do this you will use the `net/http` library. You will then extend this to output a random joke by calling an open API without the need for authentication. The API in this lab is a random dad joke API but feel free to explore and chose another if you'd like, the principals are the same!

### Step 1

We will start by creating a route handler. Below your `main()` function in `main.go`, add the following snippet of code.

```golang
func handler(w http.ResponseWriter, r *http.Request) {
    // Assign a variable with a string
    name := "<your name here>"

    // Logs a message to the terminal using the 3rd party import logrus
    logr.Info("Received request for the home page")

    // Write the response to the byte array - Sprintf formats and returns a string without printing it anywhere
    w.Write([]byte(fmt.Sprintf("Hello, %s\n", name)))
}
```

> **Note**: You will also need to add the following import to your code (this makes the terminal logs look pretty). To do this, your imports should look like:

```golang
import (
    "fmt"
    "net/http"

    // You can prefix imports to make it easier to reference them in your code, like this one
    logr "github.com/sirupsen/logrus"
)
```

### Step 2

Now you have got a route handler, you need to create the web server to invoke it. To do this, use the code snippet below and insert it into your `main()` function. You will be using the standard `net/http` library and this demonstrates just how easy it is to spin one up in Golang!

```golang
// Create the first route handler listening on '/'
http.HandleFunc("/", handler)
logr.Info("Starting up on 8080")

// Start the sever
http.ListenAndServe(":8080", nil)
```

### Step 3

Head back to your terminal window and run your code using the command `go run cmd/main.go`. This will start up a server on port :8080.

> **Note**: You may be prompted by your system to allow a network connection (you need to allow this otherwise the application may not run corretly)

Open up a browser and type `localhost:8080` into the top URL bar and you should see the output from the `handler()` function on your screen.

### Step 4

The server is up and running but this is very basic. Use `control+c` in your terminal to terminate the server connection. Next, you will add in the route to call the random joke API without any authentication.

To do this, add the the code snippet below as a new function inside your `main.go` file.

```golang
func getJoke() (string, error) {
    logr.Infof("Getting joke from API..")

    req, err := http.NewRequest("GET", "https://icanhazdadjoke.com/", nil)

    // Check the request doesnt return an error
    if err != nil {
        return "", err
    }

    // Set the request header
    req.Header.Set("Accept", "text/plain")

    // Make the HTTP request - '.Do' sends an HTTP request and returns an HTTP response
    resp, err := http.DefaultClient.Do(req)

    // Check the request doesn't return an error
    if err != nil {
        return "", err
    }

    // Closes resp.Body at the end of the function (always do this to prevent memory leaks, even if it isn't used)
    defer resp.Body.Close()

    // Read resp.Body until EOF
    body, err := ioutil.ReadAll(resp.Body)

    // Check the ReadAll doesn't return an error
    if err != nil {
        return "", err
    }

    return string(body), nil
}
```

This will return a string of the body as you want to see the joke in plain text on the page and nil, since there is no error at this point. 

Now the API call function is in place, the next thing you need to do is add another route handler, just like you did in Step 1.

To do this, add the new function shown below and then invoke it in the `main()` function, just like you did with the previous handler.

```golang
func jokeHandler(w http.ResponseWriter, r *http.Request) {
    // Write the status code 200
    w.WriteHeader(http.StatusOK)

    // Logs a message to the terminal using the 3rd party import logrus
    logr.Infof("Received request to show a joke")

    // getJoke() will return 2 values so we must assign them with x, y
    dadJoke, err := getJoke()

    // Check the request doesnt return an error
    if err != nil {
        logr.Error(err)
    }

    // Write the response to the byte array - Sprintf formats and returns a string without printing it anywhere
    w.Write([]byte(fmt.Sprintf(dadJoke)))
    logr.Info(dadJoke)
}
```

```go
// Add this line below the existing "/" route
http.HandleFunc("/showjoke", jokeHandler)
```

If you run the code and navigate to `localhost:8080/showjoke` in your browser you should be presented with a randomly generated joke!

Now the jokes are flowing, lets get it up in the cloud. Continue to [Lab 3](./lab-3.md) to see how this is done.
