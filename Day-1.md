Seting Up
- Create a new project > del module-info.java from src > create a new class with package name as anything like org.first and class as anything like first
- You can use ctrl+i to indent

Taking input and output program
---------------------------------------------------------------------------------------------------------------------------
package org.javatraining;
import java.lang.*;
import java.util.*;

public class First {
	public static void main(String[] args) {
		Scanner ob = new Scanner(System.in); // taking input where scanner is a class from util package
		System.out.println("Enter 2 Nums : ");
		int a=ob.nextInt(), b = ob.nextInt(), c = a+b; // you can use nextFloat also
		System.out.println("The sum is : " + c);
		
	}
}
-------------------------------------------------------------------------------------------------------------------------------

Find sum and avg
----------------------------------------------------
package org.javatraining;
import java.lang.*;
import java.util.*;

public class First {
	public static void main(String[] args) {
		Scanner ob = new Scanner(System.in);
		int[] nums = new int[5];
		int sum=0;
		float avg=0;
		for(int i=0;i<5;i++) {
			nums[i]=ob.nextInt();
			sum+=nums[i];
		}
		System.out.println("The sum is : " + sum);
		avg = sum/5;
		System.out.println("the Average is : "+avg);
		
	}
}
---------------------------------------------------------------

Program for Oops
--------------------------------------
package org.javatraining;
import java.util.*;
public class Oops {
	int rollno;
	String name,address;
	
	void input() {
		Scanner ob = new Scanner(System.in);
		System.out.println("Enter rollno, name, address");
		rollno = ob.nextInt();
		name = ob.next();
		address = ob.next();
	}
	void display() {
		System.out.println("the roll no is "+rollno);
		System.out.println("the name is "+name);
		System.out.println("the address is "+address);
	}
	
	public static void main(String[] args) {
		Oops obj = new Oops();
		obj.input();
		obj.display();
	}
}
---------------------------------------------------------

#Inheritence Single
-------------------------------------------------------------------------------------
package org.javatraining;
import java.util.*;
class studentClass {
	int rollno;
	String name,address;
	public studentClass(int rollno, String name, String address) {
		super();
		this.rollno = rollno;
		this.name = name;
		this.address = address;
	}
	
	void display() {
		System.out.println("The roll no is "+rollno+"\tThe name is"+name+"\tThe address is "+address);
	}
}

public class inheritence extends studentClass{
	int phy,chem,total,avg;

	public inheritence(int rollno, String name, String address, int phy, int chem) {
		super(rollno, name, address); // Parent class constructor always works first
		this.phy = phy;
		this.chem = chem;
		this.total = phy+chem;
		this.avg = this.total/2;
	}
	void display() {
		super.display();// accessing display of parent class
		System.out.println("The phy : "+phy+"\t The chem "+chem+"\t The Total "+total+"\t The avg"+avg);
	}
	public static void main(String[] args) {
		inheritence ob=new inheritence(11,"Mayank","Patiala",40,50);
		ob.display();
	}
	
}
--------------------------------------------------------------------------------------------------------------------
# Multiple Inheritence
package org.javatraining;
import java.util.*;

class person{
	int id;
	String name;
	
	public person(int id, String name) {
		this.id = id;
		this.name = name;
	}
	
	public void display() {
		System.out.println("The Id is "+id);
		System.out.println("The name is "+name);
	}
}

class teacher extends person{
	String subject,section;
	
	public teacher(int id,String name,String subject,String section) {
		super(id,name);
		this.subject = subject;
		this.section = section;
	}
	
	public void display() {
		super.display();
		System.out.println("The Subject is "+ subject);
		System.out.println("The section is "+ section);
	}
}
public class multiLevelInheritence extends teacher {
	String school;

	public multiLevelInheritence(int id, String name, String subject, String section, String school) {
		super(id, name, subject, section);
		this.school = school;
	}
	
	public void display() {
		super.display();
		System.out.println("The School is "+school);
	}
	
	public static void main(String args[]) {
		multiLevelInheritence ob = new multiLevelInheritence(11,"Mayank","Java","13","TIET");
		ob.display();
	}
}
-------------------------------------------------------------------------------------------------------
# Heirarchial Inheritence
package org.javatraining;
import java.util.*;

class emp{
	int id,Salary;
	String name;
	public emp(int id,String name,int  Salary) {
		this.id=id;
		this.name=name;
	}
	
	public void display() {
		System.out.println("The id is " + id);
		System.out.println("The Name is "+name);
	}
}

class Trainee extends  emp{
	String skills;

	public Trainee(int id, String name, int Salary, String skills) {
		super(id, name, Salary);
		this.skills = skills;
	}
	
	public void display() {
		super.display();
		System.out.println("The Skills of Trainee are "+skills);
	}
}

class Trainer extends emp{
	int exp;
	
	public Trainer(int id,String name,int Salary,int exp) {
		super(id,name,Salary);
		this.exp = exp;
	}
	public void display() {
		super.display();
		System.out.println("The exp of the Trainer is "+exp);
	}
}

public class heirarchialInheri {
	public static void main(String args[]) {
		Trainee t = new Trainee(11,"Mayank",15,"MERN");
		t.display();
		
		Trainer t1 = new Trainer(101,"Sandip",50,20);
		t1.display();
	}
}
-------------------------------------------------------------------------------------------------------
