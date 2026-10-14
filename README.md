class Solution {
    public int numOfSubarrays(int[] arr, int k, int threshold) {
        int l = 0 ; int h = k -1 ;
        int avg = 0 ; 
        for(int i = l ; i <= h ; i++) avg += arr[i]; 

        avg =avg / k ; 

        int count = 0 ; 

        while(h < arr.length){
            int x = avg / k ;
            if(x>=threshold) count++;
            l++;
            h++;
          if(h < arr.length)    avg = avg - arr[l-1]/k + arr[h]/k; 
        }

  
    

        return count;
        
    }
}
