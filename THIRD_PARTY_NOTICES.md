# Third-party notices

## Generative Agents

HumanNPC's survivor memory (`src/main/java/humannpc/mind/MemoryStream.java`) and reflection / daily planning
(`src/main/java/humannpc/mind/NpcMind.java`) contain code and prompt text ported and modified from:

- **Generative Agents: Interactive Simulacra of Human Behavior**
  https://github.com/joonspk-research/generative_agents
  Copyright 2023 Joon Sung Park and contributors
- Licensed under the Apache License, Version 2.0. The full license text is in
  [`licenses/generative_agents-LICENSE.txt`](licenses/generative_agents-LICENSE.txt).

Files used as the source of the port:

- `reverie/backend_server/persona/memory_structures/associative_memory.py`
- `reverie/backend_server/persona/cognitive_modules/retrieve.py`
- `reverie/backend_server/persona/cognitive_modules/reflect.py`
- `reverie/backend_server/persona/prompt_template/v2/poignancy_event_v1.txt`, `poignancy_chat_v1.txt`,
  `generate_focal_pt_v1.txt`, `insight_and_evidence_v1.txt`, `daily_planning_v6.txt`

The changes made are listed at the top of each ported file.

## Design references (no code used)

- EchoColony (https://github.com/CarlosNahuelcoy/EchoColony): the idea of talking with a colonist whose
  answers reflect their mood, health and history, and whose words affect the game. HumanNPC's player chat is its
  own implementation; no EchoColony code is included.

## Byte Buddy and ASM (bundled in the jar)

- **Byte Buddy** (https://bytebuddy.net), Copyright Rafael Winterhalter, Apache License 2.0. Bundled inside the
  engine jar under the relocated package `humannpc.shaded.net.bytebuddy`; its license and NOTICE are kept in the
  jar at `META-INF/LICENSE` and `META-INF/NOTICE`.
- **ASM** (https://asm.ow2.io, `asm` and `asm-commons`), Copyright INRIA, France Telecom, BSD 3-Clause License.
  The engine rewrites the game's classes with it; bundled under the relocated package
  `humannpc.shaded.org.objectweb.asm`; the license text is in the jar at `META-INF/licenses/ASM`.
