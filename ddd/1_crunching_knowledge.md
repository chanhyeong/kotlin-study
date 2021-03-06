# 1부. 동작하는 도메인 만들기
- Domain: 소프트웨어를 사용하는 사용자의 활동이나 관심사와 관련
- Model: 지식을 선택적으로 단순화하고 의식적으로 구조화한 형태
- Domain model
  - 특정 다이어그램이 아니라 다이어그램이 전달하고자 하는 아이디어
  - 도메인 전문가의 머릿속에만 존재하는 지식이 아니라, 해당 지식을 엄격하게 구성하고 선택적으로 추상화한 것
- Domain modeling 은 realistic 한 모델을 만드는 문제가 아님, 단순히 필요한 결과를 내는 소프트웨어 매커니즘을 만드는 것도 아님
  - 목적에 따라 제약에 관계 없이 현실을 표현하는 영화 제작에 가까움

## DDD 에서의 모델의 유용성
1. 모델과 핵심 설계는 서로 영향을 주며 구체화된다
    - 모델 - 구현의 긴밀한 연결
      - 모델을 의미있게 만들고, 모델의 분석이 프로그램에 적용되게끔 보장
      - 유지보수, 기능 개선에 도움
2. 모델은 모든 팀 구성원이 사용하는 언어의 중추
    - 모델과 구현이 서로 연결되어 있으므로, 이걸 토대로 프로그램에 관한 의견
    - 개발자 - 도메인 전문가가 의사소통하는데 별도의 번역이 필요 없음
3. 모델은 지식의 정수만을 뽑아낸 것
    - 모델: 도메인 지식을 조직화하고 가장 중요한 요소를 구분하는 팀의 합의된 방식
      - 용어 선택, 개념 분류, 분류한 지식을 서로 연관시킬 때 도메인에 관한 우리의 사고 방식이 담겨 있음
      - 모델 - 구현이 연결되어 있다면 초기 버전의 소프트웨어를 통해 얻은 경험을 모델링 프로세스에 피드백으로 활요할 수 있음

## 소프트웨어의 본질
도메인에 관련된 문제를 해결하는 능력

도메인이 복잡하면? -> 유능하고 숙력된 사람의 집중적인 노력이 필요한 어려운 일이 됨  
개발자는 도메인 연구에 몰두 + 모델링 기법을 연마하여 도메인 설계에 통달해야 함

팀의 리더가 도메인의 중심이 되는 개념을 알고 있어야, (갈피를 못 잡을 때) 프로젝트를 올바른 방향으로 되돌려 놓을 수 있음

# 1. 지식 탐구
PCB 기판 프로그램 설계 예시...

## 효과적인 모델링의 요소
1. 모델과 구현의 연계
    - 초기 프로토타입을 토대로 본질적인 **연결 고리** 를 만들고, 이어지는 주기 내내 유지
2. 모델을 기반으로 하는 언어 정제
    - 엔지니어는 PCB, 본인은 클래스 다이어그램이 뜻하는 바를 설명
    - 모델에서 바로 용어를 꺼내서 모델의 구조와 일관되게 문장을 구성, 별도 해석 없이도 명확히 이해
3. 풍부한 지식이 담긴 모델 개발
    - 객체를 행위를 지니고 규칙 이행
    - 모델은 단순 데이터 스키마가 아니라, 다양한 지식 포함
4. 모델의 정제
    - 중요한 개념이 더해지기도 하고
    - 중요하지 않다고 판명된 개념은 제거
5. 브레인스토밍과 실험
    - 스케치를 비롯한 브레인스토밍을 하려는 태도 + 결합된 언어를 바탕으로 토의를 모델에 대한 실험실로 변모
    - 수백 가지의 실험용 변종 연습, 시도, 평가

## 지식 탐구 (Knowledge Crunching)
효과적으로 도메인 모델링을 수행하는 과정
- 많은 정보 속에서 미미한 관련성을 찾고
- 전체를 이해할 수 있는 간결한 관점을 찾아 체계적인 아이디어들을 차례로 시도
- 모든 세부사항에 들어 맞는 추상적 개념이 나타나면 성공

도메인 모델의 지속적인 정제를 토대로, 개발자는 기능만을 기계적으로 만드는 데 머무르지 않고 업무의 중요 원칙을 배움  
도메인 전문가들은 스스로 이해하는 바를 자주 정제하고, 소프트웨어 프로젝트에서 요구하는 개념적 엄밀함을 이해  
-> 팀 구성원이 유능한 지식 탐구자로 거듭남  
-> 모델과 관게 없는 것은 가려내고 모델을 더욱 유용한 형태로 고침 -> 모델이 명료하게 조직화, 추상화. 구현을 더 용이하게 함

모델이 향상되면서 - 프로젝트 과정에서의 정보들을 조직화하는 도구로 자리 잡음 + 요구사항 분석에 초점  
모델은 도메인을 이해하는 데 실용적이고 유용해야 함 + 쉽게 구현하고 이해하기 충분할 만큼 엄밀

## 지속적인 학습
**소프트웨어를 작성하기 시작할 때 우리는 충분히 알지 못한 상태에서 시작**

#### 지식이 새기 마련
- 학습한 사람들은 자리를 옮김, 조직 개편으로 팀이 흩어짐
- 중대한 시스템이 외주로 제작되어 코드는 전달되지만 지식은 전달되지 않음
- 힘겹게 알아낸 지식이 코드와 문서에 유용한 형태로 표현되지 못함

생산성이 매우 뛰어난 팀은 **지속적인 학습**을 바탕으로 의식적으로 지식 함양
- 개발자; 도메인 모델링 기술과 같은 기술적 지식이 모두 함양됨을 의미
- 스스로 학습하는 팀원은 가장 핵심적인 부분을 개발하는 데 초점을 맞춘 고정 핵심 인력을 형성 (15장)
- 핵심 팀원에게 축적된 지식으로 더욱 유능한 지식 탐구자

## 풍부한 지식이 담긴 설계
도메인과 관련된 엔티티만큼, 업무 활동과 규칙도 도메인에 중요  
개발자는 모델의 변경에 맞춰 구현을 리팩토링하여 변경 사항 반영, 애플리케이션에서는 활용

지식 탐구가 열정적으로 이루어지려면 엔티티와 값을 넘어 이러한 활동이 이루어져야 함  

### 예시 - 감춰진 개념 추출하기
선박 화물의 운송 예약을 위한 애플리케이션의 도메인 모델 예  

```java
public int makeBooking(Cargo carge, Voyage voyage) {
  int confirmation = orderConfirmationSequence.next();
  voyage.addCargo(cargo, confirmation);
  return confirmation;
}
```

- 마지막 순간에 예약 취소할 가능성이 있어 **초과예약(overbooking)**을 받는 것이 해운 산업의 관행
```java
public int makeBooking(Cargo carge, Voyage voyage) {
  double maxBooking = voyage.capacity() * 1.1;

  // 중요한 업무 규칙이 메소드의 guard clause 로 감춰짐
  // guard clause: 오류를 방지하고자 미리 제약조건을 점검할 용도로 사용하는 절
  if ((voyage.bookedCargoSize() + cargo.size()) > maxBooking)
    return -1;
  int confirmation = orderConfirmationSequence.next();
  voyage.addCargo(cargo, confirmation);
  return confirmation;
}
```

4장에서는 layered architecture 원칙을 보고 위 규칙을 도메인 객체로 옮길 것  
위 코드는 다음과 같은 문제가 있음

1. 개발자의 도움이 있더라도 업무 전문가가 이 코드를 읽고 규칙을 검증하지는 못함
2. 해당 업무에 종사하지 않고 기술적인 측면만 담당하는 사람은 코드와 요구사항을 결부시키기가 어려움

초과예약은 일종의 정책(policy) - Strategy

변경 예
```java
public int makeBooking(Cargo cargo, Voyage voyage) {
  if (overbookingPolicy.isAllowed(cargo, voyage)) return -1;
    return -1;
  int confirmation = orderConfirmationSequence.next();
  voyage.addCargo(cargo, confirmation);
  return confirmation;
}

public boolean isAllowed(Cargo cargo, Voyage voyage) { ... }
```

1. 초과예약의 특성을 단순 불분명한 계산이 아닌 불개의 중요한 업무 규칙임을 알아야 함
2. 프로그래머는 업무 전문가가 이해할 수 있는 수준의 기술적 산출물, 코드까지 보여주면서 피드백 고리 완성

## 심층 모델
유용한 모델은 겉으로 드러나 있는 경우가 거의 없음  
도메인과 애플리케이션의 요구사항을 이해하게 되면서, 처음에 중요하게 생각했던 피상적인 모델 요소를 버리거나, 관점을 바꿈  
처음에는 안보이지만 문제의 핵심을 관통하는 포착하기 힘든 추상화가 서서히 나타남