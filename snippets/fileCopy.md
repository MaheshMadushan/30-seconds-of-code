---
title: fileCopy
tags: node,beginner
---

Returns the copy of source file to specified location

- Use `fs.readFile()` to asynchronously reads the entire contents of a file and returns buffer and converted into string using `UTF-8` encoding

- Use `fs.writeFile()` asynchronously writes data to the file, replacing the file if it already exists.

```js
const fs = require('fs');

const copyFile = (socurceFilePath, pathToCopy, newFileName) => {
    const filePath = pathToCopy +'/'+ newFileName
    fs.readFile(socurceFilePath, 'utf8', (err, data) => {
        if(err){
            console.log('error occured while reading file')
        }else{
            fs.writeFile(filePath,data,()=>{
                console.log('file is wriiten')
            })
        }
    })
}
```


```js
/*
file path - path/to/sourceFile.tex

sourceFile.txt content
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Odio tenetur quo animi dolorum itaque, aut corporis laborum a rerum tempora, at quia nostrum libero id sit, esse odit architecto error culpa explicabo facere minus? Inventore, nostrum blanditiis? Fuga praesentium porro sequi culpa molestiae, amet a natus labore exercitationem corporis optio.
 */
copyFile('path/to/sourceFile.text','path/to/copy','newFileName.text')

/*
new file path - path/to/copy/newFileName.text

newFileName.text content
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Odio tenetur quo animi dolorum itaque, aut corporis laborum a rerum tempora, at quia nostrum libero id sit, esse odit architecto error culpa explicabo facere minus? Inventore, nostrum blanditiis? Fuga praesentium porro sequi culpa molestiae, amet a natus labore exercitationem corporis optio.
 */
```