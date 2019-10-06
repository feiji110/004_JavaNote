			

		读contains()、equals()、startsWith()、endsWith()的源码    

		阅读String类的源码，分析String类中equals方法和indexOf方法的具体实现流程，并谈谈自己的理解。
		
		public boolean equals(Object anObject) {}
     
		static int indexOf(char[] source, int sourceOffset,
				int sourceCount, char[] target, int targetOffset,
				int targetCount, int fromIndex){}
		
```java
		   public boolean equals(Object anObject) {
		        if (this == anObject) {
		            return true;//==两边为引用数据类型：比较地址是否相等（若地址一样返回true）
		        }
		        if (anObject instanceof String) {//是否为String类的对象
		            String anotherString = (String)anObject;
		            int n = value.length;//n为当前文本的长度，用于判断值是否相等的循环条件
		            if (n == anotherString.value.length) {//文本长度==模式长度，如果相等才有必要判断值是否相等。
		                char v1[] = value;
		                char v2[] = anotherString.value;
		                int i = 0;
		                while (n-- != 0) {//n--先取值后--
		                    if (v1[i] != v2[i])
		                        return false;
		                    i++;
		                }//比较值是否相等(地址不一样，类型和值一样，返回true)
		                return true;
		            }
		        }
		        return false;
		    }
```



```java
		       public int indexOf(String str) {
		           return indexOf(str, 0);//fromIndex = 0
		       }//返回调用下一个函数（两个参数）

		       public int indexOf(String str, int fromIndex) {
		           return indexOf(value, 0, value.length,
		                   str.value, 0, str.value.length, fromIndex);//文本值，0，文本长度，模式值，0，模式长度，起始索引
		       }//返回调用下一个函数（五个参数）

		       static int indexOf(char[] source, int sourceOffset, int sourceCount, String target, int fromIndex) {
		           return indexOf(source, sourceOffset, sourceCount,  target.value, 0, target.value.length,
		                          fromIndex);
		       }//返回调用下一个函数（七个参数）

		       static int indexOf(char[] source, int sourceOffset, int sourceCount,
		               char[] target, int targetOffset, int targetCount,
		               int fromIndex)
//source:文本，sourceOffset文本匹配结束位置,sourceCount:文本长度
//target:模式，targetOffset模式匹配结束位置，targetCount:模式长度
//fromIndex:开始匹配索引起始位置
                        {
		           if (fromIndex >= sourceCount) { // 开始匹配位置 >= 文本的总长度 
		               return (targetCount == 0 ? sourceCount : -1); 
		               // 如果模式长度等于0，直接返回文本总长度，否则返回-1 ，未匹配
		           }
		           if (fromIndex < 0) { // 开始匹配位置 < 0
		               fromIndex = 0;
		           }
		           if (targetCount == 0) { // 模式长度 == 0
		               return fromIndex; 
		           }

		           char first = target[targetOffset]; 
		           // first 为模式第一个字符
		           int max = sourceOffset + (sourceCount - targetCount); 
		           // max = 0 + （文本长度- 模式长度）
		           // 最终（最坏情况），模式第一个字符匹配的位置。
                   //用于条件判断

		           for (int i = sourceOffset + fromIndex; i <= max; i++) { 
		           // i = 开始匹配位置+0
		               /* Look for first character. */
		               if (source[i] != first) { // 找到第一个匹配的字符
		                   while (++i <= max && source[i] != first);
		               }

		               /* Found first character, now look at the rest of v2 */
		               // 到这里时，要么匹配到第一个字符（i <= max），要么没有匹配到( i > max )
		               if (i <= max) {
		                   int j = i + 1;  // j = 第一个匹配字符的下一个
		                   int end = j + targetCount - 1;  //  end = j + 模式长度 - 1

		                   // k  =  模式第二个字符 -> 最后， 
		                   // j  =  第一个匹配字符 -> 匹配完，或者匹配失败
		                   // end = 当前匹配的第一个字符 + 模式长度 - 1 (循坏条件)
		                   for (int k = targetOffset + 1; j < end && source[j]
		                           == target[k]; j++, k++);


		                   if (j == end) {
		                       // 匹配 成功，返回对应开始下标 即i-文本offset
		                       /* Found whole string. */
		                       return i - sourceOffset;
		                   }
		               }
		           }
		           return -1;
		       }

```

