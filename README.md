# 키친포스

## 미션 요구 사항
### 요구 사항1
- [x] 키친포스의 요구 사항을 README.md에 작성한다.
### 요구 사항2
- [x] 정리한 키친포스의 요구 사항을 토대로 테스트 코드를 작성한다.
    - 모든 Business Object에 대한 테스트 코드를 작성한다.
    - @SpringBootTest를 이용한 통합 테스트 코드 또는 @ExtendWith(MockitoExtension.class)를 이용한 단위 테스트 코드를 작성한다.
    - Controller에 대한 테스트 코드 작성은 권장하지만 필수는 아니다.

## 요구 사항
### 상품
- 상품의 이름과 가격을 입력해서 상품 등록을 할 수 있다.
    - 상품의 가격은 0원 이상이어야 한다.
- 전체 상품 리스트를 조회할 수 있다.

### 메뉴 그룹
- 메뉴 그룹 이름을 입력해서 메뉴 그룹을 등록할 수 있다.
- 전체 메뉴 그룹을 조회할 수 있다.

### 메뉴
- 메뉴의 이름, 가격, 메뉴 그룹 Id, 메뉴 상품을 이용해서 메뉴를 등록할 수 있다.
    - 메뉴의 가격은 0원 이상이어야 한다.
    - 메뉴는 하나의 그룹에 속해야 한다.
    - 메뉴는 상품을 1개 이상 가진다.
    - 메뉴의 가격은 메뉴에 포함된 상품의 가격 합 보다 클 수 없다.
- 전체 메뉴 그룹을 조회할 수 있다. 각 메뉴에 해당하는 상품들을 같이 조회한다.

### 테이블
- 테이블 그룹 Id와 손님 수를 이용해서 테이블을 추가할 수 있다.
- 테이블의 리스트를 조회할 수 있다.
- 테이블을 빈 테이블 상태를 수정할 수 있다.
    - 테이블이 테이블 그룹에 속한 상태라면 빈 테이블 상태를 수정할 수 없다.
    - 테이블의 상태가 'Cooking' 혹은 'meal'일 때는 테이블의 빈 테이블 상태를 수정할 수 없다.
- 테이블의 방문한 손님 수를 수정할 수 있다.
    - 테이블의 방문한 손님 수는 0보다 작을 수 없다.
    - 빈 테이블에 방문한 손님 수를 지정할 수 없다.

### 테이블 그룹
- 테이블 그룹을 만들 수 있다.
    - 2개 이상의 테이블을 그룹으로 만들 수 있다.
    - 테이블이 빈 상태가 아니거나 이미 그룹Id가 있으면 안된다.
- 테이블 그룹을 해제할 수 있다.
    - 테이블의 상태가 'Cooking' 혹은 'meal'일 때는 테이블의 그룹을 해제할 수 없다.

### 주문
- 테이블 Id와 주문 메뉴로 주문을 추가할 수 있다.
    - 1개 이상의 메뉴로 주문할 수 있다.
    - 빈 테이블에 주문을 추가할 수 없다.
    - 주문은 'Cooking' 상태로 등록된다.
- 주문 리스트를 조회할 수 있다.
- 주문의 상태를 수정할 수 있다.
    - 주문 상태가 Completion이면 상태를 수정할 수 없다.

## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
