### 抽象类Animal
````java
public abstract class Animal {
	
	public abstract void shout();
}
````
### Comparable接口
````java
//定义一个接口，interface 取代 class位置
public interface Comparable {
	///默认全为抽象方法
	public int compareTo(Object other);
}
````
### Dog类
````java
//public class Dog extends Animal {
//
//	@Override
//	//派生类继承抽象类,必须实现（重写）抽象类的所有方法
//	public void shout() {
//		// TODO Auto-generated method stub
//		System.out.println("Dog shout!");	
//	}	
//}
public class Dog extends Animal implements Comparable {

	@Override
	//派生类继承抽象类,必须实现（重写）抽象类的所有方法
	public void shout() {
		// TODO Auto-generated method stub
		System.out.println("Dog shout!");	
	}
	@Override
	public int compareTo(Object other) {
		// TODO Auto-generated method stub
		return 0;
	}
	
}
````
### Test类
````java
public class Test1 {

	public static void main(String[] args) {
		/* abstract 修饰的抽象类不能初始化，不能实例化对象
		 * 上层基类产生对象不合理
		 * 抽象类种可以定义抽象方法。//最大不同
		 * 用来被继承的
		 * 基类中的抽象方法
		 * */
		//Animal a = new Animal();//Animal为抽象类
		Dog d = new Dog();
		d.shout();
		
		Animal a = new Dog();
		a.shout();
		//接口的引入
		
		
	}
````

