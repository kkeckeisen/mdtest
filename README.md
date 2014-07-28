# luafile
Module to process lua files for generating documentation
## Functions
### LuaFile:append(lines)
#### Parameters
name | type | description
--- | --- | ---
lines | string &#124; array &#124; number | the line (or array of lines) to append

### LuaFile:check_for_tag(line, func_doc_tags, index, something, options, ploptions)
Test description
#### Parameters
name | type | description
--- | --- | ---
line | string | line
func_doc_tags | table | func doc tags
index | number | index
something | table | this shouldn't exPLODE
options | table | Table of options [*[sea, bee, z](#options)*]
ploptions | table | Table of ploptions [*[one, eight, three](#options)*]
##### options
name | type | description
--- | --- | ---
sea | string | third param
bee | number | second param
z | string | first param
##### ploptions
name | type | description
--- | --- | ---
one | string | first
three | number | second
eight | string | third
#### Usage
```lua
local DNC = require 'dnc'
local inspect = require 'inspect'
local _print = print

function print(f)
    _print(inspect(f))
end

local loginId = "xxxx"
local accountId = "XXXX"
local projectId = "xxxx"

local dnc = DNC(loginId, accountId, projectId)
local numbers = {'4445551212', '4445551213'} -- Can either be array-like table or single string
print(dnc:scrub(numbers))
print(dnc:block(numbers))
print(dnc:status(numbers))
print(dnc:unblock(numbers))
print(dnc:status(numbers))
```
### LuaFile:initialize(path)
#### Parameters
name | type | description
--- | --- | ---
path | string | the path of the lua file

### LuaFile:line_has_param_type(str)
#### Parameters
name | type | description
--- | --- | ---
str | string |

### LuaFile:process()
The process function is called from the FileList class (filelist.lua) and is responsible for building a table of all the docs for that file.
#### Parameters
name | type | description
--- | --- | ---


### get_file_name(path)
#### Parameters
name | type | description
--- | --- | ---
path | string | the full path of the file

### process_function_tag(self, tag, doc)
Gets the function name and removes 'lines' from the @function tag key
#### Parameters
name | type | description
--- | --- | ---
self | table | the instance of a LuaFile
tag | string | the tag that is being processed (e.g. @details)
doc | table | the whole doc (json obj)

### process_params_tag(self, tag, doc)
Tried to logically break down the parsing of the @params section into digestible bits. Stepping through the lines of this part of the doc a few times helps make things more maintainable.
#### Parameters
name | type | description
--- | --- | ---
self | table | the instance of a LuaFile
tag | string | the tag that is being processed (e.g. @details)
doc | table | the whole doc (json obj)

### process_tag(self, tag, doc)
#### Parameters
name | type | description
--- | --- | ---
self | table | the instance of a LuaFile
tag | string | the tag that is being processed (e.g. @details)
doc | table | the whole doc (json obj)

