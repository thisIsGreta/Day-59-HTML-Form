# Blog Project
To build a personal blog using Html Form, Python, Flask, Request and Jinja.

# What I learned:
1) Sending over arguments from Python file to HTML file. In the HTML file, the variable shall be wrapped with {{ }}
2) Writing multi-lines expressions in the HTML file using {% %} and {% endfor %}. See Flask--> quickstart--> routing
3) Navigating to another individual HTML file from index.html file by using: href = "{{ url_for( 'function_name_without_parentheses', input=variable) }}"

# Updates from Day 59
4) {% include "header.html" %}
   {% include "footer.html" %}
5) url building concerning inline style: style="background-image: **url(url_for('static', filename='assets/img/post-bg.jpg'))**"

# Updates from Day 60 - Handle POST Request with Flask
6) 在HTML文件的Form中加入action和method。 E.g. form action="{{ url_for('function') }}" method="post" ... /form
7) To catch the Post request in the server, we first need to give each input in the form a name attribute. 
   E.g. html: input name="username"
        server: name_data = request.form['username']
8) Then create a decorator in the main.py that will trigger a method wehn it receives a POST request. Note that the methods is a list and its name is in plural form. E.g. @app.route('/contact', method**s**=['POST', 'GET'])


# Updates from Day 64 - Regarding Flask Request. Get Hold of the Parameter of a URL
9) in the anchor tag: href="{{url_for('delete', id=movie.id)}}" creates a url http://localhost/delete?id={movie.id}. That is to say, the second argument in the url_for(args) puts in a paramater while the first argument creates an endpoint.
10) After Step 9), when we get back to the server, how do we get hold of the 'id' paramater? Use movie_id = request.args.get('id'), i.e. get the name of the paramater. Then search by id in the database. Note: request.args only ever contains values included in the request query string, the optional part of a URL after the ? question mark. Since it’s part of the URL, it is independent from the POST request body.
