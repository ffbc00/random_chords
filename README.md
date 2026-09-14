# Chord Trainer

피아노·기타 등 악기 연습을 위한 웹 앱. 일정 시간마다 랜덤으로 코드 또는 음계가 화면에 표시되고, 연주자는 표시된 내용을 보며 연습한다.

- 서버 불필요 — 단일 HTML 파일
- 외부 라이브러리 없음
- 모바일(iOS / Android) 지원
- 한국어 / English 지원

---

## 화면 구성

상단 탭으로 **Chords(코드)** 와 **Scales(음계)** 를 전환한다.

```
[ Chords ] [ Scales ]
```

코드를 어떤 기준으로 뽑을지는 화면이 아니라 설정 패널의 **Chord Selection(코드 선택 방식)** 에서 고른다.

```
⚙ 설정 › Chord Selection
  ( By Chord Type | By Chord Function )
```

하단 컨트롤: **Skip**(현재 항목 건너뜀) / **Start · Pause · Resume**  
우상단 **⚙** 버튼으로 설정 패널을 열고 닫는다. 설정 패널은 현재 모드에 해당하는 항목만 보여준다.

---

## Chords — By Chord Type (코드 유형별)

기본값이다. 조성과 무관하게 루트음 × 코드 타입 조합에서 무작위로 뽑는다. 코드명이 화면 중앙에 크게 표시된다.

### 설정 — Chord Types

네 가지 카테고리를 선택한다. 카테고리 헤더를 누르면 전체를 켜거나 끄고, **▼** 를 눌러 펼치면 개별 코드 타입을 선택할 수 있다.

| 카테고리 | 포함 코드 |
|---|---|
| **Triads** | maj · m · aug · dim · sus2 · sus4 |
| **7th Chords** | M7 · m7 · 7 · m7♭5 · dim7 · mM7 · aug7 · augM7 · 7sus4 |
| **Extended** | M9 · m9 · 9 · M11 · m11 · 11 · M13 · m13 · 13 · add9 · madd9 · 6 · m6 · 6/9 |
| **Altered** | 7♭9 · 7♯9 · 7♭5 · 7♯5 · 7♯11 · 7♭13 · 7♭9♭5 · 7♯9♯5 · alt |

헤더 왼쪽 색상 바로 선택 상태를 확인할 수 있다.  
보라색 = 전체 선택 · 노란색 = 일부 선택 · 없음 = 전체 해제

---

## Chords — By Chord Function (코드 기능별)

키를 하나 정해두고, **그 키에서 실제로 기능하는 코드만** 뽑는다. 코드명과 함께 로마숫자 기능 표기가 표시된다.

```
        KEY: C MAJOR
        Am7 → D7
        ii7–V7 / V
```

### 설정 — Key

12개 루트음 중 하나를 고르고 **Major / Minor** 를 선택한다. 나란한조라도 기능이 다르므로 장조·단조를 분리해 총 24개 키를 지원한다. 키를 고르면 표기법(♯/♭)이 자동으로 맞춰진다.

각 버튼은 그 조성의 관용 표기로 고정 표시된다. 장조는 `D♭ E♭ G♭ A♭ B♭`, 단조는 `C♯ E♭ F♯ G♯ B♭` 로, 어떤 키를 골라도 목록이 바뀌지 않는다.

### 설정 — Chord Functions

기능별로 7개 그룹을 제공한다. 헤더를 누르면 그룹 전체를 켜고 끄며, **▼** 로 펼치면 개별 기능을 선택할 수 있다. 기본값은 **Diatonic 만 켜짐**.

| 그룹 | 설명 | C major 예시 |
|---|---|---|
| **Diatonic** | 그 조의 기본 화음 | CM7 · Dm7 · Em7 · FM7 · G7 · Am7 · Bm7♭5 |
| **Secondary Dominants** | 다이어토닉 코드를 일시적 토닉으로 삼는 도미넌트 | A7 · B7 · C7 · D7 · E7 |
| **Related II–V** | 세컨더리 도미넌트 앞에 붙는 ii7 | Am7 → D7 · Gm7 → C7 |
| **Substitute Dominants** | 트라이톤 대리 도미넌트 | D♭7 · E♭7 · G♭7 · A♭7 · B♭7 |
| **Modal Interchange** | 동주단조 등에서 빌려온 차용화음 | Cm7 · E♭M7 · A♭M7 · B♭7 · D♭M7 |
| **Diminished** | 패싱·리딩톤 디미니시드 | C♯dim7 · F♯dim7 · Bdim7 |
| **Sus & Cadential** | sus 계열 | Csus2 · Gsus4 · G7sus4 |

차용화음과 대리 도미넌트는 조표와 무관하게 제 표기를 지킨다 — C major의 ♭III은 `D♯M7`이 아니라 `E♭M7`.

### 설정 — Voicing

**3화음** 과 **7화음** 을 각각 켜고 끈다. 둘 다 켜면 두 형태가 모두 출제된다. 최소 하나는 켜져 있어야 하므로 마지막 하나는 꺼지지 않는다.

설정은 하나뿐이며 모든 기능 그룹에 함께 적용된다. 그룹마다 따로 지정하지는 않는다.

> 코드 기능별 모드에서는 조성이 표기법을 결정하므로 ♯/♭ 수동 선택은 표시되지 않는다.

### 단조의 Diatonic — Scale

Minor 키에서는 Diatonic 그룹 안에 **Natural / Harmonic / Melodic** 선택이 추가된다. 복수 선택이 가능하며 기본값은 Harmonic. 최소 하나는 켜져 있어야 한다.

| A minor | 구성 |
|---|---|
| Natural | Am7 · Bm7♭5 · CM7 · Dm7 · Em7 · FM7 · G7 |
| Harmonic | AmM7 · Bm7♭5 · CaugM7 · Dm7 · **E7** · FM7 · **G♯dim7** |
| Melodic | AmM7 · Bm7 · CaugM7 · **D7** · E7 · F♯m7♭5 · G♯m7♭5 |

음계를 추가로 켜면, 새로 들어오는 항목은 그룹의 현재 전체 활성 여부를 따른다. 그룹이 꺼져 있으면 꺼진 채로, 전부 켜져 있으면 켜진 채로 추가된다.

#### 중복 제거

세 음계는 서로 겹치므로, 여러 개를 켜면 같은 코드가 여러 번 나올 수 있다. 겹치는 것은 하나만 남기고 서로 다른 것만 따로 표시한다. 판정 기준은 **현재 켜져 있는 보이싱**이다.

자연 + 화성을 켠 경우 (3화음):

| 음도 | 자연 · 화성 | 표시 |
|---|---|---|
| IV | iv · iv | **iv** — 같으므로 하나 |
| V | v · V | **v · V** — 다르므로 둘 다 |
| III | ♭III · ♭III+ | **♭III · ♭III+** |
| I · II · VI | 각각 동일 | **i · ii° · ♭VI** |

3화음만 켜면 자연 `i` 와 화성 `i` 는 둘 다 `Am` 이라 하나로 합쳐지지만, 7화음에서는 `i7` / `i(M7)` 로 갈리므로 따로 표시된다. 그래서 **7화음이 켜져 있으면 이 그룹의 칩이 7화음 로마숫자로 표시된다** — `i7` · `i(M7)` · `vii°7` · `viiø7` 처럼 구별이 필요하기 때문이다.

세 음계를 모두 켰을 때 결과:

| 보이싱 | 코드 수 |
|---|---|
| 3화음 | 21 → **13** |
| 7화음 | 21 → **15** |
| 둘 다 | 42 → **28** |

### Related II–V — Display

**As Pair** 는 `Am7 → D7` 처럼 두 코드를 한 화면에 묶어 보여주고, **Separate** 는 각각을 독립된 항목으로 흩어서 낸다.

### Show Function

로마숫자 기능 표기를 켜고 끈다. 끄면 코드명만 보이므로 "이게 이 조에서 무슨 기능이지?"를 스스로 답하는 훈련이 된다.

#### 로마숫자 표기 규칙

대소문자는 **밑에 깔린 3화음의 성질**로 정해진다.

| 성질 | 표기 | 예 |
|---|---|---|
| 장3화음 | 대문자 | I · IV · V · V7 |
| 단3화음 | 소문자 | ii · vi · ii7 |
| 감3화음 | 소문자 + ° / ø | vii° · iiø7 |
| 증3화음 | 대문자 + + | ♭III+ · ♭III+M7 |

7화음은 3화음을 따른다 — `V7` 은 장3화음 위 단7도라 대문자, `iiø7` 은 감3화음이라 소문자다.

sus 코드는 3음이 없어 장단 구분이 없으므로 장조·단조 모두 대문자로 적는다 (`Isus4` · `IVsus4` · `V7sus4`).

---

## Scales 모드

루트음(크게)과 음계명이 함께 표시된다. 예: **G** / *Dorian*

### Show Notes

설정 패널 하단 **Show Notes** 토글을 On으로 설정하면 구성음이 함께 표시된다.

```
G
Dorian
G · A · B♭ · C · D · E · F
```

### 설정 — Scale Types

두 가지 카테고리를 선택한다. 코드 모드와 동일하게 헤더 전체 토글 및 개별 선택이 가능하다.

| 카테고리 | 포함 음계 |
|---|---|
| **Basic** | Major · Natural Minor · Harmonic Minor · Melodic Minor |
| **Church Modes** | Ionian · Dorian · Phrygian · Lydian · Mixolydian · Aeolian · Locrian |

> Major = Ionian, Natural Minor = Aeolian 으로 음이 같지만, 기본 음계로서의 명칭과 교회 모드로서의 명칭을 구분하기 위해 양쪽 카테고리에 모두 포함되어 있다.

---

## 공통 설정

| 설정 | 적용 모드 |
|---|---|
| **Language** — 한국어 / English. 최초 실행 시 브라우저 언어를 따른다 | 전체 |
| **Interval** — 전환 시간. 2 · 3 · 4 · 5 · 8 · 10 · 15 · 20 · 30초 프리셋 또는 직접 입력(1~300초) | 전체 |
| **Chord Selection** — 코드를 뽑는 기준. By Chord Type(기본) / By Chord Function | Chords |
| **Notation** — ♯ Sharps / ♭ Flats 선택 | By Chord Type · Scales |
| **Root Notes** — 12개 루트음을 개별 선택. All / None 으로 일괄 조작 | By Chord Type · Scales |

설정 패널 하단에 현재 선택된 풀(pool)의 항목 수가 표시된다.

---

## 접속 방법

### GitHub Pages (권장)
```
https://YOUR_USERNAME.github.io/random-chords/
```
iOS Safari에서 열고 **공유 → 홈 화면에 추가** 하면 앱처럼 사용할 수 있다.

### 로컬 파일
`index.html` 파일을 브라우저로 직접 열면 된다.
