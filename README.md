private TextField usernameField;
private PasswordField passwordField;
private Button loginButton;
private Button registerButton;

public static void main(String[] args) {
    launch(args);
}

@Override
public void start(Stage primaryStage) {
    primaryStage.setTitle("Login & Register");

    // Crear un GridPane para organizar los elementos
    GridPane grid = new GridPane();
    grid.setPadding(new Insets(10, 10, 10, 10));
    grid.setVgap(5);
    grid.setHgap(5);

    // Agregar campos de texto
    Label usernameLabel = new Label("Usuario:");
    GridPane.setConstraints(usernameLabel, 0, 0);
    usernameField = new TextField();
    GridPane.setConstraints(usernameField, 1, 0);

    Label passwordLabel = new Label("Contraseña:");
    GridPane.setConstraints(passwordLabel, 0, 1);
    passwordField = new PasswordField();
    GridPane.setConstraints(passwordField, 1, 1);

    grid.getChildren().addAll(usernameLabel, usernameField, passwordLabel, passwordField);

    // Agregar botones
    loginButton = new Button("Iniciar sesión");
    GridPane.setConstraints(loginButton, 0, 2);

    registerButton = new Button("Registrarse");
    GridPane.setConstraints(registerButton, 1, 2);

    grid.getChildren().addAll(loginButton, registerButton);

    // Eventos de botones
    loginButton.setOnAction(e -> login());
    registerButton.setOnAction(e -> register());

    // Crear una escena y mostrarla en el escenario
    Scene scene = new Scene(grid, 300, 150);
    primaryStage.setScene(scene);
    primaryStage.show();
}

private void login() {
    String username = usernameField.getText();
    String password = passwordField.getText();

    // Aquí puedes agregar la lógica de inicio de sesión, como verificar las credenciales en una base de datos
    // o realizar comprobaciones adicionales.

    System.out.println("Iniciando sesión...");
    System.out.println("Usuario: " + username);
    System.out.println("Contraseña: " + password);
}

private void register() {
    String username = usernameField.getText();
    String password = passwordField.getText();

    // Aquí puedes agregar la lógica de registro, como guardar las credenciales en una base de datos
    // o realizar validaciones adicionales.

    System.out.println("Registrando usuario...");
    System.out.println("Nuevo usuario: " + username);
    System.out.println("Contraseña: " + password);
}
