prjson
======

Tiny utility for pretty printing JSON encoded data. 


How to install
--------------

Download the script and run it.


Usage
-----

	# Pretty-print a file
    prjson < file.json
    
	# Pretty-print the whole response from a web server
	curl 'https://ajax.googleapis.com/ajax/services/search/web?v=1.0&q=Google' | prjson
    
	# Pretty-print the value of "results" key
	curl 'https://ajax.googleapis.com/ajax/services/search/web?v=1.0&q=Google' | prjson responseData results
    
	# Print only the URL of the first result
	curl 'https://ajax.googleapis.com/ajax/services/search/web?v=1.0&q=Google' | prjson responseData results 0 url
    
	# Decoding a double-encoded JSON (unfortunately there are some weird APIs that use it)
	cat >>EOF > example.json
    {
        "key1": "{ \"another_key\": \"value\" }",
        "key2": true
    }
	EOF
	cat example.json | prjson key1 | prjson


Author
------

Dan Keder <dan.keder@gmail.com>
