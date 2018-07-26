# English-tense-cecker
This programme checks your ability to choose the right tense in English
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.canvas.Canvas;
import javafx.scene.canvas.GraphicsContext;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.layout.Background;
import javafx.scene.layout.BackgroundFill;
import javafx.scene.layout.CornerRadii;
import javafx.scene.layout.FlowPane;
import javafx.scene.paint.Color;
import javafx.stage.Stage;

public class Dispatcher extends Application {
	Color[] col = { Color.BLACK, Color.AQUAMARINE, Color.BLUE, Color.BLUEVIOLET, Color.BROWN, Color.BURLYWOOD,
			Color.CHARTREUSE, Color.CORAL, Color.CRIMSON, Color.GOLD, Color.RED, Color.YELLOW, Color.GREEN,
			Color.SKYBLUE, Color.WHITE, Color.PURPLE, Color.SANDYBROWN, Color.ROYALBLUE, Color.DARKORCHID,
			Color.GREENYELLOW, Color.INDIANRED, Color.BISQUE, Color.SILVER, Color.LIGHTCORAL, Color.MEDIUMSLATEBLUE,
			Color.PINK, Color.DARKVIOLET, Color.SPRINGGREEN, Color.HOTPINK, Color.LIGHTBLUE };

	Label response;
	Label response2;
	Label response3;
	static int n = 0;
	Button btn1;
	Button btn2;
	Button btn3;
	Button btn4;
	Button btn5;
	Button btn6;
	Button btn7;
	Button btn8;
	Button btn9;
	Button btn10;

	@Override
	public void start(Stage primaryStage) {

		response = new Label();
		response2 = new Label();
		response3 = new Label();
		response.setAlignment(Pos.CENTER);
		response2.setAlignment(Pos.CENTER);
		response3.setAlignment(Pos.CENTER);
		response.setText(
				"Choose from the sentences which are signed with the same number the one made using the right tense, please :-)");
		response.setTextFill(Color.WHITE);
		response2.setTextFill(Color.WHITE);
		response3.setTextFill(Color.WHITE);
		btn1 = new Button("1) I have been to Paris three times.                     ");
		btn1.setOnAction(e -> btn1_click());
		btn2 = new Button("1) I was in Paris three times.                              ");
		btn2.setOnAction(e -> btn2_click());
		btn3 = new Button("2) The sun rises on the east.                                ");
		btn3.setOnAction(e -> btn1_click());
		btn4 = new Button("2) The sun is rising on the east.                          ");
		btn4.setOnAction(e -> btn4_click());
		btn5 = new Button("3) We had supper when he came.                       ");
		btn5.setOnAction(e -> btn5_click());
		btn6 = new Button("3) We were having supper when he came.         ");
		btn6.setOnAction(e -> btn1_click());
		btn7 = new Button("4) I will be lying on a beach this time next week.");
		btn7.setOnAction(e -> btn1_click());
		btn8 = new Button("4) I will lie on a beach this time next week.        ");
		btn8.setOnAction(e -> btn8_click());
		btn9 = new Button("5) He always confuses my name.                         ");
		btn9.setOnAction(e -> btn9_click());
		btn10 = new Button("5) He is always comfusing my name!                  ");
		btn10.setOnAction(e -> btn1_click());
		btn1.setAlignment(Pos.TOP_LEFT);
		btn3.setAlignment(Pos.TOP_LEFT);
		btn2.setAlignment(Pos.CENTER_RIGHT);
		btn4.setAlignment(Pos.CENTER_RIGHT);
		btn5.setAlignment(Pos.TOP_LEFT);
		btn7.setAlignment(Pos.TOP_LEFT);
		btn6.setAlignment(Pos.CENTER_RIGHT);
		btn8.setAlignment(Pos.CENTER_RIGHT);
		btn9.setAlignment(Pos.TOP_LEFT);
		btn10.setAlignment(Pos.CENTER_RIGHT);
		FlowPane frame = new FlowPane(10, 60);
		frame.setBackground(new Background(new BackgroundFill(Color.PURPLE, CornerRadii.EMPTY, Insets.EMPTY)));
		frame.getChildren().add(btn1);
		frame.getChildren().add(btn2);
		frame.getChildren().add(btn3);
		frame.getChildren().add(btn4);
		frame.getChildren().add(btn5);
		frame.getChildren().add(btn6);
		frame.getChildren().add(btn7);
		frame.getChildren().add(btn8);
		frame.getChildren().add(btn9);
		frame.getChildren().add(btn10);
		frame.getChildren().add(response);
		frame.getChildren().add(response2);
		frame.getChildren().add(response3);

		Scene scene = new Scene(frame, 1000, 1000);
		Canvas canvas = new Canvas(1000, 1000);
		frame.getChildren().add(canvas);
		GraphicsContext gc = canvas.getGraphicsContext2D();
		primaryStage.setScene(scene);
		gc.setFill(Color.RED);
		gc.fillOval(700, 80, 500, 500);
		gc.setFill(Color.YELLOW);
		gc.fillOval(750, 129, 450, 450);
		gc.setFill(Color.YELLOWGREEN);
		gc.fillOval(800, 180, 400, 400);
		gc.setFill(Color.BLUE);
		gc.fillOval(850, 230, 350, 350);
		gc.setFill(Color.PURPLE);
		gc.fillOval(900, 280, 300, 300);
		primaryStage.setTitle("E N G L I S H   G R A M M A R");
		primaryStage.show();

	}

	public void btn9_click() {
		response.setText("Your answer is wrong!");
		response.setTextFill(Color.RED);
		response2.setText("Your score is: " + n + "/5");
		response3.setText("We can express our concern with 'always' and Present Progressive.  ");

	}

	public void btn8_click() {
		response.setText("Your answer is wrong!");
		response.setTextFill(Color.RED);
		response2.setText("Your score is: " + n + "/5");
		response3.setText("We use Future Progressive with words: 'this time next week/ tomorrow and so on'.  ");

	}

	public void btn5_click() {
		response.setText("Your answer is wrong!");
		response.setTextFill(Color.RED);
		response2.setText("Your score is: " + n + "/5");
		response3.setText("The action in Past Simple interrupts the action in Past Progressive!  ");

	}

	public void btn4_click() {
		response.setText("Your answer is wrong!");
		response.setTextFill(Color.RED);
		response2.setText("Your score is: " + n + "/5");
		response3.setText("Never forget, we use Present Simple speaking about the laws of nature! ");

	}

	public void btn1_click() {
		response.setText("Your answer is right!");
		response.setTextFill(Color.WHITE);
		n++;
		response2.setText("Your score is: " + n + "/5");
		if (n == 5) {
			response.setText("Well done!");
		}
	}

	public void btn2_click() {
		response.setText("Your answer is wrong!");
		response.setTextFill(Color.RED);
		response2.setText("Your score is: " + n + "/5");
		response3.setText(" We usually use The Present Perfect with the question 'How many times?'");
		
	}

	public static void main(String[] args) {
		launch(args);

	}

}

