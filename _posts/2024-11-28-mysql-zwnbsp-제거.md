---
title: "[Mysql] mysql ZWNBSP 문자열 제거하기"
categories:
  - junk
tags:
  - sql
  - mysql
  - query
toc: true
toc_sticky: true
---
  
> 요즘 cursor ai 에디터랑 같이 개발하고있는데.. 왠만한 구글 검색보다 똑똑한듯?   
> 아무리 찾아도 안나왔던 mysql ZWNBSP 제거하는 방법을 cursor ai가 알려줬다

![img.png](/assets/images/junk/img.png)

어느날 데이터베이스에 이상한 문자열이 들어가있어서 xml 파싱이 안되는 이슈가 발생   
후.. 아직도 xml 파싱을 하고있다니 우리회사 참 대단해 👍   
아무튼 별짓을 해도 계속해서 인코딩 이슈로 파싱이 안되서 데이터를 까봤는데   
진짜 요상한 문자열이 들어가있었다   
이제 어디서 들어갔는지를 찾아야하는데.. 너무구ㅣ찮ㅠ   

구글에서 구글링을 아무리해도 안나오고    
chat GPT한테도 물어봤는데 구글이랑 똑같이 대답하길래   
`cursor ai`한테 물어봤는데 우리 똑쟁이가 정답을 알려줬다

## Mysql ZWNBSP (Zero Width No-Break Space, U+FEFF) 제거하기
```mysql
UPDATE your_table
SET your_column = REPLACE(your_column, UNHEX('EFBBBF'), '')
WHERE your_column LIKE CONCAT('%', UNHEX('EFBBBF'), '%');
```

* ZWNBSP의 UTF-8 인코딩은 hex값으로 EF BB BF
* UNHEX('EFBBBF')는 이 hex값을 실제 문자로 변환
* REPLACE 함수를 사용해 해당 문자를 빈 문자열로 대체
* WHERE 절에서 LIKE를 사용해 해당 문자가 포함된 레코드만 찾아서 업데이트

요렇게 하니깐 깔-끔하게 데이터베이스에서 ZWNBSP 문자열이 제거되었음   
이제 왜 생겼는지 찾아보러가야함 ==333
