# 2022년 대한민국 20대 대선 개표 데이터 (2022년 3월 10일 AM 09~12시 버젼)
- 2022년 3월 10일 오전 9시경 선거관리위원회 홈페이지의 개표단위별 개표결과입니다.
- 대전광역시의 경우 오전 11시 50분경의 자료입니다
- 선관위 데이터를 옮겨온 것으로, 별도의 출처 표기는 필요 없습니다.
- 만든 후 한 번 검토하였으나, 실수가 있을 수 있습니다. 본인 책임 하에 사용하시기 바랍니다.


## 파일 구성
- ver20220309_sgg_vote_simple.geojson : 시군구 개표 데이터 및 지도. 폴리곤 도형 단순화
- ver20220309_emd_vote_simple.geojson : 읍면동 개표 데이터 및 지도. 폴리곤 도형 단순화
- ver20220309_emd_vote.geojson : 읍면동 개표 데이터 및 지도. 폴리곤 도형 좀 더 상세함
- vote_all_raw.tsv : 투표소별 개표 데이터. 선관위 테이블 형식에 시도, 시군구를 덧붙인 것으로, 온전한 RDB 형식은 아님
- vote_sgg.tsv : 시군구별 개표 데이터
- vote_emd.tsv : 읍면동별 개표 데이터
- propertiesTable.tsv : 행정구역 코드 및 이름 + 선관위 코드 및 이름

## 읍면동 데이터 주의점
  
- 읍면동별 자료는 투표소별 투표수와 관내사전투표만 포함됩니다.
- 읍면동별 자료는 시군구단위 집계 기준 대비 다음의 세 가지 항목이 누락되어 있습니다.
  - 거소,선상투표 
  - 관외사전투표
  - 재외투표
- 따라서, 이 자료의 모든 투표수를 합산해도 전국 투표수보다 적게 나옵니다.

- 0으로 처리한 읍면동
  -서울특별시 강동구 둔촌제1동의 자료는 0으로 처리했습니다.
  - 둔촌제1동은 재건축 중이라 적은 투표인원이 둔촌제2동 투표소에서 투표했으므로 둔촌제2동 투표 결과에 포함되어 있습니다.
  - 경기도 광명시 광명1동도 마찬가지 경우로, 광명2동 투표 결과에 포함되어 있으며, 광명1동은 0으로 처리했습니다.


## 영문 컬럼
각각의 컬럼 내용은 다음과 같습니다.
- POPU_ALL	선거인수 (투표수 + 기권수)
  - VOTER	투표수 ( 유효투표수 + 무효투표수)
  - C01	더불어민주당 이재명
  - C02	국민의힘 윤석열
  - C03	정의당 심상정
  - C04	기본소득당 오준호
  - C05	국가혁명당 허경영
  - C06	노동당 이백윤
  - C07	새누리당 옥은호
  - C08	신자유민주연합 김경재
  - C09	우리공화당 조원진
  - C10	진보당 김재연
  - C11	통일한국당 이경희
  - C12	한류연합당 김민찬
  - VOTE_VAL	유효투표수(C01~C13합계)
  - VOTE_INVAL	무효투표수
  - NON_VOTER	기권수