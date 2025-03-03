1. Have to add a jar file       >> properties>java build path>libraries>classpath>add external jars
OR
2. Use maven repo


Template for JDBC

```

package jdbcdemo;
import java.sql.*;  // addthis and than add throwsexception in main method

public class Learning {
	public static void main(String[] args) throws Exception {
		Class.forName("com.mysql.cj.jdbc.Driver");  // Initialisation of jdbc COMMON CODE
		
		// Creating the Connection
		Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/learning","root","Admin@123");
	}
}

```
