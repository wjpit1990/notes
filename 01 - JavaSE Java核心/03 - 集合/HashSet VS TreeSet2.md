
HashSet 底层Hash表，若两个元素的hash值不同，则一定不是同一个元素，若hash值相同，则判断equals，若equals相同，则是同一个对象，若equals不同，则不是一个对象，

TreeSet 集合的特点是可以对其中的元素进行排序，一种情况是放进treeset中的元素必须具有比较性，集合的底层结构是二叉树，保证元素唯一性的方法是compareTo方法返回0.
另一种情况是元素没有比较性，但是集合有比较性，定义一个类，实现comparetor接口，实现一个比较器。
