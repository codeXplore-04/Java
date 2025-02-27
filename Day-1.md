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

#Inheritence
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
