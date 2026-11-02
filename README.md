# P -Alive engine

The survivor engine for **P -Alive**, a Project Zomboid mod (Build 42.21, single player; later builds may show
errors). Download the installer from **[Releases](../../releases)**; the mod itself is on the Steam Workshop.

P -Alive 모드(프로젝트 좀보이드 Build 42.21, 싱글플레이. 이후 버전에서는 오류가 날 수 있습니다)의 생존자 엔진입니다.
설치 파일은 **[Releases](../../releases)**에서 내려받고, 모드는 스팀 창작마당에서 구독하세요.

## Install / 설치

1. Subscribe to **P -Alive** on the Steam Workshop. The engine comes inside the mod.
   창작마당에서 **P -Alive**를 먼저 구독합니다. 엔진은 모드 안에 같이 들어 있습니다.
2. Close the game, download **`P-Alive-Setup.exe`** from the latest release and run it. It adds the engine line to the
   game's launch settings, pointing at the engine inside the subscribed mod: from then on **the engine updates together
   with the mod**. Windows may warn because the file is not signed: **More info → Run anyway**.
   게임을 끄고 최신 릴리스에서 **`P-Alive-Setup.exe`**를 내려받아 실행합니다. 실행 설정에 엔진 한 줄을 추가하는데, 구독한
   모드 안의 엔진을 쓰도록 연결하므로 앞으로는 **모드가 업데이트될 때 엔진도 같이 업데이트**됩니다. 서명이 없는 파일이라
   경고가 뜨면 **추가 정보 → 실행**을 누르세요.
3. Enable **P -Alive** in the game's mod list. / 게임의 모드 목록에서 **P -Alive**를 켭니다.

The Setup also installs the optional AI chat (Ollama) and the Codex add-on, and uninstalls. Run it again after a game
update or a file integrity check. (The zip and .bat installers of 0.3.3 and older are no longer released.)
선택 기능인 AI 대화(Ollama)와 Codex 애드온 설치, 그리고 제거도 Setup에서 합니다. 게임 업데이트나 무결성 검사 뒤에는
Setup을 다시 실행하세요. (0.3.3 이하의 zip과 .bat 설치 파일은 이제 배포하지 않습니다.)

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

- The engine talks to **`qwen2.5:7b`** by default; that is the model the Setup's AI chat option downloads, and
  free-form chat expects it. / 엔진은 기본으로 **`qwen2.5:7b`**와 대화합니다. Setup의 AI 대화 설치가 받는 모델이
  이것이고, 자유 대화는 이 모델이 있어야 동작합니다.
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

The Codex add-on (installed from the Setup) lets **one survivor of your choice** be run by Codex (OpenAI's coding AI,
through Codex on your PC) instead of the local AI: richer talk and decisions, and game actions you ask for in the chat.
Codex 애드온(Setup에서 설치)을 넣으면 **고른 생존자 한 명**을 로컬 AI 대신 Codex(이 PC의 Codex)가 맡습니다.
대화와 판단이 더 풍부해지고, 채팅으로 부탁한 게임 행동을 직접 해 줍니다.

- Needs Windows and **Codex signed in**: the Codex app for Windows is enough (the bridge finds its `codex.exe` by
  itself), or the Codex CLI. Use counts against your own OpenAI / ChatGPT plan.
  GitHub Copilot CLI, if you have it, takes over when Codex hits its limit.
  Windows와 **로그인된 Codex**가 필요합니다. 윈도우용 Codex 앱만 있어도 되고(브리지가 앱의 `codex.exe`를 알아서 찾습니다),
  Codex CLI도 됩니다. 사용량은 본인 요금제에서 차감됩니다. GitHub Copilot CLI가 있으면 한도 초과 시 대신 씁니다.
- Install: choose the Codex add-on in the Setup; it puts the files into `C:\Users\<you>\Zomboid\PRBrain\`. The engine
  starts it by itself. / 설치: Setup에서 Codex 애드온을 고르면 `C:\Users\<사용자>\Zomboid\PRBrain\`에 넣습니다. 엔진이
  알아서 켭니다.
- In game: right-click a survivor, **Set as Codex**. **Only one survivor at a time**; designating another replaces the first.
  게임에서 생존자를 오른쪽 클릭해 **코덱스로 지정**. **한 번에 한 명만** 지정되고, 다른 사람을 지정하면 앞사람은 해제됩니다.
- A survivor can be set as Codex even without the add-on, but the Codex features only work while Codex (the add-on and a signed-in Codex) is running.
  애드온이 없어도 코덱스 지정은 되지만, 코덱스 기능은 Codex(애드온과 로그인된 Codex)가 켜져 있을 때만 동작합니다.
- What the Codex survivor sees is sent to OpenAI through your Codex. / 코덱스 생존자가 보는 내용은 본인의 Codex를 통해 OpenAI로 전송됩니다.

## Notes / 참고

- This repository only hosts the release downloads. / 이 저장소는 릴리스 파일만 올립니다.
- Each release lists the SHA-256 of its files so you can check the download. / 릴리스마다 파일의 SHA-256을 적어 둡니다.
- Third-party licenses are in [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) and [`licenses/`](licenses) in this
  repository. / 사용한 외부 라이브러리 라이선스는 이 저장소의 `THIRD_PARTY_NOTICES.md`와 `licenses/`에 있습니다.
- Bugs and feedback: the comments on the Workshop page. / 버그와 의견은 창작마당 페이지 댓글로 남겨 주세요.
