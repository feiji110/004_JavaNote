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
