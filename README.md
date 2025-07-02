# The Batch++ standard v1.0.1
  
## 1. Setting a value to a variable  
  
```batch  
set var=value  
```  
  
## 2. Comments  
  
```batch  
# You can use a hash to comment, unlike in regular batch files  
# This is a comment  
```  
  
## 3. Macros  
  
```batch  
defmacro macro_name  
    echo Hello world!  
endmacro  
  
# You can also optionally have arguments.  
  
defmacro greet name  
    echo Hello %name%!  
endmacro  
```  
  
## 4. Calling a macro  
  
```batch  
callmacro macro_name  
```  
  
## 5. If statements  
  
```batch  
# The if statements are similar to regular Batch files.  
# The difference here is that you use the scope ends at the `endif` statement.  
if <condition>  
    # Do something  
else  
    # Do something else  
endif  
```  
  
## 6. While loops  
  
```batch  
while <condition>  
    # Do something  
endwhile  
```  
  
## 7. For loops  
  
```batch  
for <something>  
    # Do something  
endfor  
```  
  
## 8. Labels  
  
```batch  
# Labels are used to mark a position in the script.  
label label_name  
# You can jump to a label using the `goto` command.  
goto label_name  
# You can also call them using the `call` command.  
call label_name  
```

Anything not mentioned to be part of the language syntax that is part of Batch syntax is supported.
  
## Rules for implementing a Batch++ compiler  

1. Macros should compile to repeating code, not subroutines.
2. Writing regular Batch should be allowed. Do not throw an error on unrecognized commands, only on invalid syntax!
3. Batch++ should compile to regular Batch.
4. You should ONLY follow the standard. If your compiler implementation is incomplete or adds extra commands, you should specify in the associated documentation files that the user WILL see.

