# SQLD 정리

SQLD 공부 내용을 주제별로 정리합니다.

## 목차

- [정규화](normalization.md)

## 기본 SQL 예시

```sql
SELECT department_id, COUNT(*) AS employee_count
FROM employees
GROUP BY department_id
HAVING COUNT(*) >= 2;
```

**기억할 점:** `WHERE`는 그룹화 전 행을 필터링하고, `HAVING`은 그룹화한 결과를 필터링합니다.

!!! question "스스로 확인"
    집계 함수로 필터링해야 할 때 `WHERE` 대신 `HAVING`을 사용하는 이유를 설명해 보세요.
