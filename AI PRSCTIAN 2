from collections import deque

# Grid
grid = [
    ['S', '.', '.', '#'],
    ['.', '#', '.', '.'],
    ['.', '.', '.', '#'],
    ['#', '.', 'T', '.']
]

rows = len(grid)
cols = len(grid[0])

# Find Start and Treasure
for i in range(rows):
    for j in range(cols):
        if grid[i][j] == 'S':
            start = (i, j)
        elif grid[i][j] == 'T':
            goal = (i, j)

# Possible moves
directions = [(-1,0), (1,0), (0,-1), (0,1)]

# BFS
queue = deque([start])
visited = {start}

# Store all popped values
popped_values = []

while queue:
    current = queue.popleft()

    # Store the popped value
    popped_values.append(current)

    if current == goal:
        print("Treasure Found!")
        break

    for dx, dy in directions:
        nx = current[0] + dx
        ny = current[1] + dy

        if (0 <= nx < rows and
            0 <= ny < cols and
            grid[nx][ny] != '#' and
            (nx, ny) not in visited):

            visited.add((nx, ny))
            queue.append((nx, ny))

print("\nTraversal Order (Popped Values):")
print(popped_values)
