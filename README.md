# Majority Element

### Implementation 1 :

```java
public int majorityElement(int[] nums) {
        if(nums == null || nums.length == 0)
            return -1;
        
        Map<Integer,Integer> map = new HashMap<>();
        for(int i : nums){
            if(map.containsKey(i)){
                map.put(i, map.get(i) + 1);
            } else{
                map.put(i, 1); 
            }
        }
        
        int majority = (int) Math.floor(nums.length / 2);
        for(Integer n : map.keySet()){
            if(map.get(n) > majority){
                return n;
            }
        }
        return -1;
}
```

### Implementation 2 :

```java
public int majorityElement(int[] nums) {
       if(nums == null || nums.length == 0)
            return -1;
            
       Arrays.sort(nums);
       return nums[nums.length / 2]; 
}
```

### Implementation 3 :

```java
public int majorityElement(int[] nums) {
       if(nums == null || nums.length == 0)
            return -1;
        
       int result = 0, count = 0;
       for(int i = 0; i < nums.length; i++ ) {
          if(count == 0){
             result = nums[ i ];
             count = 1;
         } else if(result == nums[i]){
           count++;
         } else {
           count--;
         }
       }
 
     return result;
}
```
