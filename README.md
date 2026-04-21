# 🐍 C++ Snake Game (Ncurses)

**Ubuntu 20.04** 환경에서 **C++**과 **Ncurses 라이브러리**를 활용하여 개발한 터미널 기반 스네이크 게임입니다. 총 4단계의 스테이지로 구성되어 있으며, 각 스테이지의 미션을 달성하여 다음 단계로 진출하는 방식입니다.

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
- [cite_start]`W`: 위로 이동 [cite: 19, 26, 34, 42]
- [cite_start]`A`: 왼쪽으로 이동 [cite: 19, 26, 34, 42]
- [cite_start]`S`: 아래로 이동 [cite: 19, 26, 34, 42]
- [cite_start]`D`: 오른쪽으로 이동 [cite: 19, 26, 34, 42]

### 🍎 아이템 (Items)
| 아이템 | 이름 | 효과 |
| :---: | :--- | :--- |
| **G** | Growth Item | [cite_start]뱀의 길이가 1 늘어납니다. [cite: 13, 21, 28, 36, 44] |
| **P** | Poison Item | [cite_start]뱀의 길이가 1 줄어듭니다. [cite: 13, 21, 28, 36, 45] |
| **R** | Reverse Item | [cite_start]일정 시간 동안 방향키 입력이 **반대로** 작동합니다. [cite: 14, 22, 29, 37, 46] |

### 🏁 스테이지 클리어 조건 (Missions)
[cite_start]다음의 미션 조건을 모두 만족하면 스테이지가 클리어되며 다음 스테이지로 이동합니다. [cite: 15, 30, 38, 46]
- [cite_start]**몸 길이**: 목표 길이 이상 달성 [cite: 15, 24, 31, 39, 47]
- [cite_start]**G 아이템**: 목표 개수 이상 획득 [cite: 15, 24, 31, 39, 47]
- [cite_start]**P 아이템**: 목표 개수 이상 획득(또는 관리) [cite: 15, 24, 31, 39, 47]
- [cite_start]**게이트(Gate)**: 특정 횟수 이상 통과 [cite: 15, 24, 31, 39, 47]

### 💀 게임 오버 (Game Over)
- [cite_start]벽(Wall)에 충돌할 경우 [cite: 15, 24, 31, 34, 48]
- [cite_start]자신의 몸(Body)에 충돌할 경우 [cite: 15, 24, 31, 34, 48]
- [cite_start]`Poison Item`을 먹어 몸의 길이가 최소 길이보다 짧아질 경우 [cite: 24, 31, 34, 48]

### 🗺 스테이지 구성
- [cite_start]**Total Stages**: 4 Levels [cite: 12, 24, 31, 34, 48]
- [cite_start]각 스테이지마다 맵의 구조와 벽의 배치가 변경되어 난이도가 상승합니다. [cite: 12, 24, 31, 34, 49]
