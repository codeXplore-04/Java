1. Have to add a jar file       >> properties>java build path>libraries>classpath>add external jars
OR
2. Use maven repo


Template for JDBC

```

package jdbcdemo;
import java.sql.*;  // addthis and than add throwsexception in main method

public class Learning {
	static final String DB_URL = "jdbc:mysql://localhost:3306/learning";
	static final String USER = "root";
	static final String PASS = "Admin@123";

	public static void main(String[] args) throws Exception {
		Class.forName("com.mysql.cj.jdbc.Driver");  // Initialisation of jdbc COMMON CODE

		// Creating the Connection
		Connection con = DriverManager.getConnection(DB_URL,USER,PASS);
	}
}


```
