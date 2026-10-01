---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled: the questions you can ask _now_ without guessing at answers you haven't heard yet. Ask the whole frontier in one round: number each question and give your recommended answer. Then wait for the user's answers before the next round.

Format a round like so:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Each round the user answers reshapes the tree: settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it; don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report; ask the rest of the frontier now. The _decisions_ are the user's: put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.

## Fork customization (yenalee04)

이 포크에서만 쓰는 규칙이다. 위 원본 규칙과 함께 지킨다. 바꾼 이유와 기록은 저장소 맨 위의 `FORK.md`에 있다.

- 질문과 추천 답은 한국어로, 쉬운 말로 쓴다. 사용자는 비개발자다.
- 이 대화 안에서 내가 만든 이름이나 번호(트랙 A/B, ①② 같은 것)를 설명 없이 쓰지 않는다. 사용자의 일상 도구 밖에 있는 개발 용어를 써야 하면 처음 나올 때 괄호로 한 줄 뜻을 붙인다.
- 우선순위나 작업 크기를 P0, S/M/L 같은 코드로 적지 않는다. "지금 바로", "작음/중간/큼"처럼 뜻이 바로 읽히는 말로 쓴다.
- 세션이 끝나면 정해진 결정 목록을 파일로 저장할지 묻는다. 채팅에만 남은 결정은 잊히기 쉽다.
