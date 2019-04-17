# Uses python3
import sys

def get_majority_element(a, left, right):
    if left + 1 == right:
        return [[a[left]], []]

    mid = int(left + (right - left) / 2)
    left_half = get_majority_element(a, left, mid)
    right_half = get_majority_element(a, mid, right)
    return count_merge(left_half, right_half)

def count_merge(left_half, right_half):
    [left_majors, right_minors] = chunk_process(left_half[0], right_half[1])
    [right_majors, left_minors] = chunk_process(right_half[0], left_half[1])
    if left_majors[0] == right_majors[0]:
        return [left_majors + right_majors, left_minors + right_minors]
    elif len(left_majors) > len(right_majors):
        return [left_majors, right_majors + left_minors + right_minors]
    else:
        return [right_majors, left_majors + right_minors + left_minors]

def chunk_process(majors, eles):
    left = []
    for ele in eles:
        if majors[0] == ele:
            majors.append(ele)
        else:
            left.append(ele)
    return [majors, left]

if __name__ == '__main__':
    input = sys.stdin.read()
    n, *a = list(map(int, input.split()))
    result = get_majority_element(a, 0, n)
    if len(result[0]) > n/2:
        print(1)
    else:
        print(0)
