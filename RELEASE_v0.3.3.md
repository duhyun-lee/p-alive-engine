# P -Alive engine 0.3.3

Survivor engine for the **P -Alive** mod (Project Zomboid Build 42.21+, single player).
P -Alive 모드의 생존자 엔진입니다 (Project Zomboid Build 42.21 이상, 싱글플레이).

> **Installed with 0.3.2 or newer? Nothing to do.** The engine comes inside the Workshop mod and updates with it; this
> release is for new installs and for the zip. Installed 0.3.1 or older, or the game closes right after pressing Play:
> run `P-Alive-Setup.exe` once (see 0.3.2's notes for why).
>
> **0.3.2 이상으로 설치했다면 할 일이 없습니다.** 엔진은 창작마당 모드 안에 들어 있어서 모드와 함께 업데이트됩니다. 이 배포는
> 새로 설치하는 분과 zip용입니다. 0.3.1 이하를 설치했거나 플레이를 누르자마자 게임이 꺼진다면 `P-Alive-Setup.exe`를 한 번
> 실행하세요(이유는 0.3.2 안내 참고).

## Install / 설치

1. Subscribe to P -Alive on the Steam Workshop first. / 창작마당에서 P -Alive를 먼저 구독합니다.
2. Close the game. / 게임을 끕니다.
3. **Easiest: download `P-Alive-Setup.exe` below and run it.** It finds the game folder and sets everything up
   (it asks for administrator rights when the game is under Program Files). Windows may show "Windows protected your
   PC" because the file is not signed: click **More info → Run anyway**.
   **가장 쉬운 방법: 아래 `P-Alive-Setup.exe`를 내려받아 실행합니다.** 게임 폴더를 찾아 알아서 설치합니다(게임이
   Program Files 아래 있으면 관리자 권한을 묻습니다). 서명이 없는 파일이라 "Windows의 PC 보호" 창이 뜨면 **추가 정보 → 실행**을
   누르세요.
   Or the zip: download `P-Alive-engine-0.3.3.zip`, extract it and double-click **`Install P-Alive.bat`**.
   또는 zip: `P-Alive-engine-0.3.3.zip`을 풀고 **`Install P-Alive.bat`**을 더블클릭합니다.
4. Enable P -Alive in the mod list. / 모드 목록에서 P -Alive를 켭니다.
5. Optional: free-form chat needs Ollama and the chat model (about 4.7 GB): the Setup offers it, or run
   **`Install AI chat (optional).bat`** from the zip.
   선택: 자유 대화에는 Ollama와 대화 모델(약 4.7GB)이 필요합니다. Setup에서 고르거나 zip의
   **`Install AI chat (optional).bat`**을 실행하세요.

**Installed 0.3.1 or older? Run the installer once more.** The launch settings now point at a small starter
(`P-Alive-starter.jar` in the game folder) that loads the engine inside the Workshop mod at every launch, so the engine
updates with the mod, and the game still starts after you unsubscribe (0.3.1 pointed straight at the Workshop file,
and the game would not start once that file was gone).
**0.3.1 이하를 설치했다면 설치 파일을 한 번 더 실행하세요.** 이제 실행 설정은 게임 폴더의 작은 시작 파일
(`P-Alive-starter.jar`)을 가리키고, 게임을 켤 때마다 창작마당 모드 안의 엔진을 불러옵니다. 엔진은 모드와 함께 업데이트되고,
구독을 끊어도 게임은 평소처럼 켜집니다(0.3.1은 창작마당 파일을 직접 가리켜서, 그 파일이 없어지면 게임이 켜지지 않았습니다).

Run the installer again after a game update or file integrity check. Uninstall: `P-Alive-Setup.exe` or
`Uninstall P-Alive.bat`.
게임 업데이트나 무결성 검사 뒤에는 설치 파일을 다시 실행하세요. 제거는 `P-Alive-Setup.exe` 또는 `Uninstall P-Alive.bat`.

## What's new / 바뀐 점

- **Survivors drive:** a survivor takes the wheel of a base car and drives it along the roads: brings it to you, drives
  to a spot you pick on the map, or follows your car. The route ahead shows on the map with the distance and time left.
  / **운전:** 생존자가 거점 차를 몰고 도로를 따라갑니다. 차를 가져오고, 지도에서 고른 곳으로 가고, 내 차를 따라옵니다. 남은
  길이 지도에 거리, 시간과 함께 보입니다.
- **Swimming:** with the "Yeah it's water bitch" mod on, survivors follow you into the water and out again, and one who
  falls in swims to dry ground. / **수영:** "Yeah it's water bitch" 모드를 켜면 생존자가 나를 따라 물에 들어가고 나오며,
  빠진 사람은 가까운 땅으로 헤엄쳐 나옵니다.
- **Lights:** a flashlight, lantern or torch a survivor holds now lights up the area (the game only lit the player's).
  / **불빛:** 생존자가 든 손전등, 랜턴, 횃불이 실제로 주변을 밝힙니다(게임은 플레이어 것만 밝혔습니다).
- **No more stagger:** a survivor running into you no longer makes you stagger or fall (sandbox option, on by
  default). / **부딪힘:** 달리던 생존자와 부딪혀도 휘청이거나 넘어지지 않습니다(샌드박스 설정, 기본 켬).
- **Grades in a fight:** higher grades attack faster, shoot straighter and hold their ground longer; every fight a
  survivor learns from makes them a little braver (table below). / **등급과 싸움:** 높은 등급일수록 더 빨리 치고, 더 잘
  맞히고, 더 오래 버팁니다. 싸움을 겪을수록 조금씩 용감해집니다(아래 표).
- **Fire:** campfires and other lasting fires are walked round (survivors used to walk through them); a survivor next
  to, under or on a fire gets away from it first. / **불:** 모닥불처럼 계속 타는 불을 돌아갑니다(전에는 지나갔습니다). 불
  옆이나 불 위에 있으면 먼저 피합니다.
- **Walking:** no more walking through someone standing at the end of the way; trees and bushes, which slow and hurt,
  are kept out of the spots survivors pick. / **걷기:** 목적지 앞에 선 사람을 뚫고 지나가지 않습니다. 느려지고 다치는 나무와
  덤불 칸은 서 있을 자리로 고르지 않습니다.
- **Saves:** survivors are saved every 30 minutes of play, not only on quit; one whose body would not load is kept
  where they were and tried again the next time, not lost. / **저장:** 플레이 30분마다 생존자를 저장합니다(나갈 때만이
  아니라). 몸을 불러오지 못한 생존자는 잃지 않고 그 자리에 두었다가 다음에 다시 불러옵니다.
- **Crash guard:** an error in a survivor's update no longer ends the game; it is logged instead.
  / **충돌 방지:** 생존자 업데이트 중 오류가 나도 게임이 끝나지 않고 기록만 남깁니다.
- **Vehicle tab:** each base car shows its own model, skin and paint. / **차량 탭:** 거점 차마다 실제 모델, 스킨, 색이
  그림으로 나옵니다.
- **Unreachable places:** a survivor is no longer sent again and again to a spot noted as one they cannot reach.
  / **못 가는 곳:** 갈 수 없다고 기록된 곳으로 같은 생존자를 계속 보내지 않습니다.

## Notes

- Works alongside Project Remnants (NPCFW) and ZombieBuddy agents (neither is required); its Byte Buddy is relocated.
- Contains no game code. Third-party licenses: `THIRD_PARTY_NOTICES.md`.

## Survivor grades / 생존자 등급

Every survivor is born with a grade. Higher grades are rarer, tougher, hit harder and know more.
모든 생존자는 등급을 갖고 태어납니다. 높을수록 드물고, 더 튼튼하고, 더 세게 치고, 아는 게 많습니다.

| Grade<br>등급 | Chance<br>확률 | Health<br>체력 | Damage taken<br>받는 피해 | Damage dealt<br>주는 피해 | Infection<br>감염 | Skills<br>기술 | Strength / Fitness<br>근력 / 체력 |
|---|---|---|---|---|---|---|---|
| **R** | 50% | +10% | — | — | normal / 보통 | 1 skill at level 6<br>기술 1개 6레벨 | as born / 그대로 |
| **SR** | 30% | +10% | −3% | — | normal / 보통 | 3 skills at 6<br>기술 3개 6레벨 | +3 |
| **SSR** | 15% | +20% | −10% | +5% | normal / 보통 | 5 skills at 6<br>기술 5개 6레벨 | +5 |
| **SSSR** | 4% | +50% | −20% | +10% | **immune / 면역** | 5 skills at 7<br>기술 5개 7레벨 | 9 |
| **UR** | 1% | +80% | −40% | +20% | **immune / 면역** | all 9 at 8<br>9개 전부 8레벨 | 10 |

- Skills are picked at random from carpentry, cooking, farming, first aid, electrical, metalworking, mechanics,
  tailoring and blacksmithing. / 기술은 목공, 요리, 농사, 응급치료, 전기, 금속세공, 정비, 재봉, 대장일 중에서
  무작위로 정해집니다.
- Health works as a real multiplier: every hit is scaled down as it lands, so +50% health means a hit does two
  thirds of its damage. / 체력 보너스는 실제 배율입니다. 맞을 때마다 피해가 줄어서, +50%면 한 방의 피해가 2/3이
  됩니다.
- The grade shows over their head (`[SSR]`) and on their card. All of these numbers can be changed in the sandbox
  options (P -Alive page). / 등급은 머리 위(`[SSR]`)와 생존자 카드에 표시됩니다. 이 수치는 모두 샌드박스 설정
  (P -Alive 페이지)에서 바꿀 수 있습니다.

New in 0.3.3, also in the sandbox options: / 0.3.3에서 추가, 샌드박스 설정에서 바꿀 수 있습니다:

| Grade<br>등급 | Attack speed<br>공격 속도 | Gun accuracy<br>사격 명중 | Holds ground<br>버티기 |
|---|---|---|---|
| **R** | — | — | — |
| **SR** | +3% | +3 points / 포인트 | — |
| **SSR** | +5% | +5 points / 포인트 | — |
| **SSSR** | +10% | +10 points / 포인트 | +10% |
| **UR** | +20% | +20 points / 포인트 | +20% |

- Every fight a survivor learns from adds 1% more to holding their ground, up to 15%. A bite still makes anyone run.
  / 싸움에서 배울 때마다 버티기가 1%씩, 최대 15%까지 오릅니다. 물리면 누구든 도망칩니다.

## AI chat model / AI 대화 모델

- The engine talks to **`qwen2.5:7b`** by default; that is the model `Install AI chat (optional).bat` downloads, and
  free-form chat expects it. / 엔진은 기본으로 **`qwen2.5:7b`**와 대화합니다. `Install AI chat (optional).bat`이
  받는 모델이 이것이고, 자유 대화는 이 모델이 있어야 동작합니다.
- **Using `qwen3:8b` instead** / **`qwen3:8b`를 쓰려면**
  1. `ollama pull qwen3:8b` (about 5.2 GB / 약 5.2GB)
  2. In `C:\Users\<you>\Zomboid\humannpc\llm.properties` change `model=qwen2.5:7b` to `model=qwen3:8b`, then restart
     the game. / `C:\Users\<사용자>\Zomboid\humannpc\llm.properties`의 `model=qwen2.5:7b`를 `model=qwen3:8b`로
     바꾸고 게임을 다시 켭니다.
- Things to know about `qwen3:8b` / `qwen3:8b` 주의사항
  - Heavier than 2.5: a graphics card with about 6 GB or more is comfortable; otherwise it runs on the CPU and
    answers slowly (a reply that takes over 90 s is skipped). / 2.5보다 무겁습니다. 그래픽 메모리 약 6GB 이상이
    편하고, 부족하면 CPU로 돌아 답이 느려집니다(90초 넘는 답은 건너뜁니다).
  - Its "thinking" mode is switched off by the engine, and any thinking text is removed, so lines come out clean.
    / 생각 모드는 엔진이 끄고, 섞여 온 생각 과정도 지워서 대사는 깔끔하게 나옵니다.
  - If only `qwen3:8b` is installed and `llm.properties` still says `qwen2.5:7b`, free-form chat simply stays
    silent (orders, events and lines all keep working). / `qwen3:8b`만 깔려 있는데 설정이 그대로 `qwen2.5:7b`면
    자유 대화만 조용히 대답하지 않습니다(명령, 이벤트, 대사는 그대로 동작).

## Optional: Codex add-on / 선택: 코덱스 애드온

`P-Alive-codex-<version>.zip` lets **one survivor of your choice** be run by Codex (OpenAI's coding AI, through
Codex on your PC) instead of the local AI: richer talk and decisions, and game actions you ask for in the chat.
`P-Alive-codex-<버전>.zip`을 설치하면 **고른 생존자 한 명**을 로컬 AI 대신 Codex(이 PC의 Codex)가 맡습니다.
대화와 판단이 더 풍부해지고, 채팅으로 부탁한 게임 행동을 직접 해 줍니다.

- Needs Windows and **Codex signed in**: the Codex app for Windows is enough (the bridge finds its `codex.exe` by
  itself), or the Codex CLI. Use counts against your own OpenAI / ChatGPT plan.
  GitHub Copilot CLI, if you have it, takes over when Codex hits its limit.
  Windows와 **로그인된 Codex**가 필요합니다. 윈도우용 Codex 앱만 있어도 되고(브리지가 앱의 `codex.exe`를 알아서 찾습니다),
  Codex CLI도 됩니다. 사용량은 본인 요금제에서 차감됩니다. GitHub Copilot CLI가 있으면 한도 초과 시 대신 씁니다.
- Install: extract the zip into your Zomboid user folder (`C:\Users\<you>\Zomboid\PRBrain\...`). The engine starts it by itself.
  설치: zip을 Zomboid 사용자 폴더에 풉니다(`C:\Users\<사용자>\Zomboid\PRBrain\...`). 엔진이 알아서 켭니다.
- In game: right-click a survivor, **Set as Codex**. **Only one survivor at a time**; designating another replaces the first.
  게임에서 생존자를 오른쪽 클릭해 **코덱스로 지정**. **한 번에 한 명만** 지정되고, 다른 사람을 지정하면 앞사람은 해제됩니다.
- A survivor can be set as Codex even without the add-on, but the Codex features only work while Codex (the add-on and a signed-in Codex) is running.
  애드온이 없어도 코덱스 지정은 되지만, 코덱스 기능은 Codex(애드온과 로그인된 Codex)가 켜져 있을 때만 동작합니다.
- What the Codex survivor sees is sent to OpenAI through your Codex. / 코덱스 생존자가 보는 내용은 본인의 Codex를 통해 OpenAI로 전송됩니다.

## SHA-256

- `P-Alive-engine-0.3.3.zip`: `016e7014a22bbdac855ca6d431bd138284de6367d58f466ea4ab69ede1480e2c`
- `P-Alive-codex-0.3.3.zip`: `b0f69fd689f65a69dc43a66e6bb34a87277fd823833d25aa60fdd6eaf77ae7ee`
- `P-Alive-Setup.exe`: `eccaef6f8c98ab985813af10db3558b18c6eafe898829b79d988b2cab714ece4`
