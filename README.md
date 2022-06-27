#### Spring_MVC_Legacy_Study

## Mybatis
> #### CDATA

>  #### SQL MAPPER ( XML 형식 ) 기본형식
```
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
