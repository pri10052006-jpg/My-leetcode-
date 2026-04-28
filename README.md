class Solution {
    public boolean isPalindrome(int x) {
        int r=0;
        int y=x;
        while(y>0){
            r=(r*10)+y%10;
            y/=10;
        }
        if(x==r)
            return true;
        else
            return false;
    }
}
