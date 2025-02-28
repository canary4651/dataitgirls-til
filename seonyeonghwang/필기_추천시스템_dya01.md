# 추천시스템

Created: Oct 21, 2019 10:27 AM

# 추천 시스템 분류

## 시나리오에 따른 분류

- 연관된 아이템 추천
    - 현재 소비되고 있는 아이템과 연관된 아이템을 추천
    - 카카오 맵 : 신전떡볶이 마포를 검색했을 때 많이 찾는 주변 음식점
- 개인화 아이템 추천
    - 11번가 : 소비중인 아이템이 없더라도, 개인의 관심사를 찾아 소비할 만한 아이템을 추천

## 피드백 종류에 따른 분류

- 명시적 피드백을 사용하는 추천 시스템
    - 영화 평점 / 좋아요, 싫어요와 같이 소비자가 "명시적으로" 자신의 선호를 표현한 데이터 = 명시적 피드백
        - facebook의 경우 positive는 명확한데 negative는 명확하지 않다
- 암시적 피드백을 사용하는 추천 시스템
    - 웹 페이지 접속 기록 (상품), 음악 청취 기록 같이 소비자가 명시적으로 표현하진 않은 피드백 = 암시적 피드백

## 업데이트 주기에 따른 분류

- **정적 추천 시스템**
    - 특정 시점의 데이터를 사용해 추천 결과를 계산하는 추천 방식
- 동적 추천 시스템
    - 지속적으로 사용자의 데이터를 받아 추천 결과를 업데이트하는 추천 방

# 추천 알고리즘

## Knowledge-based Filtering

- 유저에 대한 정보가 거의 없어서 추천해줄 수 있는 게 없을 때 사용
- 추천하고자 하는 분야의 도메인 지식을 활용해 추천 하는 방식
- e.g. 성별/연령별로 많이 팔리는 상품들을 모아 추천에 활용
- 편견이 들어갈 수 있음

## Content-based Filtering

- 추천 하려는 아이템의 콘텐츠 정보를 분석하거나 정리 된 메타 정보를 활용해 콘텐츠별로 특징 정보를 만들고 이를 활용해 추천
- e.g. 액션 장르 영화 페이지 하단에 다른 액션 장르의 영화를 추천
- 대체적으로 리소스가 많이 든다

## Collaborative Filtering

- **가장 많이 쓰는** 방법
- 소비자의 아이템 소비 이력을 사용해 소비하지 않은 새로운 아이템을 추천
- e.g. 영화 감상 이력을 바탕으로 소비자가 좋아할 만한 영화를 찾아내서 추천
- 쇼핑몰에서 청바지를 샀는데 청바지를 산 사람들은 대체로 셔프를 샀으니 추천해주는 형태

# 추천 알고리즘 평가 방법

## 오프라인 평가

- 사용자의 아이템에 대한 선호 기록과 추천 시스템이 추천한 결과를 비교하여 추천 품질을 평가
- 마우스를 추천해줬을 떄 진짜 마우스를 샀는지를 평가
- 따로 돈이 들지 않음

### 특징

- 별다른 비용 지출 없이 수집된 데이터만 사용하여 평가가 가능
- 여러 모델을 동시에 평가할 수 있음
- 선호 기록이 기존에 사용 중인 추천 모델에 영향을 받을 수 있으므로 실제 사용자의 만족도와 평가 결과가 다를 수 있음
    - 기존의 데이터를 가지고 추천해주는 거기 때문에 점수가 높다고해도 확신하기 어려움

## 온라인 평가

- 가장 좋은 방법
- 만들어진 추천 시스템을 직접 사용자에게 노출시켜 사용자의 반응을 수집하여 추천 품질을 평가
    - A/B 테스트나 통계적인 샘플링을 적용
    - 최대한 랜덤하게 뿌림

### 특징

- 시간의 흐름에 따른 평가가 가능하고 실제 사용자의 만족도를 측정한다는 측면에서 정확한 방식
- 비용이 비싼 평가 방식 (사용자의 만족도 감소 가능성 등)
    - 사용자가 좋아할지 안좋아할지 모르는 상태에서 내보내야 함
    - 나쁜 경험을 받은 유저가 이탈을 해버리면 크리티컬