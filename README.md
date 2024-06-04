# Library-system
In this code i have designed a Java GUI application for managing a library's book inventory


#code is as below

// Import necessary libraries
import javax.swing.*;
import java.awt.*;
import java.sql.*;

public class LibraryBookInventoryApp extends JFrame {
    // GUI Components
    private JTextField txtBookID, txtTitle, txtAuthor, txtYear;
    private JButton btnAdd, btnDelete, btnRefresh;
    private JTable tblBooks;

    // Database Connection
    private Connection connection;
    private Statement statement;

    // Constructor
    public LibraryBookInventoryApp() {
        // Initialize GUI components
        // Add book form
        JLabel lblBookID = new JLabel("Book ID:");
        txtBookID = new JTextField(10);
        JLabel lblTitle = new JLabel("Title:");
        txtTitle = new JTextField(20);
        JLabel lblAuthor = new JLabel("Author:");
        txtAuthor = new JTextField(20);
        JLabel lblYear = new JLabel("Year:");
        txtYear = new JTextField(4);

        // Buttons
        btnAdd = new JButton("Add Book");
        btnDelete = new JButton("Delete Book");
        btnRefresh = new JButton("Refresh");

        // Table to display books
        tblBooks = new JTable();

        // Set layout and add components to the frame
        setLayout(new FlowLayout());
        add(lblBookID);
        add(txtBookID);
        add(lblTitle);
        add(txtTitle);
        add(lblAuthor);
        add(txtAuthor);
        add(lblYear);
        add(txtYear);
        add(btnAdd);
        add(btnDelete);
        add(btnRefresh);
        add(new JScrollPane(tblBooks));

        // Connect to the database
        try {
            Class.forName("net.ucanaccess.jdbc.UcanaccessDriver");
            connection = DriverManager.getConnection("jdbc:ucanaccess://C:/path/to/your/database.accdb");
            statement = connection.createStatement();
        } catch (Exception e) {
            e.printStackTrace();
        }

        // Add Book Button Action
        btnAdd.addActionListener(e -> {
            // Implement adding a book to the database
        });

        // Delete Book Button Action
        btnDelete.addActionListener(e -> {
            // Implement deleting a book from the database
        });

        // Refresh Button Action
        btnRefresh.addActionListener(e -> {
            // Implement refreshing the book list
        });

        // Set frame properties
        setTitle("Library Book Inventory Management");
        setSize(800, 600);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setVisible(true);
    }

    public static void main(String[] args) {
        new LibraryBookInventoryApp();
    }
}
