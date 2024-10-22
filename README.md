# Huge 팀 발표흐름

1. 제목 (1p.)
2. 팀 소개 (1p.)
    1. 팀 소개
    2. 팀원 소개
3. 경영진을 위한 요약 (1p. 모자라다면 2p.) = Executive Summary
4. 목차 (1p.)
5. <Q1-8> 과제에서 제시된 질문 리스트 (발표시간 중 11min을 여기에 할당하자.)
    1. <Q1> 2019.01~06중에 언제 지하철을 가장 많이 이용했을까?(기준:승하차총승객수)
        1. 탐색적 데이터 분석
            1. "일자별 합계 승하차총승객수 Top 10" (Dataframe table + 핵심 코드)
        2. 인사이트
            1. "일자별 합계 승하차총승객수 Top 5" (Dataframe table, 이전 것과 동일한 장표)
                1. 가장 많은 날은 5월 3일
                2. 대체로 5월이 많음
                3. 대체로 금요일이 많음
        3. <Q2> 첫 번째 가설: 1월~6월중에 5월에 지하철 승객수가 많다? (기준:승하차총승객수)
            1. 가설 정의 (1p.)
                1. H0: 1월~6월중에 5월에 지하철 승객수가 가장 많은 것은 아니다.
                2. H1: 1월~6월중에 5월에 지하철 승객수가 가장 많다.
            2. 탐색적 데이터 분석 (1p.)
                1. ["월별 합계 승하차총승객수" (barplot 1개 + 시각화 핵심 코드)](실습/김동주%20-%20월별%20합계%20및%20평균%20승하차총승객수.ipynb)
                2. (넣을지 말지 논의 필요) 평균으로 집계하면 4월이 많다.
            3. 결론 (1p.)
                1. H1 채택. (단, 합계를 기준으로 하였음을 명시.)
        4. <Q3> 두 번째 가설: 요일중에서 목요일에 지하철 승객수가 많다? (기준:승하차총승객수)
            1. 가설 정의 (1p.)
                1. H0: 요일중에서 목요일에 지하철 승객수가 가장 많은 것은 아니다.
                2. H1: ...
            2. 탐색적 데이터 분석 (3p.)
                1. ["요일별 합계 승하차총승객수" (barplot 1개 + 시각화 핵심 코드)](실습/김동주%20-%20요일별%20합계%20및%20평균%20승하차총승객수.ipynb)
                2. ["요일별 평균 승하차총승객수" (barplot 1개 + 시각화 핵심 코드)](실습/김동주%20-%20요일별%20합계%20및%20평균%20승하차총승객수.ipynb)
                3. 평균으로 비교하는 것이 유의미한가? (1p.)
                    1. ["요일별 승하차총승객수" (boxplot 1개 + 시각화 핵심 코드)](실습/김동주%20-%20요일별%20합계%20및%20평균%20승하차총승객수.ipynb)
                    2. 데이터의 정규성을 확인 -> 평균은 분명 유의미한 지표이다.
                4. [합계와 평균 비교 (barplot 1개)](실습/김동주%20-%20요일별%20합계%20및%20평균%20승하차총승객수.ipynb)
            3. 결론
                1. H0 채택 -> 금요일이 가장 많았다.
            4. 인사이트
                1. 왜 월요일의 합계/평균 승하차총승객수가 유독 차이가 났는가?
                    1. 데이터에 포함된 2019년 1월 1일은 화요일, 2019년 6월 30일은 일요일이다.
                    2. 월요일이 1회 덜 집계된 것이 영향을 주었다.
                2. 실습 예제로 제공받은 코드로 요일을 매핑하면 잘못된 요일에 매핑된다.
                    1. 2018년 어린이날(5월 5일)은 일요일이다. (어린이날 외에 다른 날을 사용해도 좋음)
                    2. 요일을 확실하게 아는 날을 기준으로하여 Dayofweek 딕셔너리를 재정의하였다.
                       -> 하루 씩 당겨져있던 것을 되돌려놓음.
    2. 연월 각각에 대해 일자별(월일별) 승하차총승객수 그래프를 그려보자.
        1. 가설 정의
            1. H0: 승하차총승객수에는 주기적으로 나타나는 패턴이 존재하지 않을 것이다.
            2. H1: 승하차총승객수에는 주기적으로 나타나는 패턴이 존재할 것이다.
        2. 탐색적 데이터 분석
            1. <Q4> "일자별 승하차총승객수 (2019-01-01 ~ 2019-06-30)" (pointplot 1개 + 시각화 핵심 코드) (2p.)
                1. 월별로 색을 구분 (1p.)
                2. 주차별로 색을 구분 (1p.) -> 주 마다 반복되는 패턴이 있음을 강조
            2. "요일별 평균 승하차총승객수" (barplot) + "승하차총승객수 (2019-01-07 ~ 2019-01-13)" (pointplot) (1p.)
                1. 두 plot을 한 figure에 출력 (subplot 말고, 그냥 하나의 plot에 두 데이터 모두 출력)
                2. 주 마다 반복되는 패턴의 예시로 보임
                3. 주말이 유독 적다는 점을 강조
        3. 결론
            1. H1 채택
        4. 인사이트
            1. 주 마다 나타나는 반복적인 패턴을 더 편하게 볼 수 없을까?
                1. "일자별 승하차총승객수 (2019-01-01 ~ 2019-06-30)" (heatmap 1개 + 시각화 핵심 코드)
            2. (이어서) 승객수가 유별난 날들이 존재한다. 이상치일까?
                1. "일자별 승하차총승객수 (2019-01-01 ~ 2019-06-30)" (heatmap 1개, 직전 것과 동일)
                2. 2월의 색이 특이한 부분 -> 설 연휴임을 강조
                3. 공휴일 혹은 주말 등 '휴일'에는 지하철 이용객 수가 더 적어진다.
                4. 공휴일 혹은 주말의 특징이 무엇일까?
                    1. "출퇴근/등하교를 하지 않는다"이지 않을까?
                    2. 아래 5.4.3. 에서 다시 소개할 예정
    3. <Q5> 가장 승객이 많이 타는 승차역은?
        1. 가설 정의
            1. H0. ...
            2. H1. 교통의 중심지들이 승차총승객수가 많을 것이다.
                1. (버스에서 내려서 지하철을 타니까? ??)
        2. 탐색적 데이터 분석
            1. "역별 승차총승객수 Top 10" (barplot 1개 + 시각화 핵심코드)
            2. "승차총승객수가 가장 많은 상위 20개의 역 위치" (folium marker + 시각화 핵심코드)
                1. 지하철 노선도가 같이 보였으면 좋겠음
                2. 특히 환승역이거나, 혹은 주변에 버스터미널이 있는지 보이면 좋겠음
                    1. 참고자료: 노선별 환승역 수 (2015년 기준) https://www.thescoop.co.kr/news/articleView.html?idxno=16708
        3. 결론
            1. H1. 채택 (!!!!!!!!!!!! 희망사항, 아직 검증 안됨 !!!!!!!!!!!!)
    4. 노선별 승하차승객수를 비교해 볼 수 있을까?
        1. 지하철 노선 소개 (2019년도 기준) (1p.)
            1. 각 노선별 대표색상과 이름이 무엇인지 한 눈에 볼 수 있는 간단한 자료
            2. 총 몇 종류의 노선이 존재하는가?
        2. 탐색적 데이터 분석
            1. <Q6> "<노선명> 역/요일별 승차승객수 (<역개수>개역)" (heatmap 작아도 되니 한 페이지에 모든 노선 표시 + 시각화 핵심코드)
        3. 인사이트
            1. 정보량이 많으니 일부 특이한 예시들을 살펴보자.
            2. (1호선, 2호선, 6호선) "<노선명> 역/요일별 승차승객수 (<역개수>개역)" (heatmap, 노선별로 각 1씩 총 3개)
                1. 히트맵 상에서 유독 승차승객이 많은 역들이 있다.
                2. 그 중 어떤 역은 평일에만 진하다.
                    1. 5.2.4.4. 기억나는가? 출퇴근/등하교 -> 평일에만 한다.
                    2. 평일에만 진한 역 근처가 직장가/학교일 수도 있을 것 같다.
        4. 첫 번째 가설
            1. 가설 정의
                1. H0. 승차와 하차 승객수는 상관관계가 없다.
                2. H1.
            2. 탐색적 데이터 분석
                1. <Q7> "1호선 역별 하차승객수" (barplot + 시각화 핵심코드)
                2. ["1호선 역별 승차/하차승객수 비교" (violin plot + 시각화 핵심코드)](실습/김동주%20-%201호선%20역별%20승하차%20승객수%20비교.ipynb)
                3. 승차/하차 승객 수의 correlation, 혹은 P-value 비교
            3. 결론
                1. 결과를 바탕으로 가설 채택
        5. 두 번째 가설
            1. 가설 설정
                1. H0. 주말에 비해 평일 이용객 수가 많은 역은 직장가/혹은 학교와 관련이 없다.
                2. H1. 주말에 비해 평일 이용객 수가 많은 역은 직장가/혹은 학교 인근에 위치한다.
            2. 탐색적 데이터 분석
                1. <Q8> "2호선 합계 승차승객수" (folium heatmap 과 marker + 시각화 핵심코드)
                2. "2호선 평일 합계 승차승객수 Top 10개 역" (folium heatmap + 시각화 핵심코드)
                    1. 가장 많았던 역들을 살펴보자
                3. 앞서 뽑은 히트맵 위에 근처에 위치한 직장가, 학교 표시
            3. 결론
                1. 5.4.5.2. 결과를 바탕으로 가설 채택
6. 인사이트 Plus
    1. 채택된 가설들 정리
    2. 새로운 질문들
        1. 주말까지 승하차총승객수가 많은 역들이 있었다. 무엇과 상관관계가 있을까?
            1. 첫 번째 가설
                1. 가설 설정
                    1. H1. 승하차총승객수는 지역 인구수에 비례 할 것이다.
                2. (추가적인) EDA
                    1. [지역구별 인구수 pointplot + 지역구별 승하차총승객수 barplot](실습/김동주%20-%20지하철%20역%20별%20인구수.ipynb)
                3. 결론
                    1. H0 채택
            2. 두 번째 가설
                1. 가설 설정
                    1. H1. 승하차총승객수는 상업구역(직장가가 포함되므로)에 밀집되어있을 것이다.
                2. EDA
                3. 결론
                    1. 아직 모름 (!!!!!!!!!!!! 아직 검증 안됨 !!!!!!!!!!!!)
        2. 상업지구는 젊은 층(생산가능인구)가 주 이용객일 것이다.
            1. 가설 세우고 확인해보기
            2. 만약 아니라면 출퇴근시간에만 젊은 층이 몰리는가 가설 세우고 확인해보기
7. 결론
8. 사업 제안
    1. 문제 정의
        1. 젊은 청년들을 가입시키고자 하는 요금제 상품이 있다고 가정. (KT에게 어필하자)
        2. 주말 이용객 수가 적은 것을 활용할 수 있는 상품이 없을까?
    2. 솔루션 제안
        1. 공휴일 할인 요금제 패키지
            1. 가입하면 주말 대중교통 이용을 할인해주거나 페이백 해주는 서비스
                1. 기업입장에서는 손실이 적음
                2. 긍정적인 기업이미지, 혹은 상품 이미지 형성
                3. 이동량이 많은 생산가능인구(젊은층)을 유인할 수 있는 좋은 미끼 상품
        2. 광고는 젊은 층이 많이 이용하는 평일 이용객수가 더 많은 지역 위주로?
            1. (!!!!!!!!!!!! 희망사항, 아직 검증 안됨 !!!!!!!!!!!!)
    3. 핵심 기능 소개
        1. (사실 기능은 없는 사업 제안 아이디어이므로)
        2. 주말에 대중교통 이용비용 10% 페이백?
        3. 광고를 설치할 역 후보 5개 정도, 역명 열거 후 선정이유 짧게 요약
9. 세 줄 요약 및 Q&A
