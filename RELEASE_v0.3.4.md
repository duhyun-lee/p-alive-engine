# P -Alive engine 0.3.4

Survivor engine for the **P -Alive** mod (Project Zomboid **Build 42.21**, single player). Made and tested on 42.21;
later builds (42.22 and up) may show errors.
P -Alive 모드의 생존자 엔진입니다 (프로젝트 좀보이드 **Build 42.21**, 싱글플레이). 42.21에서 만들고 시험했습니다.
42.22 이후 버전에서는 오류가 날 수 있습니다.

> **Installed with 0.3.2 or newer? Nothing to do.** The engine comes inside the Workshop mod and updates with it.
> This release is for new installs.
>
> **0.3.2 이상으로 설치했다면 할 일이 없습니다.** 엔진은 창작마당 모드 안에 들어 있어서 모드와 함께 업데이트됩니다. 이 배포는
> 새로 설치하는 분을 위한 것입니다.

## Install / 설치

1. Subscribe to P -Alive on the Steam Workshop first. / 창작마당에서 P -Alive를 먼저 구독합니다.
2. Close the game. / 게임을 끕니다.
3. Download **`P-Alive-Setup.exe`** below and run it. It finds the game folder and sets everything up (it asks for
   administrator rights when the game is under Program Files). Windows may show "Windows protected your PC" because
   the file is not signed: click **More info → Run anyway**.
   아래 **`P-Alive-Setup.exe`**를 내려받아 실행합니다. 게임 폴더를 찾아 알아서 설치합니다(게임이 Program Files 아래 있으면
   관리자 권한을 묻습니다). 서명이 없는 파일이라 "Windows의 PC 보호" 창이 뜨면 **추가 정보 → 실행**을 누르세요.
4. Enable P -Alive in the mod list. / 모드 목록에서 P -Alive를 켭니다.

The Setup also installs the optional AI chat (Ollama and its model, about 4.7 GB) and the Codex add-on, and
uninstalls. Run it again after a game update or a file integrity check.
선택 기능인 AI 대화(Ollama와 모델, 약 4.7GB)와 Codex 애드온 설치, 그리고 제거도 Setup에서 합니다. 게임 업데이트나 무결성
검사 뒤에는 Setup을 다시 실행하세요.

**The zip and the .bat installers are no longer released:** `P-Alive-Setup.exe` does everything they did.
**zip과 .bat 설치 파일은 이제 배포하지 않습니다:** `P-Alive-Setup.exe`가 같은 일을 모두 합니다.

## What's new / 바뀐 점

- **Holding their own against many:** a survivor picks the weapon that suits their skill, swing speed, weight and
  its condition; out of breath, they stop swinging wildly; they back off while still fighting, hold a doorway or put
  their back to a wall, and finish off a zombie that is down. Each is a sandbox option, on by default.
  / **여럿을 상대하기:** 자기 기술, 휘두르는 속도, 무게, 내구도에 맞는 무기를 고르고, 숨이 차면 마구 휘두르지 않으며,
  싸우면서 물러나고, 문간을 지키거나 벽을 등지고, 쓰러진 좀비를 마무리합니다. 모두 샌드박스 설정이고 기본으로 켜져 있습니다.
- **No more endless backing off:** survivors who kept stepping back from zombies, hundreds of times, and got scratched
  all over now stand and fight when that is the better choice. / **끝없는 뒷걸음 없음:** 좀비 앞에서 수백 번씩 뒷걸음만 치다
  상처투성이가 되던 생존자가, 싸우는 게 나을 때는 버티고 싸웁니다.
- **Corpse sickness:** survivors get corpse sickness from rotting bodies as the player does, and a gas mask protects
  them. / **시체 병:** 생존자도 플레이어처럼 썩은 시체 때문에 병이 들고, 방독면이 막아 줍니다.
- **Sneaking:** a sneaking survivor is much harder for zombies to notice. / **살금살금:** 살금살금 걷는 생존자는 좀비 눈에
  훨씬 덜 띕니다.
- **Walking:** fewer survivors stuck at walls, at a fence beside a gate, at a fence with a bush behind it, or on the way
  to a basement; two passing each other no longer bump into one. / **걷기:** 벽, 대문 옆 울타리, 뒤에 덤불이 있는 울타리,
  지하실 가는 길에서 막히는 일이 줄었고, 엇갈려 지나가는 두 사람이 서로 부딪쳐 겹치지 않습니다.
- **Doors and gates:** a door or a pen's gate they go through is shut behind them even in a fight, so the animals stay in.
  / **문과 대문:** 싸우는 중에 지나간 문이나 목장 대문도 뒤에서 닫아, 가축이 나가지 않습니다.
- **Saves:** a survivor no longer shows up twice with the same name after loading. / **저장:** 불러온 뒤 같은 이름의
  생존자가 둘이 되는 일이 없어졌습니다.

Farming, ranching and the blacksmith's orders were reworked in the mod itself (Workshop update).
농사, 목축, 대장장이 의뢰는 모드 쪽(창작마당 업데이트)에서 새로 정리했습니다.

## Download check / 파일 확인

- `P-Alive-Setup.exe`: `dc4a64b544f1d66bfec06e4491acdc56a870ed18112d2ba1d707d81743f56cb9`

Third-party licenses: `THIRD_PARTY_NOTICES.md` and `licenses/` in this repository.
외부 라이브러리 라이선스: 이 저장소의 `THIRD_PARTY_NOTICES.md`와 `licenses/`.
