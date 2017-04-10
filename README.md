# Map的遍历
```java
public class MapIterator {



    public static void main(String[] args) {
        HashMap<String,Double> hashMap = new HashMap<>();
        hashMap.put("语文",80.0);
        hashMap.put("数学",90.2);
        hashMap.put("英语",78.2);


        /**
         * 1 通过键找值
         * 效率低  避免使用
          */
        for (String key:hashMap.keySet()){
              System.out.println("key= " + key + " and value= " + hashMap.get(key));
        }


        System.out.println();
        System.out.println();

        /**
         使用Iterator
         优点：遍历是调用iterator.remove可以删除entries
         缺点：在for-each遍历中尝试使用此方法，结果是不可预测的
         */
        Iterator it = hashMap.entrySet().iterator();
        while (it.hasNext()){
            Map.Entry entry = (Map.Entry) it.next();
            System.out.println("key= " + entry.getKey() + " and value= " + entry.getValue());
        }

        System.out.println();
        System.out.println();


        /**
         * 3 使用Map.entry
         * for-each循环在Java 5中引用
         * 如果遍历的是一个空的map，for-each循环将抛出NullPointException，因此在遍历前你总是应该检查空引用
         */
        for (Map.Entry entry :hashMap.entrySet()){
            System.out.println("key= " + entry.getKey() + " value= " + entry.getValue());
        }


        System.out.println();
        System.out.println();

        /**
         * key value的直接遍历
         *
         *
         */
        for (String string : hashMap.keySet()){
            System.out.println("key=" + string);
        }
        for (Double score : hashMap.values()){
            System.out.println("values=" + score);
        }

    }
}
```