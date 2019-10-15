````java

public class Student {
	private String no;
	private String name;
	public Student() {
		this("zhangsan","2018001");
	}
	
	public Student(String _name,String _no){
		no = _no;
		name = _name;
	}
	
	public String getNo(){
		return no;
	}
	public void setNo(String _no) {
		no = _no;
	}
//	public void setNo(Student this,String _no){	
//		this.no = _no;
//	}

	public String getName() {
		return name;
	}
	public void setName(String _name) {
		name = _name;
	}
	
	
	
	//用于两个类型相同的赋值
	public void set(Student as) {
		this.no = as.no;
		// this.setNo(as.no);//this可省
		//this.setNo(as.getNo());
		this.name = as.name;
		// this.setName(as.name);		
	}
}	
````
### student
````java

public class Student {
	private String no;
	private String name;
	/*无参构造方法*/
	public Student() {
		this("zhangsan","2018001");
	}
	/*有参构造方法*/
	public Student(String _name,String _no){
		no = _no;
		name = _name;
	}
	public void print() {
		System.out.println(no);
		System.out.println(name);
	}
	public String getNo(){
		return no;
	}
	public void setNo(String _no) {
		no = _no;
	}
	public String getName() {
		return name;
	}
	public void setName(String _name) {
		name = _name;
	}
	

}	
	

````
### CollegeStudent
````java

public class CollegeStudent extends Student {
	private String major;
	
	public CollegeStudent() {
		/*继承自积累的*/
		super("lisi","2018002");//手工调用只能放在第一行
		/*新增的*/
		major = "Math";
	}
		/*方法的重写*/
	public void print() {
		super.print();
		System.out.println(major);
	}
	public void set(String _major,String _name,String _no) {
		major = _major;
		setName( _name );
		setNo(_no);  //no = _no;
	}
	public void setMajor(String _major) {
		major = _major;
	}
	public String getMajor() {
		return major;
	}
	
}
````
### test
````java


public class Test1 {
	public static void main(String[] args) {
//		Student s1 = new Student();	
//		s1 = new Student();
//		System.out.println(s1.getName());
//		Student s2 = new Student("lizh","002");
//		System.out.println(s2.getName());
		
//		CollegeStudent c1 = new CollegeStudent();
//		System.out.println(c1.getName());
//		c1.setName("haha");
//		System.out.println(c1.getName());
//		c1.setMajor("Math");
//		System.out.println(c1.getMajor());

		Student s1 = new Student();
		CollegeStudent c1 = new CollegeStudent();
		s1.print();
		c1.print();
	}
	
	
}

````
