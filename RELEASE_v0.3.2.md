# P -Alive engine 0.3.2

Survivor engine for the **P -Alive** mod (Project Zomboid Build 42.21+, single player).
P -Alive 모드의 생존자 엔진입니다 (Project Zomboid Build 42.21 이상, 싱글플레이).

> **Updated 10-30: the game closed right after pressing Play? Download the installer again and run it once.**
> Steam's Play button starts the game through `ProjectZomboid64.exe`, which runs Java inside its own process. To load
> the engine, Java needs two of its own files (`java.dll`, `jli.dll`) next to that exe, and a stock game folder has
> them only in `jre64\bin`. Java then stopped with "Could not find agent library instrument" and the game closed at
> once; the `.bat` launch worked because it starts Java from `jre64\bin`. The new `P-Alive-Setup.exe` and
> `install.ps1` copy these two files from the game's own Java next to the exe (and remove them again on uninstall).
> Players with Project Remnants installed had them already, which is why it did not show for everyone.
> Run the installer again after a game update. The engine itself is unchanged.
>
> **10-30 업데이트: 플레이를 누르자마자 게임이 꺼졌다면 설치 파일을 다시 받아 한 번 실행하세요.**
> 스팀 플레이 버튼은 `ProjectZomboid64.exe`로 게임을 켜고, 이 실행기는 자바를 자기 안에서 돌립니다. 엔진을 불러오려면
> 자바 자신의 파일 두 개(`java.dll`, `jli.dll`)가 그 실행 파일 옆에 있어야 하는데, 원래 게임 폴더에는 `jre64\bin`에만
> 있습니다. 그래서 자바가 "Could not find agent library instrument"로 멈추고 게임이 바로 꺼졌습니다(`.bat`은 `jre64\bin`의
> 자바로 켜서 됐습니다). 새 `P-Alive-Setup.exe`와 `install.ps1`은 이 두 파일을 게임 자체 자바에서 실행 파일 옆으로
> 복사합니다(제거할 때 다시 지웁니다). Project Remnants를 설치한 분은 이미 그 파일이 있어서 문제가 없었습니다.
> 게임 업데이트 뒤에는 설치 파일을 다시 실행하세요. 엔진은 그대로입니다.

## Install / 설치

1. Subscribe to P -Alive on the Steam Workshop first. / 창작마당에서 P -Alive를 먼저 구독합니다.
2. Close the game. / 게임을 끕니다.
3. **Easiest: download `P-Alive-Setup.exe` below and run it.** It finds the game folder and sets everything up
   (it asks for administrator rights when the game is under Program Files). Windows may show "Windows protected your
   PC" because the file is not signed: click **More info → Run anyway**.
   **가장 쉬운 방법: 아래 `P-Alive-Setup.exe`를 내려받아 실행합니다.** 게임 폴더를 찾아 알아서 설치합니다(게임이
   Program Files 아래 있으면 관리자 권한을 묻습니다). 서명이 없는 파일이라 "Windows의 PC 보호" 창이 뜨면 **추가 정보 → 실행**을
   누르세요.
   Or the zip: download `P-Alive-engine-0.3.2.zip`, extract it and double-click **`Install P-Alive.bat`**.
   또는 zip: `P-Alive-engine-0.3.2.zip`을 풀고 **`Install P-Alive.bat`**을 더블클릭합니다.
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

- **Installer:** `P-Alive-Setup.exe` (one window, no scripts) and the starter described above.
  / **설치:** 창 하나로 끝나는 `P-Alive-Setup.exe`, 그리고 위의 시작 파일.
- **Walking into walls and walking in place:** a survivor counted as walking whenever the game said it "should be
  moving", even with no path, so it kept pushing at walls. It now counts as walking only with a path.
  / **벽으로 걸어가기, 제자리걷기:** 길이 없어도 "움직여야 함" 상태면 걷는 중으로 봐서 벽을 계속 밀었습니다. 이제 길이 있을
  때만 걷는 중으로 봅니다.
- **Routes:** survivors' paths in the game's own pathfinder now weigh walls, windows and fences; a low fence is not
  treated as a wall (it stays a place to fight at). Survivors stuck on the way are noticed and sent another way.
  / **길찾기:** 게임 길찾기 안에서 생존자의 길이 벽, 창문, 울타리를 따집니다. 낮은 울타리는 벽으로 보지 않습니다(싸우는
  자리로 남음). 가다가 막힌 생존자를 알아채고 다른 길로 보냅니다.
- **Waking and spawning:** a survivor that wakes up inside furniture (a bed square) steps out of it; new survivors
  appear in the same room first. / **깨어남, 나타남:** 가구(침대 칸) 안에서 깨면 밖으로 나옵니다. 새 생존자는 같은 방부터
  자리를 찾습니다.
- **AI chat:** lines read more like real people (a concrete detail, no pep talk), and Korean keeps one speech level
  (반말 or 존댓말) per line. / **AI 대화:** 구체적인 이야기를 하고 힘내자 같은 말을 줄였습니다. 한국어는 반말과 존댓말을 섞지
  않습니다.
- **Hooks:** every game hook is listed with its exact method and checked at start; one that does not fit this game
  version is left out and named in the diagnostics instead of breaking the game. Single hooks can be switched off in
  `Zomboid\humannpc\engine.properties` (see README.txt).
  / **훅:** 게임 훅마다 정확한 메서드를 적고 시작할 때 확인합니다. 게임 버전에 안 맞는 훅은 빼고 진단에 이름을 남깁니다.
  훅 하나씩 끌 수 있습니다(`Zomboid\humannpc\engine.properties`, README.txt 참고).
- **Bug reports:** "Copy diagnostics" now includes the frame time per survivor and the slowest P -Alive Lua files;
  when a survivor gets stuck, its last 30 s are kept in `Zomboid\humannpc-traces\` (on your PC only, newest 30).
  / **버그 제보:** "진단 복사"에 생존자당 프레임 시간과 가장 무거운 P -Alive Lua 파일이 들어갑니다. 생존자가 막히면 직전
  30초 기록이 `Zomboid\humannpc-traces\`에 남습니다(PC 안에만, 최근 30개).

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

- `P-Alive-engine-0.3.2.zip`: `e22f0cde35deebf12443fe6b9da1387032f0bce2b6363d1c91ddb8b4240df428`
- `P-Alive-codex-0.3.2.zip`: `b0f69fd689f65a69dc43a66e6bb34a87277fd823833d25aa60fdd6eaf77ae7ee`
- `P-Alive-Setup.exe`: `9c8cdf18822e445a73d04a14bf597da54cf8d5baede8eedb33bb0f0153e8dc23`
