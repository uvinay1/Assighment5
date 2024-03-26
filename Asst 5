import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.Statement;

public class StoreDepartment {

    public static void main(String[] args) throws Exception {
        String url = "jdbc:mysql://localhost:3306/departments";
        String username = "your_username";
        String password = "your_password";
        Department department = new Department(1, "Engineering");

        Connection connection = null;
        Statement statement = null;

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            connection = DriverManager.getConnection(url, username, password);
            statement = connection.createStatement();
            String sql = "INSERT INTO department (id, name) VALUES (" + department.getId() + ", '" + department.getName() + "')";
            statement.executeUpdate(sql);
            System.out.println("Department " + department.getName() + " stored successfully!");

        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            if (statement != null) {
                statement.close();
            }
            if (connection != null) {
                connection.close();
            }
        }
    }
}

class Department {
    private int id;
    private String name;

    public Department(int id, String name) {
        this.id = id;
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }
}