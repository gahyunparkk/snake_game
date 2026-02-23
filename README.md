# C++ 프로그래밍 프로젝트: Ncurses 라이브러리를 활용한 스네이크 게임 개발

## Ncurses 설치 및 실행 방법

```
Wget https://ftp.gnu.org/pub/gnu/ncurses/ncurses-6.2.tar.gz-P~/Downloads
cd Downloads/ncurses-6.2/
ncurses-6.2.tar.gz
make
make install
```

```
git clone https://github.com/gahyunparkk/snake_game.git
g++ -o play_game ScoreBoard.cpp MapInit.cpp SnakeGame.cpp main.cpp -lncurses
./main
```
