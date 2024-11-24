---
title: 五子棋 AI 設計
sidebar_position: 2
---

遊戲使用 `pygame` 套件設計，預設的遊戲程式是單機雙人對戰，
我們首先要做的事情，就是先理解這個遊戲的程式，然後為遊戲加上 `AI` 功能可以和玩家進行對弈。

- `grid` 存放棋盤狀態， `""` 空字串表示空 `"b"` 表示黑棋 `"w"` 表示白棋
- `turn` 是紀錄目前換誰下，`b` 表示黑棋 `w` 表示白棋
- `AI()` 是你要設計的函式，你要讀取棋盤資料並找出最佳的策略
- `pace(x, y)` 是下棋的函式，它會根據 `x` 和 `y` 和 `turn` 將棋子放入並切換 `turn`

```python
import pygame
import sys

# 定義顏色
WHITE = (255, 255, 255)  # 白色
BLACK = (0, 0, 0)  # 黑色
BG_COLOR = (240, 200, 120)  # 背景色

# 定義視窗與棋盤尺寸
WIDTH, HEIGHT = 600, 600  # 視窗長寬
SIZE = 15  # 棋盤格子數
CELL_SIZE = WIDTH / SIZE  # 每個格子的大小

# 初始化棋盤，使用二維串列表示，每格初始為空
grid = [['' for x in range(SIZE)] for y in range(SIZE)]

# 初始化 pygame
pygame.init()
screen = pygame.display.set_mode((WIDTH, HEIGHT))  # 設定視窗大小
pygame.display.set_caption("五子棋")  # 設定視窗標題
screen.fill(BG_COLOR)  # 填充背景顏色

# 定義初始輪到的玩家，'b' 表示黑棋，'w' 表示白棋
turn = 'b'

# 繪製棋盤的函式
def render_board():
    for i in range(SIZE):  # 繪製垂直與水平線條
        pygame.draw.line(screen, BLACK, (CELL_SIZE * i, 0), (CELL_SIZE * i, HEIGHT), 2)
        pygame.draw.line(screen, BLACK, (0, CELL_SIZE * i), (WIDTH, CELL_SIZE * i), 2)

# 根據棋盤狀態繪製所有棋子
def render_pieces():
    for y in range(SIZE):  # 遍歷棋盤每一格
        for x in range(SIZE):
            if grid[y][x] == 'b':  # 若該格為黑棋
                draw_circle(x, y, BLACK)
            elif grid[y][x] == 'w':  # 若該格為白棋
                draw_circle(x, y, WHITE)

# 繪製單顆棋子的函式
def draw_circle(x, y, color):
    px = x * CELL_SIZE + CELL_SIZE / 2  # 棋子圓心的 x 座標
    py = y * CELL_SIZE + CELL_SIZE / 2  # 棋子圓心的 y 座標
    pygame.draw.circle(screen, color, (px, py), CELL_SIZE / 3)  # 繪製圓形棋子

# 處理滑鼠點擊事件
def handle_click(pos):
    x, y = int(pos[0] // CELL_SIZE), int(pos[1] // CELL_SIZE)  # 計算點擊位置的格子座標
    if grid[y][x] == '':  # 若該格為空，允許落子
        place(x, y)  # 玩家下棋
        AI()  # 呼叫 AI 下棋

# 放置棋子並切換玩家
def place(x, y):
    global turn
    if grid[y][x] == '':  # 確保該格為空
        grid[y][x] = turn  # 在該格放置當前玩家的棋子
    turn = 'w' if turn == 'b' else 'b'  # 切換到另一位玩家
    if check_winner(x, y):  # 檢查是否有玩家獲勝
        print(f"玩家 {turn.upper()} 勝利！")
        pygame.time.wait(2000)  # 等待兩秒顯示結果
        pygame.quit()  # 關閉 pygame
        sys.exit()  # 結束程式

# 檢查當前玩家是否獲勝
def check_winner(x, y):
    a = check_line(x, y, 1, 0)  # 檢查水平線 (右方向)
    b = check_line(x, y, -1, 0)  # 檢查水平線 (左方向)
    c = check_line(x, y, 0, 1)  # 檢查垂直線 (下方向)
    d = check_line(x, y, 0, -1)  # 檢查垂直線 (上方向)
    e = check_line(x, y, 1, 1)  # 檢查主對角線 (右下方向)
    f = check_line(x, y, -1, -1)  # 檢查主對角線 (左上方向)
    g = check_line(x, y, 1, -1)  # 檢查副對角線 (右上方向)
    h = check_line(x, y, -1, 1)  # 檢查副對角線 (左下方向)
    return a + b >= 4 or c + d >= 4 or e + f >= 4 or g + h >= 4  # 任何方向的總和 >= 4 視為勝利

# 檢查單一方向的連續棋子數
def check_line(x, y, dx, dy):
    count = 0
    player = grid[y][x]  # 當前玩家的棋子類型
    for i in range(1, 5):  # 檢查當前棋子周圍的 4 格
        xx, yy = x + dx * i, y + dy * i  # 計算下一格座標
        if 0 <= xx < SIZE and 0 <= yy < SIZE and grid[yy][xx] == player:  # 確認座標有效且棋子類型一致
            count += 1
        else:
            break
    return count

# AI 下棋邏輯
def AI():
    global turn
    bx, by, best_score = 0, 0, 0  # 初始化最佳分數與位置
    for y in range(SIZE):
        for x in range(SIZE):
            if grid[y][x] == '': # 跳過非空格

                # 計算攻擊分數

                # 計算防守分數

                # 如果分數超過目前最佳的策略就更新
    
    place(bx, by)  # 在最佳位置下棋

# 計算某位置的分數
def get_score(x, y):
    pass

# 主循環
while True:
    for event in pygame.event.get():  # 處理事件
        if event.type == pygame.MOUSEBUTTONDOWN:  # 滑鼠點擊
            handle_click(pygame.mouse.get_pos())  # 處理點擊位置
    
    screen.fill(BG_COLOR)  # 重繪背景
    render_board()  # 繪製棋盤
    render_pieces()  # 繪製棋子
    pygame.display.flip()  # 更新畫面
```