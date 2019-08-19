```c++
class Solution {
public:
    int strStr(string haystack, string needle) {
        if(needle.length()==0){
            return 0;
        }
        if(needle.length()>haystack.length()){
            return -1;
        }
        if(needle.length()==haystack.length()){
            int i;
            for(i=0;i<needle.length();i++){
                if(needle[i]!=haystack[i]){
                    break;
                }
            }
            return i==needle.length()?0:-1;
        }
        int i=0,j=0,k=0;
        for(i=0;i<haystack.length();i++){
            while(haystack[i+j]==needle[j]&&j<needle.length()){
                j++;
            }
            if(j==needle.length()){
                return i;
            }
            j=0;
        }
        return -1;
    }
};
```
