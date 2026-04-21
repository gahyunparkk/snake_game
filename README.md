# 🐍 C++ Snake Game (Ncurses)

**Ubuntu 20.04** 환경에서 **C++** 과 **Ncurses 라이브러리**를 활용하여 개발한 터미널 기반 스네이크 게임입니다. 

총 4단계의 스테이지로 구성되어 있으며, 각 스테이지의 미션을 달성하여 다음 단계로 진출하는 방식입니다.

---

## 🛠 개발 환경 (Environment)
- **OS**: Ubuntu 20.04 LTS
- **Language**: C++
- **Library**: Ncurses (v6.2)

---

## 📥 설치 및 실행 방법 (Installation & Run)

### 1. Ncurses 라이브러리 설치
터미널에서 아래 명령어를 입력하여 Ncurses를 설치합니다.

```
# 다운로드 및 압축 해제
wget [https://ftp.gnu.org/pub/gnu/ncurses/ncurses-6.2.tar.gz](https://ftp.gnu.org/pub/gnu/ncurses/ncurses-6.2.tar.gz) -P ~/Downloads
cd ~/Downloads
tar -zxvf ncurses-6.2.tar.gz
cd ncurses-6.2/

# 빌드 설정 및 설치
./configure
make
sudo make install
```

### 2. 프로젝트 빌드 및 실행
```
# 리포지토리 클론
git clone [https://github.com/gahyunparkk/snake_game.git](https://github.com/gahyunparkk/snake_game.git)
cd snake_game

# 컴파일
g++ -o play_game ScoreBoard.cpp MapInit.cpp SnakeGame.cpp main.cpp -lncurses

# 게임 실행
./play_game
```

## 🎮 게임 규칙 (Game Rules)

### 🕹 조작법 (Controls)
- `W / Up`: 위로 이동
- `A / Left`: 왼쪽으로 이동
- `S / Down`: 아래로 이동
- `D / Right`: 오른쪽으로 이동

### 🍎 아이템 (Items)
| 아이템 | 이름 | 효과 |
| :---: | :--- | :--- |
| **G** | Growth Item | 뱀의 길이가 1 늘어납니다. |
| **P** | Poison Item | 뱀의 길이가 1 줄어듭니다. |
| **R** | Reverse Item | 5초간 방향키 입력이 **반대로** 작동합니다. |

### 🏁 스테이지 클리어 조건 (Missions)
다음의 미션 조건을 모두 만족하면 스테이지가 클리어되며 다음 스테이지로 이동합니다.
- **Length**: 뱀의 몸길이 **13** 달성
- **Growth**: G 아이템 **8개** 이상 획득
- **Poison**: P 아이템 **3개** 이상 획득
- **Gate**: 게이트 통과 횟수 **5회** 이상

### 💀 게임 오버 (Game Over)
- 벽에 충돌할 경우
- 자신의 몸에 충돌할 경우
- `Poison Item`을 먹어 몸의 길이가 3 미만이 될 경우

### 🗺 스테이지 구성
- **Total Stages**: 4 Levels
- 각 스테이지마다 맵의 구조와 벽의 배치가 변경되어 난이도가 상승합니다.

---

## 📂 소스코드 구조 (Project Structure)
핵심 로직이 담긴 소스 파일의 역할은 다음과 같습니다.

- **main.cpp**: 게임의 전체 루프를 실행하고 초기 설정을 담당합니다.
- **SnakeGame.cpp**: 뱀의 이동, 아이템 처리, 게임 로직 전반을 관리합니다.
- **MapInit.cpp**: 4단계 스테이지별 맵 구조를 초기화하고 렌더링합니다.
- **ScoreBoard.cpp**: 현재 점수, 획득 아이템, 스테이지 미션 달성 현황을 우측 화면에 표시합니다

---

## 📺 게임 플레이 영상 (Demo Video)

[![Snake Game Play Video](https://img.youtube.com/vi/m0fpE1VW1-g/0.jpg)](https://www.youtube.com/watch?v=m0fpE1VW1-g)

> 🔗 [전체 플레이 영상 보기 (YouTube)](https://www.youtube.com/watch?v=m0fpE1VW1-g)
