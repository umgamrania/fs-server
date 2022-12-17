# fs-server
Modified Python http.server to make the user interface better and added functionality to upload files to server

Set the DEFAULT_FOLDER variable to be the path where you want to store the uploaded files, <br /> 
```DEFAULT_FOLDER = '/path/to/folder'```

and maybe change the PORT if you want to<br />
```PORT = (int)```

# What I've changed

### list_directory() in SimpleHTTPRequestHandler:
* The implimentation of getting data in the current directory is the same, I've just changed the HTML portion.

### Added do_POST method in BaseHTTPRequestHandler:
* When a file is uploaded, a POST request is made to the server, this function handles that POST request
* The file is uploaded using a ```<form>```, and that file is recieved inside this function and saved in the ```DEFAULT_FOLDER``` location with the same filename
* To receive the file, I've used the cgi library from python, which is depricated and will be removed in Python 3.13 and I haven't thought of any solution for that 😅
