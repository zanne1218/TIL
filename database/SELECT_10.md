# SELECT 문

### 중첩 질의
### 한 개의 애트리뷰트로 이루어진 릴레이션이 반환되는 경우
- 중첩 질의의 결과로 한 개의 애트리뷰트로 이루어진 다수의
투플들이 반환될 수 있음
- 외부 질의의 WHERE절에서 IN, ANY(SOME), ALL, EXISTS와
같은 연산자를 사용해야 함
- 키워드 IN은 한 애트리뷰트가 값들의 집합에 속하는가를 테스
트할 때 사용됨
- 한 애트리뷰트가 값들의 집합에 속하는 하나 이상의 값들과
어떤 관계를 갖는가를 테스트하는 경우에는 ANY를 사용
- 한 애트리뷰트가 값들의 집합에 속하는 모든 값들과 어떤 관
계를 갖는가를 테스트하는 경우에는 ALL을 사용
- 예) 영업부나 개발부에 근무하는 사원들의 이름을 검색하라.
    - IN 을 사용한 질의
        SELECT      EMPNAME
        FROM        EMPLOYEE
        WHERE       DNO IN

                    (SELECT     DEPTNO
                     FROM       DEPARTMENT
                     WHERE      DEPTNAME = '영업' OR DEPTNAME = '개발');
        이 질의는 중첩 질의를 사용하지 않고 아래 조인 질의로 나타낼 수 있다.
        SELECT      EMPNAME
        FROM        EMPLOYEE E, DEPARTMENT D
        WHERE       E.DNO = D.DEPTNO
                    AND (D.DEPTNAME = '영업' OR D.DEPTNAME = '개발');
