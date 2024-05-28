//organizes all elements related to the actual game

class TicTacToeGame {
    public void makeMove(Board board, int row, int col, int currentPlayer) {
        board.getBoard()[row][col] = (currentPlayer == 1) ? 'X' : 'O';
    }
    
    public boolean isGameOver(Board board) {
        return checkWin(board, 1) || checkWin(board, 2) || isBoardFull(board);
    }

    public boolean checkWin(Board board, int currentPlayer) {
        char symbol = (currentPlayer == 1) ? 'X' : 'O';
        // Check rows, columns, and diagonals
        for (int i = 0; i < 3; i++) {
            if (board.getBoard()[i][0] == symbol && board.getBoard()[i][1] == symbol && board.getBoard()[i][2] == symbol) {
                return true; //row win
            }
            if (board.getBoard()[0][i] == symbol && board.getBoard()[1][i] == symbol && board.getBoard()[2][i] == symbol) {
                return true; //column win
            }
        }
        if (board.getBoard()[0][0] == symbol && board.getBoard()[1][1] == symbol && board.getBoard()[2][2] == symbol) {
            return true; //diagonal win (top-left to bottom-right)
        }
        if (board.getBoard()[0][2] == symbol && board.getBoard()[1][1] == symbol && board.getBoard()[2][0] == symbol) {
            return true; //diagonal win (top-right to bottom-left)
        }
        return false;
    }

    public boolean isBoardFull(Board board) {
        for (char[] row : board.getBoard()) {
            for (char cell : row) {
                if (cell == '-') {
                    return false; //board not full
                }
            }
        }
        return true; //board full
    }

    //easy mode on computer
    public void computerMoveEasy(Board board) {
        int row, col;
        do {
            row = (int) (Math.random() * 3);
            col = (int) (Math.random() * 3);
        } while (board.getBoard()[row][col] != '-');
        board.getBoard()[row][col] = 'O';
    }

    public void computerMoveHard(Board board) {
        //makes a move based on the board along with the random
        computerMoveEasy(board);
    }
}
