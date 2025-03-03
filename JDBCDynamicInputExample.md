```
package jdbcdemo;
import java.sql.*;
import java.util.*;


public class dynamicInput {
	static final String DB_URL = "jdbc:mysql://localhost:3306/learning";
	static final String USER = "root";
	static final String PASS = "Admin@123";
	public static void main(String[] args) throws Exception {
		Class.forName("com.mysql.cj.jdbc.Driver");  // Initialisation of jdbc COMMON CODE
		Connection con;
		try {
			// Creating the Connection
			con = DriverManager.getConnection(DB_URL,USER,PASS);
			System.out.println("Connection Success");
		}catch(Exception e) {
			throw new Exception("Database not Connected");
		}

		//st.execute("create table firsttable(empno int,name varchar(30),address varchar(30))");
		Scanner ob = new Scanner(System.in);
		int empno = ob.nextInt();
		String name = ob.next(),address=ob.next();
		
		PreparedStatement st = con.prepareStatement("insert into firsttable values(?,?,?)");
		st.setInt(1,empno);
		st.setString(2, name);
		st.setString(3, address);
		st.execute();		
		
		ResultSet rs = st.executeQuery("select * from firsttable");
		System.out.println(rs);
		while(rs.next()) {
			System.out.println(rs.getInt(1) + "--" + rs.getString(2) + "--" + rs.getString(3));
		}
	}
}
```
