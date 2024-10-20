```
const unsigned char BP = 11;
const float MAX_DEPTH = 0xFFFF/(float)(1<<BP);
for(int i=0; i<height; i++) {
	for(int j=0; j<width; j++) {
		if(z<MAX_DEPTH) {
			*depth++ = round(z*(1<<BP));
		}
		else {
			*depth++ = 0xFFFF;
		}
	}
}
```

```
const unsigned char BP = 11;
float toFloat = 1.0/(float)(1<<BP);
for(int i=0; i<height; i++) {
	for(int j=0; j<width; j++) {
		*z++ = (*depth++)*toFloat;
	}
}
```