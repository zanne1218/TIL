# 이상(anomaly)현상

### 이상의 원인
- 애트리뷰트들 간에 존재하는 여러 종속관계를 하나의 릴레이션에 표현했기 때문

### 이상의 해결
- 정규화 (normalization) : 애트리뷰트들 간의 종속관계를 분석하여 여러 개의 릴레이션으로
분해(decomposition)

### 스키마 설계 : 데이타베이스의 논리적 설계
① 애트리뷰트들과 이들의 제약 조건 (종속성)들을 수집
② 수집된 결과를 명시된 제약 조건에 따라 여러 개의 릴레이션으로 분할
    ⇒ 스키마 변환 (schema transformation)

### 스키마 변환의 원리
① 정보의 무손실
스키마 변환 시 정보의 손실이 있어서는 안 된다.
② 데이타의 중복성이 감소되어야 한다.
여러 가지 이상 현상을 제거할 수 있기 때문.
③ 분리의 원칙
하나의 독립된 관계성은 하나의 독립된 릴레이션으로 분리시켜 표현해야 함.
