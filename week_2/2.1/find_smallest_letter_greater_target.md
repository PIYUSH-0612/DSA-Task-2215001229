```py
class Solution(object):
    def nextGreatestLetter(self, letters, target):
        """
        :type letters: List[str]
        :type target: str
        :rtype: str
        """
        ls=[]
    
        for i in range(0,len(letters)):
            if(ord(target)<ord(letters[i])):
                ls.append(letters[i])
        ls.sort()

        if(len(ls)>=1):
            return ls[0]
        else:
           return letters[0]
```