<h2><img src="https://cdn4.iconfinder.com/data/icons/socialcones/508/Amazon-512.png" alt="amazon-icon" width="30" height="30"> 937. Reorder Data in Log Files</h2>

- `sort()` method to reorder data into the log files </p>
- `split()` method to split the data that I will reorder lexicographically by their contents
- `regex` as a parameter to split the data acording the specifications
- `localeCompare()` method to compare the splited strings and then reorder then by their numerator (-1, 1, 0)

```javascript
var reorderLogFiles = function(logs) {
    // As the phrases are inside a list called 'logs', we gonna build a customized 'sort' function
    return logs.sort((a, b) => {
        // Split the logs into identifier and content using Regex
        // Here we separate the first part of the phrase into 'contentA'
        let [idA, contentA] = a.split(/ (.+)/);
        // Here we separata the second part of the phrase into 'contentB'
        let [idB, contentB] = b.split(/ (.+)/);

        // Check if the content is a digit or not
        // Then we gonna check if the 'contentA' contains a digit and if it contains reordered it
        let isDigitA = /^\d/.test(contentA);
        let isDigitB = /^\d/.test(contentB);

        // Logic for sorting
        if (!isDigitA && !isDigitB) { // Both are letter logs
            // This JS function we analyze if the string should become first (-1), after (1) or they're the same
            let contentComparison = contentA.localeCompare(contentB);

            if (contentComparison === 0) { return idA.localeCompare(idB);}
            return contentComparison; // Sort by content
        } else if (!isDigitA) { // A is a letter log and B is a digit log
            return -1;
        } else if (!isDigitB) { // B is a letter log and A is a digit log
            return 1;
        } else { // Both are digit logs
            return 0; // Keep original order for digit logs
        }
    });   
};

console.log(reorderLogFiles);
```
