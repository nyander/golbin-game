import java.util.HashSet;

/**
 * This class implements a game controller.
 * It is the top level class in this project.
 * The game communicates via text input/output
 * in the text terminal.
 * 
 * This class uses an object of class InputReader to read input
 * from the user, and an object of class Responder to generate responses.
 * It contains a loop that repeatedly reads input and generates
 * output until the users wants to leave.
 * 
 * @author     Tony Beaumont, Michael Kolling and David J. Barnes
 * @version    1.0
 */
public class Game
{
    private InputReader reader;
    private Responder responder;
    
    /**
     * Creates a game.
     */
    public Game()
    {
        reader = new InputReader();
        responder = new Responder();
    }

    /**
     * Start the game. This will print a welcome message and enter
     * into a dialog with the user, until the user ends the dialog.
     */
    public void start()
    {
        boolean finished = false;

        printWelcome();

        while(!finished) {
            String input = reader.getInput();

            if(input.contains("bye")) {
                finished = true;
            }
            else {
                String response = responder.generateResponse(input);
                System.out.println(response);
            }
        }
        printGoodbye();
    }

    /**
     * Print a welcome message to the screen.
     */
    private void printWelcome()
    {
        System.out.println("Welcome to the game.");
        System.out.println();
        System.out.println("Commands are move, look, light, pick");
        System.out.println("The aim is to keep warm");
    }

    /**
     * Print a good-bye message to the screen.
     */
    private void printGoodbye()
    {
        System.out.println("Nice talking to you. Bye...");
    }
}
