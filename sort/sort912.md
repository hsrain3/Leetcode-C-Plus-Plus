/*插入排序java*/
public int[] sortArray(int[] nums) {
        int n=nums.length;
         int tmp;
         int j=0;
         for(int i=1;i<n;i++)
         {
             tmp=nums[i];
             for(j=i;j>0&&nums[j-1]>tmp;j--)
             {
                 nums[j]=nums[j-1];
                // nums[j-1]=tmp;  
             }
             nums[j]=tmp;
         }
         return nums;
    }
    
    
    /*快速排序java*/
     public int[] sortArray(int[] nums) {
       
       return qsort(nums,0,nums.length-1);
    }
    
    int[] qsort(int[] nums,int left,int right)
    {
         if(left<right){
            int pivotpos=partition(nums,left,right);
            qsort(nums,left,pivotpos-1);
            qsort(nums,pivotpos+1,right);
        }
        return nums;
    }
    int partition(int[] nums,int low,int high)
    {
        int pivotpos=low;
        int pivot=nums[low];
        for(int i=low+1;i<=high;i++)
        {
            if(nums[i]<pivot)
            {
                pivotpos++;
                if(pivotpos!=i){
                    
                    int tmp=nums[pivotpos];
                    nums[pivotpos]=nums[i];
                    nums[i]=tmp; //交换

                }

            }
        }
        nums[low]=nums[pivotpos];
        nums[pivotpos]=pivot;
        return pivotpos;
    }
/*C++都超时了。。。。。*/
