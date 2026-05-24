# ☕ 당신은 어떤 커피인가요?

8개의 짧은 질문으로 당신의 **MBTI**에 어울리는 커피 메뉴와 한국 브랜드를 찾아주는 작은 웹사이트.

> 걱정 마세요, 스타벅스는 추천하지 않을게요 😉

**🔗 라이브 데모 → [ai.tchung.org/coffee](https://ai.tchung.org/coffee/)**

---

## 무엇인가요?

MBTI 4개 축(E/I, S/N, T/F, J/P)에 대해 각각 2문항씩, 총 **8문항**으로 16개 MBTI 유형 중 하나를 산출하고 — 각 유형에 어울리는 **커피 메뉴 + 한국에서 만날 수 있는 비(非)스타벅스 브랜드**를 추천합니다.

- 8문항 진단 + 진행률 바
- 결과 카드: 커피 메뉴 + 추천 브랜드(📍) + 한 줄 태그라인 + 짧은 설명
- 다시 하기 / 공유 메뉴 — 데스크톱: 링크 복사 · iMessage · X · Threads · 이메일 / 모바일: 네이티브 share sheet (KakaoTalk 등 앱 통합)
- 단일 `index.html` (외부 라이브러리·빌드 과정 없음)
- 모바일 친화적 반응형 레이아웃
- 한국어 UI, 한글 가독성을 위한 시스템 폰트 스택과 `word-break: keep-all`

## 추천 목록

| MBTI | 메뉴 | 브랜드 |
|------|------|--------|
| INTJ | 에스프레소 | Blue Bottle (블루보틀) |
| INTP | 핸드드립 | Fritz Coffee Company (프릳츠) |
| ENTJ | 도피오 | illy (일리) |
| ENTP | 코르타도 | Paul Bassett (폴 바셋) |
| INFJ | 말차 라떼 | % Arabica (퍼센트 아라비카) |
| INFP | 라벤더 라떼 | Tous les Jours (뚜레쥬르) |
| ENFJ | 카라멜 마키아토 | Coffee Bean & Tea Leaf (커피빈) |
| ENFP | 딸기 라떼 | A Twosome Place (투썸플레이스) |
| ISTJ | 아메리카노 | Ediya Coffee (이디야커피) |
| ISFJ | 바닐라 라떼 | Paris Baguette (파리바게뜨) |
| ESTJ | 진한 아메리카노 | Tim Hortons (팀홀튼) |
| ESFJ | 카푸치노 | Dunkin' (던킨) |
| ISTP | 콜드 브루 | Mega Coffee (메가커피) |
| ISFP | 아이스 라떼 | Compose Coffee (컴포즈커피) |
| ESTP | 아포가토 | Tom N Toms (탐앤탐스) |
| ESFP | 시그니처 라떼 | Joe & The Juice (조앤더쥬스) |

## 어떻게 동작하나요?

각 질문은 MBTI의 한 축(E/I, S/N, T/F, J/P)에 매핑되어 있고, 선택한 옵션에 따라 해당 글자에 1점이 누적됩니다. 8문항이 끝나면 각 축에서 더 높은 점수를 받은 글자 4개를 조합해 유형을 결정합니다(동점이면 E·S·T·J 우선).

```
INTJ → COFFEES.INTJ → { icon, name, brand, tagline, desc }
```

질문이나 추천을 바꾸고 싶다면 `index.html`의 `QUESTIONS` / `COFFEES` 오브젝트만 수정하면 됩니다.

## 로컬에서 실행

별도 빌드 과정이 없습니다. 브라우저로 파일을 바로 열거나, 간단한 정적 서버를 띄우세요.

```bash
# 옵션 1 — 바로 열기
open index.html

# 옵션 2 — 정적 서버
python3 -m http.server 8000
# → http://localhost:8000
```

## 배포

이 사이트는 nginx로 정적 파일을 서빙합니다. 업데이트 시:

```bash
scp index.html root@<서버>:/var/www/html/coffee/index.html
```

## 기술 스택

- HTML / CSS / 바닐라 JavaScript
- 외부 라이브러리/프레임워크 없음
- 시스템 폰트 스택 (`Pretendard`, `Noto Sans KR`, `Apple SD Gothic Neo` 등)
- Footer 아이콘은 인라인 SVG (외부 이미지 없음)

## 참고

브랜드 추천은 재미를 위한 매칭으로, 각 브랜드와의 제휴/광고가 아닙니다. 매장·메뉴는 시점에 따라 달라질 수 있어요.

## 만든 사람

[Claude Opus 4.7](https://www.anthropic.com/news/claude-opus-4-7) 과 함께 만들었습니다.
