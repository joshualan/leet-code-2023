**Problem**

https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/777/


**Solution**

```
/**
 Do not return anything, modify matrix in-place instead.
 */
function setZeroes(matrix: number[][]): void {
    // find all the 0's first
    
    if (!matrix.length) {
        return;
    }
    
    const height = matrix.length;
    const width = matrix[0].length;
    let zeroRowHeader = false;
    let zeroColumnHeader = false;

    // mark the first number of every row and 
    // column to be zero'd out as undefined
    for (let i = 0; i < height; i++) {
        for (let j = 0; j < width; j++) {
            if (matrix[i][j] === 0) {
                matrix[i][0] = 0;
                matrix[0][j] = 0;
                
                if (i === 0) {
                    zeroColumnHeader = true;      
                }
                
                if (j === 0) {
                    zeroRowHeader = true;    
                }
            }
        }
    }

    // mark cell as 0 if the column or row header is undefined
    for (let i = height - 1; i > 0; i--) {
        for (let j = width - 1; j > 0; j--) {
            if (matrix[i][0] === 0 || matrix[0][j] === 0) {
                matrix[i][j] = 0;
            }
        }
    }

    if (zeroRowHeader) {
        for (let i = 0; i < height; i++) {
            matrix[i][0] = 0;
        }
    }

    if (zeroColumnHeader) {
        for (let j = 0; j < width; j++) {
            matrix[0][j] = 0;
        }
    }
};
```
