# Chord Trainer

피아노·기타 등 악기 연습을 위한 웹 앱. 일정 시간마다 랜덤으로 코드 또는 음계가 화면에 표시되고, 연주자는 표시된 내용을 보며 연습한다.

- 서버 불필요 — 단일 HTML 파일
- 외부 라이브러리 없음
- 모바일(iOS / Android) 지원

---

## 화면 구성

상단 탭으로 **Chords(코드)** 와 **Scales(음계)** 두 가지 모드를 전환한다.  
하단 컨트롤: **Skip**(현재 항목 건너뜀) / **Start · Pause · Resume**  
우상단 **⚙** 버튼으로 설정 패널을 열고 닫는다.

---

## Chords 모드

코드명이 화면 중앙에 크게 표시된다. 타이머가 끝나면 다음 코드로 넘어간다.

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

| 설정 | 설명 |
|---|---|
| **Interval** | 전환 시간. 2 · 3 · 4 · 5 · 8 · 10 · 15 · 20 · 30초 프리셋 또는 직접 입력(1~300초) |
| **Notation** | ♯ Sharps / ♭ Flats 선택 |
| **Quick Key Select** | 조성을 선택하면 해당 음계의 루트음만 자동으로 필터된다. 장조와 나란한조(단조)를 하나로 묶어 표시 (예: G / Em) |
| **Root Notes** | 12개 루트음을 개별 선택. All / None 버튼으로 일괄 조작 가능 |

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
