# -integer-triangle
# python
위와 같은 삼각형의 꼭대기에서 바닥까지 이어지는 경로 중, 거쳐간 숫자의 합이 가장 큰 경우를 찾아보려고 합니다. 아래 칸으로 이동할 때는 대각선 방향으로 한 칸 오른쪽 또는 왼쪽으로만 이동 가능합니다. 삼각형의 정보가 담긴 배열 triangle이 매개변수로 주어질 때, 거쳐간 숫자의 최댓값을 return 하는 프로그램 작성해보자!

def solution(triangle):
    answer=0
    data=[[0]*len(triangle) for _ in range(len(triangle))] #초기화
    data[0][0]=triangle[0][0]
    
    for a in range(0,len(triangle)-1):
        for b in range(len(triangle[a])):
            data[a+1][b]=max(data[a+1][b],data[a][b]+triangle[a+1][b])
            data[a+1][b+1]=max(data[a+1][b+1],data[a][b]+triangle[a+1][b+1]    #data의 계산을 다끝낸 마지막 원소들중에서 최댓값을 가르킴 
    answer=max(data[-1])  return answer
triangle=[[7],[3, 8],[8, 1, 0],[2, 7, 4, 4],[4, 5, 2, 6, 5]]
x=solution(triangle)
print(x)
