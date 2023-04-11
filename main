import java.util.Scanner;
public class TicTacToe {

	public static void main(String[] args) {
		char[][] board = new char[3][3];
		for (int row = 0; row < board.length; row++) {
			for (int col = 0; col <board.length; col ++) {
				board[row][col] = '-';
			}
		}
		printBoard(board);
		Scanner scan = new Scanner(System.in);
		boolean player1 = true;
		boolean ended = false;
		int n, m, turn = 0;
		char token;
		
		while (!ended) {
			if(player1) {
				System.out.print("Player 1: ");
				token = 'X';
			} else {
				System.out.print("Player 2: ");
				token = 'O';
			}
			
			n = scan.nextInt() - 1;
			m = scan.nextInt() - 1;
			
			if(canPlace(board, n, m)) {
				board[n][m] = token;
				turn++;
			} else {
				System.out.println("Token could not be placed, spote is taken. Try again");
				continue;
			}
			if(checkWin(board, token)) {
				if (token == 'x') System.out.println("Winner is player 1!");
				else System.out.println("Winner is Player 2!");
				printBoard(board);
				ended = true;
			} else if (turn == 9) {
				System.out.println("It's a draw!");
				printBoard(board);
				ended = true;
			} else {
				System.out.println("Unfinished.");
				printBoard(board);
			}
			player1 = !player1;
		}
	}
	
	public static void printBoard(char[][] board) {
		for (int row = 0; row < board.length; row++) {
			for (int col = 0; col < board.length; col ++) {
				System.out.print(board[row][col] + " ");
			}
			System.out.println();
		}
	}
	
	public static boolean canPlace(char[][] board, int n, int m) {
		if(board[n][m] == '-')
			return true;
		else
			return false;
	}
	
	public static boolean checkWin(char[][] board, char token) {
		if(checkHorizontal(board, token) || checkDiagonal(board, token) || checkVertical(board, token)) {
			return true;
		}
		else {
			return false;
		}
	}
	
	public static boolean checkHorizontal(char[][] board, char token) {
		for(int row = 0; row < board.length; row++) {
			int count = 0;
			for (int col = 0; col < board.length; col++) {
				if(board[row][col] == token) count++;
			}
			if(count == board.length) return true;
		}
		return false;
	}
	
	public static boolean checkVertical(char[][] board, char token) {
		for(int col = 0; col < board[0].length; col++) {
			int count = 0;
			for(int row = 0; row < board.length; row++) {
				if(board[row][col] == token) count++;
			}
			if(count == board.length) return true; 
		}
		return false;
	}
	
	public static boolean checkDiagonal(char[][] board, char token) {
		int count = 0;
		for (int row = 0; row < board.length; row++) {
			if(board[row][row] == token) count++;
		}
		if (count == board.length) return true;
		
		count = 0;
		for(int row = 0; row < board.length; row++) {
			if (board[row][board.length - 1 - row] == token) count++;
		}
		if(count == board.length) return true;
		return false;
	}
}
