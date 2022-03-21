# Programa printF

## Prototype:
	int ft_printf(const char *, ...); 

### Has to handle flags: 
* cspdiuxX% 

### Flags:
* %c - Prints a single char
* %s - Prints a string
* %p - Prints void * in hexadecimal format
* %d - Prints an int in base 10
* %u - Prints an unsigned decimal (base 10 num)
* %x - Prints a num in hex (base 16) lowercase format
* %X - Prints a num in hex (base 16) uppercase format
* %% - Prints a % sign
### BONUS:
* Manage any combination of the following flags: ’-0.’ and the field minimum width under all conversions. 
* Manage all the following flags: ’# +’ (Yes, one of them is a space) 


## Dynamic args

### **va_list:** 
* holds info about the other 3 macros

### **Void va_start** ( va_list ap, last_arg )
  * the macro initializes ap variable to be used with the va_arg and va_end macros -> va_end is the last known fixed arg

### **Type va_arg** ( va_list ap, type )
* this macro retrieves the next argument in the parameter list of the function w type type

### **Void va_end** ( va_list ap )
* this macro allows a func w variable arguments which used the va_start macro to return, if va_end is not called before returning from the func, the result is undefined


## Structure of PrintF
* Main format parser
* Flag/modifier parser
* Conversion dispatcher
* each conversion

main > variadic func > initialize va_list and euqal to the start of the variables list > passes to main function to difer print and flags (%*) > finds %, the flag modifier saves it into data struct taken by conversion func and passes to each convert and prints

# Main formater:
* prints everything until %
* checks % > ALLSYMBOLS  (cspdiouxXfy.*0123456789hLljz)
  * if not break, error
* check the rest until \0
  * if checkes ALLSYMBOLS
* func parse 2 will save it into data struct
	
￼

[Main Source](https://medium.com/@zhang.yine/ft-printf-d95747b7aa5a)

[Other sources](ttps://velog.io/@pawer/Printf)