import java.util.*; //imports java utility

public class TicTacToeRunner
{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); //creates new scanner for game modes and moves
        TicTacToeGame game = new TicTacToeGame();
        int playerScore = 0;
        int computerScore = 0;
        
        //intro
        System.out.println("Welcome to Java Tic Tac Toe!");
        System.out.println("Player: X | Computer: O");

        boolean playAgain = true; //allows game to loop
        while (playAgain) {
            Board board = new Board();
            board.initializeBoard();
            int currentPlayer = 1;
            int mode = chooseMode(scanner);
            
            //move generator
            while (!game.isGameOver(board)) {
                board.printBoard();
                if (mode == 1 || currentPlayer == 1) {
                    System.out.println("Player's turn (Enter row and column):");
                    int[] move = getValidMove(scanner, board);
                    game.makeMove(board, move[0], move[1], currentPlayer);
                } else {
                    System.out.println("Computer's turn:");
                    if (mode == 2) {
                        game.computerMoveEasy(board);
                    } else {
                        game.computerMoveHard(board);
                    }
                }
                if (game.checkWin(board, currentPlayer)) {
                    board.printBoard();
                    if (currentPlayer == 1) {
                        System.out.println("Player wins!");
                        playerScore++;
                    } else {
                        System.out.println("Computer wins!");
                        computerScore++;
                    }
                    break;
                }
                if (game.isBoardFull(board)) {
                    board.printBoard();
                    System.out.println("It's a tie!");
                    break;
                }
                currentPlayer = (currentPlayer == 1) ? 2 : 1;
            }

            //ends game
            System.out.println("Player Score: " + playerScore + " | Computer Score: " + computerScore);
            System.out.println("Play again? (Y/N)");
            String choice = scanner.next();
            playAgain = choice.equalsIgnoreCase("Y");
        }
        scanner.close();
        System.out.println("Thanks for playing!");
    }

    //modes for the player to choose
    private static int chooseMode(Scanner scanner) {
        System.out.println("Select mode:");
        System.out.println("1. Play against a friend");
        System.out.println("2. Play against the computer (Easy)");
        System.out.println("3. Play against the computer (Hard)");
        int mode;
        do {
            System.out.print("Enter your choice: ");
            while (!scanner.hasNextInt()) {
                System.out.println("Invalid input! Please enter a number between 1 and 3.");
                System.out.print("Enter your choice: ");
                scanner.next();
            }
            mode = scanner.nextInt();
        } while (mode < 1 || mode > 3);
        return mode;
    }

    //checks for an errors in the move inputs
    private static int[] getValidMove(Scanner scanner, Board board) {
        int[] move = new int[2];
        boolean isValidMove = false;
        while (!isValidMove) {
            System.out.print("Enter row and column (0-2 separated by space): ");
        while (!scanner.hasNextInt()) {
            System.out.println("Invalid input! Please enter two integers.");
            System.out.print("Enter row and column (0-2 separated by space): ");
            scanner.next();
        }
        move[0] = scanner.nextInt();
        while (!scanner.hasNextInt()) {
            System.out.println("Invalid input! Please enter two integers.");
            System.out.print("Enter row and column (0-2 separated by space): ");
            scanner.next();
        }
        move[1] = scanner.nextInt();
        if (move[0] < 0 || move[0] > 2 || move[1] < 0 || move[1] > 2 || board.getBoard()[move[0]][move[1]] != '-') {
            System.out.println("Invalid move! Try again.");
        } else {
            isValidMove = true;
        }
        }
        return move;
    }
}
