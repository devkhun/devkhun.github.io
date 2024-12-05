---
title: "[Mysql] mysql 조건절을 이용하여 질의 조회"
categories:
  - junk
tags:
  - sql
  - mysql
  - query
toc: true
toc_sticky: true
---

> 지금 다니는 회사 직전에서는 쿼리를 많이 썼는데,, 지금은 쓰는 기회가 적어 쿼리의 신에서 내려옴  
> 나 원래 쿼리의 신이였는데 헤헤,,ㅠ0ㅠ  
> 아주 기본적인 case ~ when 절 사용해보기!

## 질의절에 case ~ when 걸어서 조건에 맞는 데이터만 추출하기
```mysql
select
    goodsNo as '상품코드',
    CASE detailInfoDeliveryFl
        WHEN 'no' THEN 'N'
        WHEN 'selection' THEN b.column_name
        WHEN 'direct' THEN g.column_name
        END as '배송안내선택',
    CASE detailInfoExchangeFl
        WHEN 'no' THEN 'N'
        WHEN 'selection' THEN b2.column_name
        WHEN 'direct' THEN g.column_name2
        END as '교환/환불안내선택'
from {my_table} as g
 left join {my_table2} b on g.id = b.id
 left join {my_table3} b2 on g.id = b2.id
```

* case ~ when 절을 이용하여 깔끔하게 조건에 맞는 값 추출 가능 !
