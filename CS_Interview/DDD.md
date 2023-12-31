# DDD(Domain-Driven Design)에 대해 설명 해 주세요
DDD는 실제 업무에서 사건이 밟생하는 집합인 도메인을 중심으로 설계하는 방법입니다.

예시:

- 쇼핑몰을 예시로 들면, 구매자와 주문하는 도메인, 판매자가 관리하는 도메인 등이 있을 수 있습니다.
    
    이러한 도메인들이 서로 상호작용하며 설계하는 것이 도메인 주도 설계입니다.
    
- 도메인 주도 설계에서, 도메인은 기준에 따라 각각 분리 되어 있습니다. DDD에서는 같은 객체들이 존재할 수 있는데, 예를 들어 구매자의 입장에서는 (name, price)와 같은 객체 정보를 담지만, 판매자의 입장에서는 (color, size, madeCountry)등이 있을 수 있습니다. 즉, 상황(사용자 등)에 따라 객체의 역할이 바뀔 수 있는 것이 DDD입니다.
