## 🚀 기능 요구 사항

포비와 크롱이 페이지 번호가 1부터 시작되는 400 페이지의 책을 주웠다. 책을 살펴보니 왼쪽 페이지는 홀수, 오른쪽 페이지는 짝수 번호이고 모든 페이지에는 번호가 적혀있었다. 책이 마음에 든 포비와 크롱은 페이지 번호 게임을 통해 게임에서 이긴 사람이 책을 갖기로 한다. 페이지 번호 게임의 규칙은 아래와 같다.

1. 책을 임의로 펼친다.
2. 왼쪽 페이지 번호의 각 자리 숫자를 모두 더하거나, 모두 곱해 가장 큰 수를 구한다.
3. 오른쪽 페이지 번호의 각 자리 숫자를 모두 더하거나, 모두 곱해 가장 큰 수를 구한다.
4. 2~3 과정에서 가장 큰 수를 본인의 점수로 한다.
5. 점수를 비교해 가장 높은 사람이 게임의 승자가 된다.
6. 시작 면이나 마지막 면이 나오도록 책을 펼치지 않는다.

포비와 크롱이 펼친 페이지가 들어있는 리스트/배열 pobi와 crong이 주어질 때, 포비가 이긴다면 1, 크롱이 이긴다면 2, 무승부는 0, 예외사항은 -1로 return 하도록 solution 메서드를 완성하라.

### 제한사항

- pobi와 crong의 길이는 2이다.
- pobi와 crong에는 [왼쪽 페이지 번호, 오른쪽 페이지 번호]가 순서대로 들어있다.

### 실행 결과 예시

| pobi | crong | result |
| --- | --- | --- |
| [97, 98] | [197, 198] | 0 |
| [131, 132] | [211, 212] | 1 |
| [99, 102] | [211, 212] | -1 |

## 📌 문제 분석

## 문제1
페이지 번호 게임의 규칙에 따라 승자를 결정한다.

+ 입력 조건:
    + List<Integer> [2]
    + [왼쪽 페이지 번호, 오른쪽 페이지 번호]


+ 출력 조건:
    + int
    + pobi 승 -> 1
    + crong 승 -> 2
    + 무승부 -> 0
    + 예외사항 -> -1


+ 책의 조건: 
  + 페이지 번호는 연속적으로 적혀있다.
  + 페이지는 1부터 400까지 있다.
  + 왼쪽 페이지는 홀수, 오른쪽 페이지는 짝수이다.
  + 모든 페이지에 번호가 적혀있다. 
  + 시작 면이나 마지막 면이 나오도록 펼치지 않는다.


+ 게임 규칙:
  + 왼쪽과 오른쪽의 각 자리 숫자를 모두 더하거나 곱한다.
  + 더한 값과 곱한 값을 비교하여 더 큰 값을 점수로 한다.
  + 점수를 비교하여 더 큰 점수를 가진 사람이 승리한다.
  + 점수가 같다면 무승부이다.


## 📋 구현 기능 목록

### ✅ 책을 펼쳐 페이지 숫자 확인
+ [x] 페이지 번호를 입력받는다.
+ [x] [예외] 왼쪽이 짝수이거나 오른쪽이 홀수인 경우
+ [x] [예외] 왼쪽의 수가 오른쪽의 수보다 큰 경우
+ [x] [예외] 연속되지 않은 경우
+ [x] [예외] 1과 400쪽이 포함된 경우
+ [x] [예외] 1미만, 400초과한 수가 있는 경우

### ✅ 승리 조건 구현
+ [x] 각 자리 숫자를 더하기
+ [x] 각 자리 숫자를 곱하기
+ [x] 더한 값과 곱한 값을 비교해서 각자의 점수 결정
+ [x] 서로의 계산된 점수를 비교해 승자를 결정
