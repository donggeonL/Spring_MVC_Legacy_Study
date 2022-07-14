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
