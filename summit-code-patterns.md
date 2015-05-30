# Summit Code Patterns

## Error Handling: User Input
Summit application should include logic to account for users inputing incorrect values, which can include non numeric values such as `*` or `#` from their touch tone keys. Additionally, review the API documentation for functions such as `channel.gather` to ensure that you're properly using the available options to limit  users on what information they can enter.

Additionally, in general you will want to inform the user of their wrong doing by providing them with a message or indication that lets them konw that their actions are not permitting them to proceed as intended through your applciation

Here's an example of a `channel.gather` which limits a users reponse to a single digit or either 1, 2 _or_ three:

`channel.gather({maxDigit = 1, minDigit = 1, regex=[1,2,3]})`


## Error Handling: Web Service Calls
Web service calls are API calls that include the public internet. In most instances, the web services will provide a successful repsonse for your application. However, in those cases where the web service returns an invalid reponse or an error, your applicaiton should check for these and handle them properly for the caller.

### Example:

```
-- import http library
local http = require 'summit.http'

-- execucute web service call (post)
local res, err = http.post(url, options)

-- check if an error was returned
if err then
	print("http.post error: " .. err)
-- if res has a value (it's not nil) then we got a return
elseif res
	print("success: the result is:" .. res)
-- if no err was returned and res ~= true, then something bad happened
else
	print("http.post error: no error returned and res == nil")
end
```

## Error Handling: Datasore
Datastore is the no-SQL database provided with any Summit Account. When applications use Datastore to gather dat, they shoudl ensure that the table exists, the key exists and the value is the one expected for the specific application's needs. If either the table, key or value are not existent or incorrect then the application should include logic that prevents the application from breaking. The applicaiton shoudl etierh include a default option if the data is absent or incorrect. Or, the application should exit gracefully and log information 

### Handling Tables Example:

```
-- import datastore library
local datastore = require 'summit.datastore'

-- get a datastore table
local my_table, err = datastore.get_table("my_table", "map")

-- check if an error was returned
if err then
	print("datastore error: " .. err)
-- if res has a value (it's not nil) then we got a return
elseif my_table
	print("success- the result is:" .. res)
-- if no err was returned and res ~= true, then something bad happened
else
	print("datastore error: no error returned and res == nil")
end
```

### Handling Get Row Example:
```
--[[
	This block of code assumes you've successfully returned a table from
	Datastore that's of type "Map".
]]--

-- get the key_name
local key_name, err = my_table:get_row_by_key('key_name')

-- check if an err was returned	
if err then
	print("datastore error - get row: " .. err)
-- if values exists (it's not nil) then we got a return
elseif key_name then
	print("success - the row is: ".. key_name)
		--[[
			Here you would check the key/value pair that's returned
			and make sure the key and/or value are what you need for your
			specific app.
		]]--
else
	-- no err was returned and value ~= true, so something bad happened
	print("datastore error - get row: no error returned and res == nil")
end	
```

