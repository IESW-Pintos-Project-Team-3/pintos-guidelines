# Pintos C 코딩 스타일 가이드

Pintos는 **C 언어 기반 프로젝트**입니다.  
모든 팀원은 아래 가이드에 따라 **일관성**과 **가독성**을 최우선으로 코드를 작성해 주세요.

---

## 1. 📏 들여쓰기 & 중괄호

- **들여쓰기:** 4칸 스페이스 사용
- **중괄호 `{}`:** 항상 사용 (한 줄짜리 블록도 예외 없음)

```c
void example_function(int x) {
    if (x > 0) {
        do_something();
    } else {
        do_something_else();
    }
}
```

---

## 2. 🧱 함수 간 줄바꿈

- 함수 정의는 **두 줄 간격**으로 구분

```c
void first_function(void) {
    // ...
}


void second_function(void) {
    // ...
}
```

---

## 3. 🧾 네이밍 규칙

| 항목       | 규칙                  | 예시                             |
| ---------- | --------------------- | -------------------------------- |
| 함수 이름  | snake_case            | `init_thread()`, `load_avg()`    |
| 변수 이름  | snake_case            | `thread_id`, `tick_count`        |
| 구조체 이름 | PascalCase            | `struct Thread`, `struct Lock`   |
| 상수       | 대문자 + 언더바       | `MAX_THREADS`, `DEFAULT_TICK`    |

---

## 4. 🔒 주석 작성

- **함수 위:** 간단한 설명 주석 작성

```c
/* Sleeps for T ticks. */
void timer_sleep(int64_t ticks) {
    // 구현부
}
```

- **구현부:** 한 줄 위 또는 옆에 설명 주석 작성

```c
while (!list_empty(&wait_list)) {
    struct thread *t = list_entry(...); // 대기 중인 쓰레드
}
```

---

## 5. 🪛 매직 넘버 사용 금지

- 의미 있는 **매크로/상수**로 치환

```c
#define ALARM_PRIORITY 5

if (priority > ALARM_PRIORITY) {
    // ...
}
```

---

## 6. 📚 헤더 파일 구조

- include guard, 함수 선언, 설명 주석 등 기본 구조 준수

```c
#ifndef THREAD_H
#define THREAD_H

/* 설명 */

void init_thread(void);

#endif /* THREAD_H */
```

---

## 7. 🎯 스타일 가이드 적용 방법

- `.clang-format` 등 자동화 도구 사용도 가능하지만,  
  **리뷰 & PR 과정에서 팀원 간 합의로 스타일을 맞추는 방식**을 권장합니다.
- 기준이 다를 경우, 본 `coding-style.md`를 공식 규칙으로 삼아주세요.

---

> **참고:**  
> 스타일 가이드 위반 시, 리뷰어가 수정 요청을 할 수 있습니다.  
> 모두가 읽기 쉽고 유지보수하기 좋은 코드를 위해 가이드 준수를 부탁드립니다.

