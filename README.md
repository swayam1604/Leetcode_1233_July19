# LeetCode POTD – 1233. Remove Sub-Folders from the Filesystem (19 July 2025)

### 🔹 Problem Statement:
Given a list of folder paths, remove all sub-folders so that only top-level folders remain. A sub-folder starts with the parent folder path followed by a `/`.

### 🔹 Solution Approach:
- Sort the folder paths lexicographically.
- Iterate through and keep only those that are **not** subfolders of the last added folder.
- Efficient and works in O(n log n) due to sorting.

### 🔹 Python Code:

```python
class Solution:
    def removeSubfolders(self, folder):
        folder.sort()  # Sort the folder list lexicographically
        res = []
        
        for path in folder:
            # If res is empty or path is NOT a subfolder of last added folder
            if not res or not path.startswith(res[-1] + "/"):
                res.append(path)
        
        return res
```

Submitted by:
Swayam Sharma
