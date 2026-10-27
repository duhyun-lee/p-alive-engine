# P -Alive engine

The survivor engine for **P -Alive**, a Project Zomboid mod (Build 42.21+, single player).
Download the engine from **[Releases](../../releases)**; the mod itself is on the Steam Workshop.

P -Alive 모드(프로젝트 좀보이드 Build 42.21 이상, 싱글플레이)의 생존자 엔진입니다.
엔진은 **[Releases](../../releases)**에서 내려받고, 모드는 스팀 창작마당에서 구독하세요.

## Install / 설치

1. Download `P-Alive-engine-<version>.zip` from the latest release and extract it.
   최신 릴리스에서 `P-Alive-engine-<버전>.zip`을 내려받아 압축을 풉니다.
2. Close the game and double-click **`Install P-Alive.bat`**.
   It copies `P-Alive.jar` into the game folder and adds `-javaagent:P-Alive.jar` to `ProjectZomboid64.json`
   and the launch .bat files. Changed files are backed up once.
   게임을 끈 상태에서 **`Install P-Alive.bat`**을 더블클릭합니다. 게임 폴더에 엔진을 넣고 실행 설정에 한 줄을 추가하며,
   바꾸는 파일은 처음 한 번 백업됩니다.
3. Subscribe to **P -Alive** on the Steam Workshop and enable it.
   창작마당에서 **P -Alive**를 구독하고 켭니다.
4. Optional: **`Install AI chat (optional).bat`** sets up a local AI (Ollama) for free-form chat.
   선택: 자유 대화용 로컬 AI(Ollama)를 설치합니다.

After a game update or a file integrity check, run the installer again. **`Uninstall P-Alive.bat`** removes it.
게임 업데이트나 무결성 검사 뒤에는 설치 파일을 다시 실행하세요. 제거는 **`Uninstall P-Alive.bat`**입니다.

## Notes / 참고

- This repository only hosts the release downloads. / 이 저장소는 릴리스 파일만 올립니다.
- Each release lists the zip's SHA-256 so you can check the download. / 릴리스마다 zip의 SHA-256을 적어 둡니다.
- Third-party licenses are in `THIRD_PARTY_NOTICES.md` and `licenses/` inside the zip.
  사용한 외부 라이브러리 라이선스는 zip 안의 `THIRD_PARTY_NOTICES.md`와 `licenses/`에 있습니다.
- Bugs and feedback: the comments on the Workshop page. / 버그와 의견은 창작마당 페이지 댓글로 남겨 주세요.
