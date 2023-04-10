- can run without an else
```c
if ( logical expression = True){
	function
}
```

```c
if ( logical expression = True){
	function
}
else{
	different function
}
```

```c
if ( logical expression = True){
	function
}
else if( logical expression2 = True){
	function2
}
else if( logical expression3 = True){
	function3
}
else{
	function4
}
```

## Switch
- alternative to many if else
- often found in menus
```c
switch(k){
	case 3:
		printf("k=3");
		break;
	case 4:
		printf("k=4");
		break;
	case 5:
		printf("k=5");
		break;
}
```