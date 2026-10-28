# P -Alive engine 0.3.1

Survivor engine for the **P -Alive** mod (Project Zomboid Build 42.21+, single player).
P -Alive 모드의 생존자 엔진입니다 (Project Zomboid Build 42.21 이상, 싱글플레이).

## Install / 설치

1. Subscribe to P -Alive on the Steam Workshop first. The engine comes inside the mod.
   창작마당에서 P -Alive를 먼저 구독합니다. 엔진은 모드 안에 같이 들어 있습니다.
2. Download `P-Alive-engine-0.3.1.zip` below and extract it. / 아래 zip을 내려받아 압축을 풉니다.
3. Close the game and double-click **`Install P-Alive.bat`**. It adds the engine line to the launch settings, after
   any other agent, pointing at the engine inside the subscribed mod: from then on **the engine updates with the
   mod**. Not subscribed yet: it copies this zip's engine into the game folder (run it again after subscribing).
   Changed files are backed up once as `.before-palive.bak`.
   게임을 끈 상태에서 **`Install P-Alive.bat`**을 더블클릭합니다. 실행 설정의 다른 에이전트 뒤에 엔진 한 줄을 추가하고,
   구독한 모드 안의 엔진을 쓰도록 연결해서 앞으로는 **모드가 업데이트될 때 엔진도 같이 업데이트**됩니다. 구독 전이면 zip의
   엔진을 게임 폴더에 넣습니다(구독한 뒤 다시 실행하세요). 바꾸는 파일은 처음 한 번 `.before-palive.bak`으로 백업됩니다.
4. Enable P -Alive in the mod list. / 모드 목록에서 P -Alive를 켭니다.
5. Optional: **`Install AI chat (optional).bat`** sets up Ollama and the chat model (about 4.7 GB) for free-form chat.
   선택: 자유 대화용 Ollama와 대화 모델(약 4.7GB)을 설치합니다.

**Installed 0.1.0? Run `Install P-Alive.bat` once more.** After that the engine updates by itself with the mod.
**0.1.0을 설치했다면 `Install P-Alive.bat`을 한 번만 다시 실행하세요.** 그 뒤로는 엔진이 모드와 함께 자동으로 업데이트됩니다.

Run the installer again after a game update or file integrity check. `Uninstall P-Alive.bat` removes it.
게임 업데이트나 무결성 검사 뒤에는 설치 파일을 다시 실행하세요. 제거는 `Uninstall P-Alive.bat`.

## What's new / 바뀐 점

- **Survivors work fully without Remnants.** They no longer use the player's keyboard, mouse cursor, aim reticle or
  line of sight (the player could turn invisible). / **Remnants 없이도 생존자가 온전히 동작합니다.** 플레이어의 키보드,
  마우스 커서, 조준선, 시야를 더 이상 쓰지 않습니다(플레이어가 투명해지던 문제).
- **A fix for the game's own Lua bridge:** a failed call to an overloaded Java method put a pooled object back twice,
  and a few seconds later any mod could crash with *"Cannot assign field callFrame because a is null"*. The engine
  now keeps it once and logs which Lua line made the bad call. / **게임 Lua 연결부의 버그 수정:** 잘못된 Java 호출
  하나가 몇 초 뒤 아무 모드에서나 *"Cannot assign field callFrame"* 오류를 냈습니다. 이제 막고, 원인 줄을 로그에 남깁니다.
- **Survivor saves have backups:** if the save cannot be read the engine falls back to the last good copy and three
  daily backups (one per 24 game hours), keeps the broken file aside, and tells you in game.
  / **생존자 저장 백업:** 저장을 못 읽으면 직전 저장과 하루 단위 백업 3개(게임 시간 24시간마다)에서 되살리고,
  깨진 파일은 따로 남기며, 게임 안에서 알려 줍니다.
- **Fences:** zombies behind a fence that holds (tall, not bending or breaking) are left alone, however many; at a low
  fence survivors wait and hit them as they climb over. No more freezing in front of a fence, and zombies outside a
  fence no longer make survivors retreat from one inside.
  / **울타리:** 버티는 울타리(높고, 휘거나 부서지지 않는) 너머 좀비는 몇 마리든 둡니다. 낮은 울타리에서는 넘어오는 좀비를
  기다렸다 칩니다. 울타리 앞에서 얼어붙지 않고, 울타리 밖 무리 때문에 안쪽 한 마리를 두고 물러나지 않습니다.
- **Combat timing** no longer runs faster with more survivors (it ran N times faster with N survivors).
  / 생존자가 많을수록 전투 시간이 빨라지던 문제를 고쳤습니다.
- **Diagnostics:** a notice at game start when the engine is missing, too old or partly not hooked, and "Copy
  diagnostics" for bug reports. / **진단:** 엔진이 없거나 오래됐거나 일부가 안 걸리면 게임 시작 때 알려 주고,
  제보용 "진단 복사"가 있습니다.

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

- `P-Alive-engine-0.3.1.zip`: `db4ebf6a4fd28ad858b20fa61e6d8969078242ac9ea3669da538c59260d76bdd`
- `P-Alive-codex-0.3.1.zip`: `b0f69fd689f65a69dc43a66e6bb34a87277fd823833d25aa60fdd6eaf77ae7ee`
