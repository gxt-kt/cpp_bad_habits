# cpp bad habits

>  Ref: [https://www.youtube.com/watch?v=i_wDa2AS_8w](https://www.youtube.com/watch?v=i_wDa2AS_8w)


## 1. Do not use `using namepsace std` on global scope

Do not use `using namepsace std` on global scope. Do not use it in header files.

You can use it in function scope like the demo. And the effect scope is only the function.

## 2. Use `'\n'` when use cout instead of `std::endl`

If you want to print a new line, use `std::endl` will refresh the buffer and take more time.

It's better using the `'\n'` and faster.

But maybe it won't refresh when you debug with `'\n'`.

## 3. Use for loop based of auto

When you do not need the index. Use for loop based of auto.

## 4. Use the already exist algorithm interface

If you want realize some algorithm. Call the existing algorithm interface first.

## 5. Use std::array to replace c style array

Use std::array to replace c style array

## 6. Don't abuse `reinterpret_cast` to change type

`reinterpret_cast` should used to change type to it's original type. All other using is UB.

The C stype convert type is the same.


## 7_8. The const can be cast away and const unorder_map cannot use `[]` to index

First you can use `const_cast` to cast the const away.

Second For const unorder_map, you need use `.at()` to index.

Use `[]` will create a defaule value and may change the map size when the index isn't exist.

Use `.at()` won't change the map size and will cast a exception when the index isn't exist.

So you cann't use `[]` to index when the map is const.


## 9_10. Don't fall const down if you sure you don't change the parameter

It's better use const if you know you don't change the paramter.

## 11. Use struct form is better than single value

Use the struct make your programs have better readability.

Such as you can use `const auto& [first,second]:map` to iterate map.

Then you can just use first and second instead of val.first and val.second.

