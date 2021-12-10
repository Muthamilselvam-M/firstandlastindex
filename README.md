# firstandlastindex



import java.util.Arrays;
public class Main
{
	public static void main(String[] args) {
		//System.out.println("Hello World");
		int[] arr = {1,2,3,3,3,3,4,4,4};
		int target = 4;
		System.out.println(Arrays.toString(meth(arr,target)));
	}
	public static int[] meth(int [] arr,int target){
	    int[] ans = {-1,-1};
	    ans[0] = binSea(arr,target,true);
	    ans[1] = binSea(arr,target,false);
	    return ans;
	}
	public static int binSea(int[] arr,int target,boolean isFirstIndex){
	    int ans = -1;
	    int start = 0;
	    int end = arr.length-1;
	    while(start<=end){
	        int mid = start + (end - start)/2;
	        if (target>arr[mid]){
	            start = mid + 1;
	        } 
	        else if(target<arr[mid]){
	            end = mid -1;
	        }
	        else{
	            ans = mid;
	            if(isFirstIndex){
	                end = mid -1;
	            }
	            else{
	                start = mid + 1;
	            }
	        }
	        
	    }
	    return ans;
	    
	}
}
