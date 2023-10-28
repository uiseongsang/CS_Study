# 인덱스
데이터 검색속도 향상을 위하여 테이블에 저장된 row를 식별 가능하도록 저장한 DB Object

## 인덱스의 장점
* 테이블을 조회하는 속도와 그에 따른 성능을 향상시킬 수 있다.
* 전반적인 시스템의 부하를 줄일 수 있다.

## 인덱스의 단점
* 인덱스를 관리하기 위해 DB의 약 10%에 해당하는 저장공간이 필요하다.

속도 향상을 위해 인덱스를 많이 만드는 것은 좋지 않다.
-> 전체적인 DB의 성능 부하를 초래한다 (Insert, Update, Delete시)

## 인덱스를 사용하면 좋은 경우
* 규모가 작지 않은 테이블
* Insert, Update, Delete가 자주 발생하지 않는 컬럼
* Join이나 Where, Order By가 자주 사용되는 컬럼
* 데이터의 중복도가 낮은 컬럼

## 인덱스의 종류

1. 클러스터형 인덱스 - 영어사전
   * 테이블당 한 개만 생성 가능
   * 테이블의 데이터를 지정된 컬럼에 대해 데이터를 재배열한다
2. 비클러스터형 인덱스 - 책 뒤에 색인에서 찾아보기
   * 테이블당 여러 개를 생성 가능

### 클러스터형 인덱스 VS 비클러스터형 인덱스
* 비클러스터형 인덱스는 클러스터형 인덱스보다 검색 속도는 느리지만, 데이터의 입력/수정/삭제는 더 빠르다
* 비클러스터형 인덱스는 테이블 당 여러개 존재 가능하지만 함부로 남용하면 오히려 시스템 성능을 떨어뜨린다