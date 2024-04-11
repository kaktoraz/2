def initialize_board():
    """Создает пустую доску 3x3."""
    return [[' ' for _ in range(3)] for _ in range(3)]

def display_board(board):
    """Отображает текущее состояние доски."""
    for row in board:
        print(' | '.join(row))
        print('-' * 9)

def get_player_move():
    """Запрашивает у игрока координаты хода."""
    row, col = map(int, input("Введите номер строки (1-3) и столбца (1-3): ").split())
    return row - 1, col - 1

def is_valid_move(board, row, col):
    """Проверяет, что ход игрока допустим."""
    return 0 <= row < 3 and 0 <= col < 3 and board[row][col] == ' '

def make_move(board, player, row, col):
    """Выполняет ход игрока на доске."""
    board[row][col] = player

def check_winner(board, player):
    """Проверяет, есть ли победитель."""
    for i in range(3):
        if all(board[i][j] == player for j in range(3)) or all(board[j][i] == player for j in range(3)):
            return True
    return board[0][0] == board[1][1] == board[2][2] == player or board[0][2] == board[1][1] == board[2][0] == player

def is_board_full(board):
    """Проверяет, заполнена ли доска."""
    return all(all(cell != ' ' for cell in row) for row in board)

def play_tic_tac_toe():
    current_player = 'X'
    game_board = initialize_board()
    while True:
        display_board(game_board)
        print(f"Ход игрока {current_player}.")
        move = get_player_move()
        if is_valid_move(game_board, *move):
            make_move(game_board, current_player, *move)
            if check_winner(game_board, current_player):
                print(f"Игрок {current_player} побеждает!")
                break
            elif is_board_full(game_board):
                print("Игра заканчивается вничью!")
                break
            else:
                current_player = 'O' if current_player == 'X' else 'X'
        else:
            print("Недопустимый ход. Попробуйте снова.")

if __name__ == "__main__":
    play_tic_tac_toe()
