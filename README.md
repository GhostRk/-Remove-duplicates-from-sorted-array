# -Remove-duplicates-from-sorted-array
leetcode problem
class Solution {
    public int removeDuplicates(int[] nums) {
        
        //for input array less than length 2
        if(nums.length<2)
        {
            return nums.length;
        }
        
        int start=0;
        int flag=0;        
    
             //initializing index for pointer i & j using start variable and checking array is repetative or not   using flag
        for(int i=0;i<nums.length-1;i++)
        {
            
            
            if(nums[i]==nums[i+1])
            {
                flag++;
                start=i+1;
                break;
            }
                
            
           
        }
        
        //if flag doest not change means no repeated elements in array
        
        if(flag==0)
        {
            return nums.length;//simply return length 
        }
   
        
        //if array have repeated elements then below
        int var=nums[start];
        int temp;
        int j=start;
        //i and j should start with first repeating element 
        for(int i=start;i<nums.length && j<nums.length;i++) 
        {
            //for swaping condition applied
            if(nums[j]!=nums[i] && nums[i]!=var)
            {
                temp=nums[j];
                nums[j]=nums[i];
                var=nums[i]; //var updated
                nums[i]=temp;
                j++;
            }
        }
        return j;
        
    
    }
}
