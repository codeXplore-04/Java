```
package jdbcdemo;
import java.sql.*;  // addthis and than add throwsexception in main method

public class Learning {
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

		Statement st = con.createStatement();
		//st.execute("create table firsttable(empno int,name varchar(30),address varchar(30))");
		st.execute("insert into firsttable values(1,'mayank','pune')");
		ResultSet rs = st.executeQuery("select * from firsttable");
		System.out.println(rs);
		while(rs.next()) {
			System.out.println(rs.getInt(1) + rs.getString(2) + rs.getString(3));
		}
	}
}

```
