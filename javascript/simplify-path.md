**Problem**

https://leetcode.com/problems/simplify-path/


**Solution**

```
function simplifyPath(path: string): string {
    const splitPaths = path.split('/');
    let canonicalPath = [];

    for (path of splitPaths) {
        if (path === '' || path === '.') {
            continue;
        }
        else if (path === '..') {
            canonicalPath.pop();
        }
        else {
            canonicalPath.push(path);
        }
    }    

    return `/${canonicalPath.join('/')}`;
};
```

**Results**

![Result](https://cdn.discordapp.com/attachments/290341065246900235/1095785029642231919/image.png "Result")