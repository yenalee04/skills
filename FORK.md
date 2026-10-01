# Fork 기록 (yenalee04/skills)

[mattpocock/skills](https://github.com/mattpocock/skills)를 포크해 내 업무에 맞게 조금 고친 저장소다.

| | |
|---|---|
| 원본 | https://github.com/mattpocock/skills (MIT, `LICENSE` 참고) |
| 포크한 날 | 2026-10-01 |
| 포크 시점 원본 커밋 | `d81f3a1` (Merge pull request #1120, release/v1.3) |

## 바꾼 것

원본 파일은 되도록 건드리지 않는다. 꼭 바꿔야 하면 파일 **맨 끝에** 단락을 붙인다. 원본이 바뀐 자리와 겹치지 않아야 Sync fork 할 때 충돌이 적다.

| 파일 | 바꾼 내용 | 이유 |
|---|---|---|
| `skills/productivity/grilling/SKILL.md` | 맨 끝에 `## Fork customization (yenalee04)` 단락 추가: 한국어·쉬운 말, 내부 번호·코드 금지, 끝나면 결정 목록을 파일로 남길지 묻기 | 원본은 영어 개발자 기준이다. 나는 비개발자라 개발 용어와 압축 코드가 섞이면 질문을 이해하지 못한 채 답하게 된다. |
| `FORK.md` (이 파일) | 새로 만듦 | 원본 주소, 바꾼 것, 업데이트 받는 법을 한곳에 남기기 위해 |

## 원본 업데이트 받기

**방법 1. 깃허브 웹 (가장 쉬움)**
1. https://github.com/yenalee04/skills 에 들어간다.
2. 파일 목록 위의 **Sync fork** 버튼 → **Update branch**.
3. 충돌이 나면 깃허브가 알려준다. 그때는 방법 2로 내 PC에서 해결한다.
4. 받은 뒤 내 PC 폴더에서 `git pull`.

**방법 2. 내 PC에서**
```
git fetch upstream
git merge upstream/main
git push origin main
```

받은 뒤 확인할 것: `grilling/SKILL.md` 맨 끝의 `## Fork customization (yenalee04)` 단락이 그대로 있는지.

## 내 Claude에 반영하기

2026-10-01부터 내 Claude는 공식 마켓 버전 대신 이 포크를 플러그인으로 쓴다(마켓 이름 `mattpocock`, 출처 `yenalee04/skills`). 깃허브 포크가 바뀌면 아래 두 줄로 Claude에 반영하고, Claude를 다시 연다.

```
claude plugin marketplace update mattpocock
claude plugin update mattpocock-skills@mattpocock
```

- 미확인: 버전 번호(1.2.3)가 그대로일 때도 `plugin update`가 새 내용을 받아오는지. 처음 실제 업데이트 때 설치본의 `grilling/SKILL.md`를 열어 확인한다.
- 공식 버전으로 되돌리기: `claude plugin uninstall mattpocock-skills@mattpocock` 후 `claude plugin install mattpocock-skills@claude-plugins-official`.

## 지킬 것

- **공개 저장소다.** 회사 이름, 브랜드, SKU, 숫자 등 회사 정보는 넣지 않는다.
- 원본(`upstream`)에는 push하지 않는다. 내 PC 설정에서 push 주소를 막아 두었다(`NO_PUSH_TO_UPSTREAM`).
- 원본에 내 수정을 제안하고 싶으면 깃허브에서 원본으로 PR을 연다. 받아줄지는 원본 주인이 정한다.
