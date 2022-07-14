## Mybatis
### SQL MAPPER ( XML 형식 ) 기본형식
>  ##### CDATA DI 받아야함
``` xml
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="crprtnCard">

    <select id="crprtnCardList" parameterType="hashmap" resultType="com.erp.dev.crprtncard.vo.ErpCrprtnCardVo">
        <![CDATA[
	        SELECT
	        	CRPRTN_CARD_SQ,
				CRPRTN_CARD_BANK,
				CRPRTN_CARD_NUM,
				CRPRTN_CARD_USR_NM,
				CRPRTN_CARD_USR_DEPT,
				CRPRTN_CARD_USR_PST,
				CRPRTN_CARD_USE_DT,
				CRPRTN_CARD_CNT,
				CRPRTN_CARD_USE_PRC,
				CRPRTN_CARD_NOTE
	        FROM 
	        	est_eep_db.tb_eep_crprtn_card_m
        ]]>
    </select>

</mapper>

```
### MyBatis에서 parameterType 과 resultType
>  ##### resultType : select 로 선택된 데이터를 담는 그릇
>  ##### parameterType : 자바에서 어떤 타입으로 설정 할 것인지를 인지시켜주는 타입
``` xml
<select id="crprtnCardList" parameterType="hashmap" resultType="com.erp.dev.crprtncard.vo.ErpCrprtnCardVo">
```

### @Resource 와 @Autowired
>  ##### 내가 만든 java 클래스의 DI 해주는 어노테이션
>  ##### Resource는 java 에서 모두 사용 가능한 어노테이션 이름 -> 타입 순으로 찾아서 자동 DI 해주며 setter 생성
>  ##### Autowired는 Spring 에서 사용 가능한 어노테이션 타입 -> 이름 순으로 찾아서 자동 DI 해주며 setter 생성

### SQLMapper 에서 Join 구문을 사용 할 수 없을때 (중복된 데이터의 칼럼이 없어 SQL 로직으로는 힘들때)
> 1. Server단에서 합 치고 싶은 두개의 테이블을 SQLMapper로 정의 한 후 컨트롤러로 넘겨준다.
> 2. Front단에서 비동기 통신으로 두 데이터를 비교한 후 같으면 데이터를 sameData 로 저장 시켜 준 후
> 3. 펑션을 만들어 view단에 뿌려주는 방식 >> 해본 결과 제일 쉬웠다..

