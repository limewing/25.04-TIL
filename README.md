# 25.04-TIL
## 04.04
개발자 의견에 따라 방향키에서 wasd키로 조작을 디폴트로 변경   
제작 시스템을 재료를 1~3개를 넣으면 그 재료를 필요로 하는 결과물이 나오도록 하자 - 개발자가 shattered pixel dungeon의 자료를 통해 건의해서 기존의 UI에서 변경하기로 정함  
  
## 04.07
ERD 작성 결과를 토대로 DB작업
  
## 04.08
DB 작업 마무리
  
## 04.09  
에셋 탐색 및 피드백에 따라 recipe_DB와 Recipe_ingredient_DB를 통합

## 04.10
- 모든 id 6자리 정수로 변경  
- 모든 PK값 필드명 id로 통일  
    - FK는 그대로 유지  
- FK 받아오는 값이 비어있을경우 -1로 처리함  
- Item_DB :  
    - 버프, 디버프 아이템 대응 위한 필드 추가  
    - ~~스크롤 기믹을 위한 mp_cost 필드 추가~~  
        - recipe_DB로 필드 이동  
    - 200101 ~ 200103 스크롤 아이템 추가  
    - 201006 ~ 201009 재료 아이템 추가  
- Recipe_DB :  
    - 210101 ~ 210103 스크롤 레시피 추가  
- Monster_DB : 230002 ~ 230005 몬스터 추가  
    - biome_id를 추가하고 Monster_Biome_DB 제거처리  
- Monster_Biome_DB : 삭제됨  
- Monster_Skill_DB :  
    - 230001 ~ 230005 : 240001(기본 공격) 스킬 추가  
    - 230004 : 240002(강타) 스킬 추가  
    - 230005 : 240003(취약 포자) 스킬 추가  
- Skill_DB :  
    - 240001 ~ 240003 스킬 추가  
    - owner_type 필드 삭제(스킬의 소유자는 monster_Skill_DB에서 판단하고 있기 때문에)  
    - trigger_type : enum으로 변경  
    - trigger_value 필드 추가됨 : trigger_type가 특정 수치를 필요로 할 경우 그 값  
- Equip_DB : 추가됨  
