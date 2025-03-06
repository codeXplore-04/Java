<%@page import = "java.sql.*" %>
<%
String a = request.getParameter("t1");
String b = request.getParameter("t2");
String c = request.getParameter("t3");
String d = request.getParameter("t4");
String e = request.getParameter("t5");
String f = request.getParameter("t6");
%>
<h1>
	<center>Employee Registration Page</center>
</h1>
<hr>
<body bgcolor=cyan>
	<%
	out.println("Name is " + a);
	out.println("<br>");
	out.println("Phoneno is " + b);
	out.println("<br>");
	out.println("Email is " + c);
	out.println("<br>");
	out.println("Address is " + d);
	out.println("<br>");
	out.println("Age is " + e);
	out.println("<br>");
	out.println("<br>");
	%>
</body>
<% 
try{
	Class.forName("com.mysql.cj.jdbc.Driver");  // Initialisation of jdbc COMMON CODE
	Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/training","root","Admin@123");
	PreparedStatement st = con.prepareStatement("insert into emp values(?,?,?,?,?)");
	st.setString(1,a);
	st.setString(2,b);
	st.setString(3,c);
	st.setString(4,d);
	st.setString(5,e);
	st.execute();
	out.println("row Inserted");
	

}catch(Exception ae){
	out.println("The error "+ae);
}
%>
