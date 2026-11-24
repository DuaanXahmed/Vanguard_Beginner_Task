# Key Notes For Beginner Task (Team Vanguard)

## Part 1 – Explore
- git status — shows working directory status and staged changes waiting for next commit.
- git log --oneline — shows commit history in compact form.
- git branch -a — lists all local and remote branches.
- game.cpp has the game logic and algorithm. random.cpp has a helper that returns a random number. main.cpp calls playGame(). game.h declares both functions so other files can call them.

## Part 2 – Error Correction
1. Fixed games.cpp to game.cpp in add_executable(). This error came from cmake -S . -B build` at the configure stage because CMake checks files exist before compiling.
2. Added target_include_directories(guessquest PRIVATE include) so the compiler could find game.h in the include directory.
3. Added random.cpp in add_executable(). The randomNumber error came from the linker because game.cpp called a function whose code was in random.cpp, which wasn't being compiled.

## Part 3 & 4 – Feature Addition
- Added limited attempts by pulling from upstream and merging into my fork.
- Added hints feature that tells user "Too high!" or "Too low!" after every wrong guess.
- Added play again with a while loop that breaks when user enters N or n.

## Questions

1. CMake vs compiler?
CMake generates Makefiles from CMakeLists.txt. The compiler compiles .cpp code into machine code.

2. git add vs commit vs push?
git add stages changes, git commit saves locally, git push uploads to remote GitHub.

3. Why did the conflict happen?
Both branches edited the same loop. Traced both logics separately first then came up with a combined logic.

4. Hardest error?
The merge conflict of the two features ,difficult to locate which logic was clashing. Learned to analyze both sides of the conflict first and then come up with a redefined solution.