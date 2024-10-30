```java
class Solution {
    public String frequencySort(String s) {
        
        HashMap<Character, Integer> mp = new HashMap<>();
        for (char c : s.toCharArray()) {
            mp.put(c, mp.getOrDefault(c, 0) + 1);
        }
        Map<Character, Integer> sortedMap = sortByValueDescending(mp);
        StringBuilder sb = new StringBuilder();
        for (Map.Entry<Character, Integer> entry : sortedMap.entrySet()) {
            char ch = entry.getKey();
            int frequency = entry.getValue();
            sb.append(String.valueOf(ch).repeat(frequency)); 
        }
        
        return sb.toString();
    }

    public static <K, V extends Comparable<? super V>> Map<K, V> sortByValueDescending(Map<K, V> map) {
        return map.entrySet()
                  .stream()
                  .sorted(Map.Entry.<K, V>comparingByValue().reversed())
                  .collect(Collectors.toMap(
                      Map.Entry::getKey, 
                      Map.Entry::getValue, 
                      (e1, e2) -> e1, 
                      LinkedHashMap::new
                  ));
    }
}

```