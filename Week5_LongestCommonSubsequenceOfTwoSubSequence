#Uses python3

import sys

def edit_distance(a, b, c):
    dp_result = [[[0 for k in range(cn+1)] for j in range(bn+1)] for i in range(an+1)]

    for x in range(1, an+1):
        for y in range(1, bn+1):
            for z in range(1, cn+1):
                if a[x-1] == b[y-1] and b[y-1] == c[z-1]:
                    dp_result[x][y][z] = dp_result[x-1][y-1][z-1] + 1
                else: 
                    dp_result[x][y][z] = max(dp_result[x-1][y][z], dp_result[x][y-1][z], dp_result[x][y][z-1])

    return dp_result

def lcs3(a, b, c):
    return edit_distance(a,b,c)

if __name__ == '__main__':
    input = sys.stdin.read()
    data = list(map(int, input.split()))
    an = data[0]
    data = data[1:]
    a = data[:an]
    data = data[an:]
    bn = data[0]
    data = data[1:]
    b = data[:bn]
    data = data[bn:]
    cn = data[0]
    data = data[1:]
    c = data[:cn]
    result = lcs3(a, b, c) 
    print(result[an][bn][cn])
