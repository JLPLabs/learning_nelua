# learning nelua
Some basics that may be useful as you start to learn Nelua

## modules
Say you have a statistics library (in Nelua) and you want to create a namespace (similiar to how you would use a table in Lua).

*stats.nelua*
```
require('span')

global Stats = @record{}

-- max value in table of values
function Stats.max(t: span(number)): number
  local res: number = t[0]
  for i,v in ipairs(t) do
    if v > res then res = v end
  end
  return res
end
```

*main.nelua*
```
require('stats')    -- load 'Stats' namespace

local res: [10]number = {}
for j = 0, 9 do
  res[j] = my_experiment()
end
print("max result: ", Stats.max(&res))

```
more at: https://nelua.io/overview/#record-globals
