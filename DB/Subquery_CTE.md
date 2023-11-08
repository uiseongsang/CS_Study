# Subquery VS CTEs(Common table expressions)
Subquery와 CTEs는 복합 SQL 쿼리를 작성하는데에 아주 유용한 툴이다.

# Subquery와 CTE 차이점

## Summary -> CTEs
* 복합한 쿼리를 읽기 쉽게 만들어 준다.
* 재귀 쿼리를 사용할 수 있다.

# Subquery
메인 쿼리내에 중첩 쿼리.

Suppose) 경영진이 모든 고객의 평균 연간 구매량 보다 높은 구매량을 가진 고객에게 할인을 제공

```
SELECT account_no, name
From customers
WHERE annual_purchases >
  (SELECT AVG(annual_purchases) FROM customers);
```

# CTEs
With "이름" AS 문법을 가지면서 정의된 이름이 지정된 결과의 집합입니다.

Suppose) 직원의 급여를 평균 급여와 해당 Role을 비교

```
WITH avg_salary AS (
  SELECT role, AVG(salary) AS average
  FROM employee
  GROUP BY role
)
SELECT employee.role, name, salary, avg_salary
FROM  employee
  JOIN avg_salary ON avg_salary.role = employee.role
ORDER BY role, name
```

# SubQuery VS CTEs
* SubQuery는 인라인으로 정의되는 반면 CTEs는 쿼리 앞에 정의된다
* CTEs는 항상 이름을 가지게 된다
* CTEs는 재귀로 사용될 수 있다
* CTEs는 읽기가 좋다
* CTEs는 쿼리 내에서 여러 번 사용할 수 있는 반면 SubQuery는 한 번만 사용할 수 있다
* SubQuery는 IN Or EXISTS 키워드와 함꼐 WHERE절에서 주로 사용하지만 CTEs에서는 적합하지 않다
* SubQuery를 사용하면 한 테이블에서 단일 데이터 조각을 선택하여 다른 테이블의 값을 업데이트할 수 있다

## SubQuery를 CTEs로 대체할 수 없는 경우
1. IN or EXISTS 키워드 사용할 때

Suppose) 은행이 당일의 모든 신용 거래 목록을 원하는 경우

```
SELECT account_no, tran_code, amount
FROM  daily_trans
WHERE tran_code IN
  (SELECT tran_code
   FROM transaction_types
   WHERE debit_creait = 1);
```
daily_trans: 은행의 그날의 모든 거래 내역

transaction_types: 거래의 종류 (debit(체크키드) or credit(신용카드))

debit_credit: 1: debit, 2: credit

SubQuery는 간결성, 목적의 명확성이 있을 때 사용하므로 IN 및 EXISTS SubQuery는 메인 쿼리와 함께 쓰일 때 그 의미가 명확하다. -> 코드 이해하기 쉽다

2. 다른 테이블을 업데이트하기 위한 한 테이블에서 단일 값을 선택하는데 사용될 때

```
UPDATE customer
SET suppory_person =
  (SELECT new_employee
   FROM reassignments
   WHERE old_employee = customer.support_person);
```

CTE를 사용하여 데이터를 조회하고 조작하는 것은 일반적이지만, CTEs 자체로는 데이터를 변경하는 데 사용되지는 않는다.

## 코드가 더 읽기 쉽다

<img width="900" alt="image" src="https://github.com/uiseongsang/CS_Study/assets/40707686/f013c397-cdcb-4a73-aa4d-1d9149a9b5e9">

<img width="464" alt="image" src="https://github.com/uiseongsang/CS_Study/assets/40707686/bf93e512-af05-47b4-9534-50702ac88432">

# 재귀 CTEs
재귀 쿼리를 사용하면 계층적 데이터를 탐색할 수 있다.



