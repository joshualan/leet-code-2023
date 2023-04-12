**Problem**

https://leetcode.com/problems/check-if-object-instance-of-class/description/


**Solution**

```
function checkIfInstanceOf(obj: any, classFunction: any): boolean {
    if (obj === null || obj === undefined || typeof classFunction !== 'function') {
        return false;
    }

    return Object(obj) instanceof classFunction;
};

/**
 * checkIfInstanceOf(new Date(), Date); // true
 */
```

**Results**

![Result](https://cdn.discordapp.com/attachments/290341065246900235/1095822831805272144/image.png "Result")