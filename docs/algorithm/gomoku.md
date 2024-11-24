---
title: 五子棋 AI 設計
sidebar_position: 2
---

遊戲使用 `pygame` 套件設計，預設的遊戲程式是單機雙人對戰，
我們首先要做的事情，就是先理解這個遊戲的程式，然後為遊戲加上 `AI` 功能可以和玩家進行對弈。

```python
import pygame
import sys

WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
BG_COLOR = (240, 200, 120)
WIDTH, HEIGHT = 600, 600
SIZE = 15
CELL_SIZE = WIDTH / SIZE

grid = [['' for x in range(SIZE)] for y in range(SIZE)]
pygame.init()
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("五子棋")
screen.fill(BG_COLOR)

player_turn = 'b'

# 繪製棋盤
def render_board():
    for i in range(SIZE):
        pygame.draw.line(screen, BLACK, (CELL_SIZE * i, 0), (CELL_SIZE * i, HEIGHT), 2)
        pygame.draw.line(screen, BLACK, (0, CELL_SIZE * i), (WIDTH, CELL_SIZE * i), 2)

# 根據 grid 繪製棋子
def render_pieces():
    for y in range(SIZE):
        for x in range(SIZE):
            if grid[y][x] == 'b':
                draw_circle(x, y, BLACK)
            elif grid[y][x] == 'w':
                draw_circle(x, y, WHITE)

# 繪製棋子
def draw_circle(x, y, color):
    px = x * CELL_SIZE + CELL_SIZE / 2
    py = y * CELL_SIZE + CELL_SIZE / 2
    pygame.draw.circle(screen, color, (px, py), CELL_SIZE / 3)

# 處理點擊事件
def handle_click(pos):
    global player_turn
    x, y = int(pos[0] // CELL_SIZE), int(pos[1] // CELL_SIZE)
    if grid[y][x] == '':
        grid[y][x] = player_turn
        if check_winner(x, y):
            print(f"玩家 {player_turn.upper()} 勝利！")
            pygame.time.wait(2000)
            pygame.quit()
            sys.exit()
        player_turn = 'w' if player_turn == 'b' else 'b'
        AI() #觸發 AI 函式

# 輸贏判斷
def check_winner(x, y):
    a = check_line(x, y, 1, 0)
    b = check_line(x, y, -1, 0)
    c = check_line(x, y, 0, 1)
    d = check_line(x, y, 0, -1)
    e = check_line(x, y, 1, 1)
    f = check_line(x, y, -1, -1)
    g = check_line(x, y, 1, -1)
    h = check_line(x, y, -1, 1)
    return a + b >= 6 or c + d >= 6 or e + f >= 6 or g + h >= 6

# 檢查單方向
def check_line(x, y, dx, dy):
    count = 1
    player = grid[y][x]
    for i in range(1, 5):
        xx, yy = x + dx * i, y + dy * i
        if 0 <= xx < SIZE and 0 <= yy < SIZE and grid[yy][xx] == player:
            count += 1
        else:
            break
    return count

def AI():
    global player_turn
    bx, by, best_score = 0, 0, 0
    for y in range(SIZE):
        for x in range(SIZE):
            if grid[y][x] != '': continue
            grid[y][x] = 'b'
            s1 = get_score(x, y)
            grid[y][x] = 'w'
            s2 = get_score(x, y)
            grid[y][x] = ''
            score = s1 + s2 * 1.01
            if score > best_score:
                bx, by, best_score = x, y, score
    
    grid[by][bx] = player_turn
    player_turn = 'w' if player_turn == 'b' else 'b'

def get_score(x, y):
    a = check_line(x, y, 1, 0) ** 10
    b = check_line(x, y, -1, 0) ** 10
    c = check_line(x, y, 0, 1) ** 10
    d = check_line(x, y, 0, -1) ** 10
    e = check_line(x, y, 1, 1) ** 10
    f = check_line(x, y, -1, -1) ** 10
    g = check_line(x, y, 1, -1) ** 10
    h = check_line(x, y, -1, 1) ** 10
    return a * b + c * d + e * f + g * h 

# 主循環
while True:
    for event in pygame.event.get():
        if event.type == pygame.MOUSEBUTTONDOWN:
            handle_click(pygame.mouse.get_pos())
    
    screen.fill(BG_COLOR)
    render_board()
    render_pieces()
    pygame.display.flip()
```