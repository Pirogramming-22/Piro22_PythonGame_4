# Piro22_PythonGame_4

## 과제 협의사항

### 1. Commit Type

| Keyword | When to use |
| --- | --- |
| `feat`  | 기능 관련 커밋 |
| `fix` | 버그 수정 |
| `add` | 내용을 추가하였을 때 |
| `chore` | 기타 변경 사항 |

- 기능을 추가하거나 코드 수정하기 전 자주 커밋하기
- 주요 부분 완성할 때 마다 main에 merge 하여 자주 동기화
- Merge 할 때 마다 팀원들에게 전파하기

### 2. Branch

| Branch 종류 | 설명 |
| --- | --- |
| `main` | 메인 브랜치 |
| `member's name` | 담당 부분별 분업화 |

## 개발 규칙
1. 글로벌 변수 사용 시 팀원들에게 미리 알리기
2. 글로벌 변수명 규칙: 함수명_변수명
3. 각자 구현할 기능을 .py 파일에 함수로 구현 후 push
4. 함수명과 파일명 일치시키기
   - 예시: 
     - 함수명: `whaleGame()`
     - 파일명: `whaleGame.py`

## 프로젝트 소개
🍺 Python 술게임 파티

혼자서도 즐기는 Python 술게임 프로젝트로, 실제 플레이어와 AI 친구들이 함께 즐기는 5가지 미니게임(숫자 맞추기, 가위바위보 하나빼기, 시장에 가면, 딸기 게임, 좋아 게임)을 통해 술자리의 재미를 느낄 수 있습니다. 게임에서 패배한 플레이어는 술을 마시게 되며, 자신의 주량에 도달하면 게임이 종료됩니다.

## 👥 Contributors

| 이름 | 담당 게임 |
|------|-----------|
| 홍다오 | 초기 프롬프트 & 숫자맞추기 |
| 박서정 | 가위바위보 하나빼기 |
| 한종서 | 시장에 가면 |
| 남경민 | 딸기 게임 |
| 조주영 | 좋아게임 |

## 프로젝트 구조

## 구현된 기능

### 1. 게임 시스템 (game.py)
- [x] 게임 시작 화면 구현
- [x] 플레이어 클래스 구현 (이름, 주량, 현재 마신 잔 수 관리)
- [x] 사용자 정보 입력 (이름, 주량 선택)
- [x] 다른 플레이어 초대 기능 (1-3명)
- [x] 턴제 게임 시스템
- [x] 게임 선택 및 실행
- [x] 게임 결과에 따른 음주량 반영
- [x] 치사량 도달 시 게임 종료
- [x] 다음 게임 선택자 결정 (현재 가장 많이 마신 사람)

### 2. 미니게임
#### 2.1 숫자 맞추기 (number_game.py)
- [x] 1-10 사이의 숫자 맞추기
- [x] 5번의 기회 제공
- [x] Up/Down 힌트 제공
- [x] 실패 시 1잔 벌칙
- [x] AI 플레이어 구현 (이전 결과 기반 추측)

#### 2.2 가위바위보 하나빼기 (rps_game.py)
- [ ] 게임 로직 구현 필요

#### 2.3 시장에 가면 (market_game.py)
- [ ] 게임 로직 구현 필요

#### 2.4 딸기 게임 (strawberry_game.py)
- [ ] 게임 로직 구현 필요

#### 2.5 좋아 게임 (like_game.py)
- [ ] 게임 로직 구현 필요

## **모듈 구조**

### **game.py**
- **클래스**
  - `class Player`: 플레이어 정보 관리
    - `__init__(name, tolerance)`: 플레이어 초기화
    - `drink(amount) -> bool`: 음주량 추가 및 치사량 체크
      - 매개변수:
        - `amount (int)`: 추가로 마셔야 할 잔 수
      - 반환값:
        - `True`: 치사량 도달
        - `False`: 치사량 미도달
- **함수**
  - `gamestart()`: 게임 시작 및 메인 로직
  - `gameover()`: 게임 종료 화면 출력


### **number_game.py**
- **함수**
  - `숫자맞추기(is_friend=False)`: 숫자 맞추기 게임 실행
    - 매개변수:
      - `is_friend (bool)`: AI 플레이어 여부
    - 반환값:
      - 성공: `0`
      - 실패: `1` (벌칙 잔 수)


### **rps_game.py**
- **함수**
  - `가위바위보하나빼기(players, is_human) -> dict`
    - **설명**: 가위바위보에서 승자를 제외한 패자들이 벌주를 마시는 게임
    - 매개변수:
      - `players (list[Player])`: 참가자 리스트
      - `is_human (bool)`: 현재 플레이어가 실제 사용자 여부
    - 반환값:
      - `{Player: int}`: 패자와 마셔야 할 잔 수


### **market_game.py**
- **함수**
  - `시장에가면(players, is_human) -> dict`
    - **설명**: 규칙에 맞는 단어를 말하는 게임
    - 매개변수:
      - `players (list[Player])`: 참가자 리스트
      - `is_human (bool)`: 현재 플레이어가 실제 사용자 여부
    - 반환값:
      - `{Player: int}`: 실패한 플레이어와 마셔야 할 잔 수


### **strawberry_game.py**
- **함수**
  - `strawberry_game(current_player, other_players) -> dict`
    - **설명**: 박자에 맞춰 '딸기'를 외치는 게임
    - 매개변수:
      - `current_player (str)`: 현재 차례인 플레이어 이름
      - `other_players (list[str])`: 다른 플레이어 이름 리스트
    - 반환값:
      - `{Player: int}`: 패자와 마셔야 할 잔 수


### **like_game.py**
- **함수**
  - `좋아게임(players, is_human) -> dict`
    - **설명**: 질문과 대답으로 상대를 곤란하게 만드는 게임
    - 매개변수:
      - `players (list[Player])`: 참가자 리스트
      - `is_human (bool)`: 현재 플레이어가 실제 사용자 여부
    - 반환값:
      - `{Player: int}`: 실패한 플레이어와 마셔야 할 잔 수


## **게임 결과 처리**
- 모든 게임은 `{Player: int}` 형식의 결과를 반환
  - `Player`: 벌주를 마셔야 하는 플레이어 객체
  - `int`: 추가로 마셔야 할 잔 수
- 반환된 결과를 통해 `drink(amount)` 메서드를 호출하여 벌주 적용


## **게임 종료**
- **조건**: 플레이어 중 한 명이라도 `tolerance`를 초과하면 게임 종료
- **동작**: 종료 메시지 출력 및 프로그램 종료

## 회의 일정
- **01-06** 23:00

## 마감일
- **01-07** 10:00 (마지막 커밋 시간 기준)