# LuaRegistry

Lua Library to work & fiddle with Windows Registry by using the `os.execute` function.

## Limitations

Because it uses OS commands, it requires double sequences, these are not integrated (working on it). However you can use block comments ``[[]]`` OR the backlash escape char `\\`.

## Examples
Get content of a full registry key.
```lua
-- require the library module
local LuaRegistry = require("lr")

-- get the Microsoft full key, containing it's sub-keys, values, etc
local Microsoft = LuaRegistry.getKey("HKEY_CURRENT_USER\\SOFTWARE\\Microsoft")

-- print what's in Microsoft key
for i, v in next, Microsoft do
    print(i, v)
end

-- print Microsoft's values
for i, v in next, Microsoft.values do
    print(i, v)
end

-- print what's in Microsoft subkeys
for i, v in next, Microsoft.keys do
    print(i, v)
end
```
Get a registry key value.
```lua
-- require the library module
local LuaRegistry = require("lr")

-- print cryptography's MachineGuid
print(LuaRegistry.getValue("HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Cryptography", "MachineGuid"))
```

## Documentation

Visit the [Wiki](https://github.com/opBandwidth/LuaRegistry/wiki) page for Documentation.

## Authors

- [@Tieske](https://github.com/Tieske) - https://github.com/Tieske/registry
- [@opBandwidth](https://github.com/opBandwidth) - Reworked the old code.

## License

MIT license

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
