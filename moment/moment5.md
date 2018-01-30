[Back](../index.md)

I've finally gotten fed up with php, so here's some Lua.

```lua
local file = io.open("test.txt", "w+")

-- This is for compatability, Lua 5.3 uses table.unpack, earlier versions use unpack
local unpack = unpack or table.unpack
-- Set the seed, different every second
math.randomseed(os.time())

function math.average(...)
	local total = 0
	for i = 1, select("#", ...) do
		assert(type(select(i, ...) == "number"))

		total = total + select(i, ...)
	end

	return total / select("#", ...)
end

local numbers = {}

for i = 1, math.random(5, 20) do
	local random = math.random(0, 25)
	table.insert(numbers, random)
	file:write(random .. "\n")
end

file:close()

-- It was really unclear what I was supposed to write to the file.
-- The example showed only the numbers written, but it said to
-- write "the answers"

print("Elements: ", unpack(numbers))
print("Number of elements: " .. #numbers)
print("Average: ", math.average(unpack(numbers)))
print("Minimum: ", math.min(unpack(numbers)))
print("Maximum: ", math.max(unpack(numbers)))
```
