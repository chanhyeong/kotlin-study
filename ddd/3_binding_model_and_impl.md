# 3. 모델과 구현의 연계
기술 분석가, 업무 전문가 간 도출된 모델은 그 사이에선 통용되지만  
개발자는 활용할 수 없음 (구현 과정의 시행착오가 포함되어 있지 않음)  
-> 개발자 자체의 즉흥적인 설계  

기능은 갖췄지만 비대하고, 이해하기 어려움 -> 유지보수가 불가능  
방향성이 있는 구현도 있지만 코드만 봐서 시스템의 목적에 관해 통찰력을 얻지는 못함  

## MODEL-DRIVEN DESIGN (모델 주도 설계)
코드와 기반 모델이 연결되면 코드에 의미가 부여되고 모델과 코드가 서로 대응

#### 분석 모델 (analysis model, 가치 없음)
- 설계와 구분, 다른 사람이 만듦
- 소프트웨어는 고려하지 않은 **업무 도메인의 개념만 가짐**
- 이해하기 위한 수단으로만 간주
- 지식 탐구가 있긴 하지만, 개발자의 설계 과정에서 추상화할 때 성과 중 대부분이 사라짐
- 설계와 느슨하게 연결된 모델 간의 대응을 모두 유지하는 것은 효과가 높지 않음
- 주된 목표인 도메인의 이해에도 떨어질 수 있음 - 중요한 발견은 설계/구현 과정에서 나타나기 때문
  - 중요한 주제는 간과하고, 관련 없는 주제는 깊이 다룸
- 코딩이 시작되자마자 폐기, 대부분의 문제 재검토
- **설계 및 주된 부분이 도메인 모델과 대응하지 않는다면, 모델은 가치가 없고 소프트웨어와 정확함도 의심스러워진다**
- **모델과 설계 기능 사이의 복잡한 대응은 이해하기 힘들고, 설계가 변경되면 유지보수가 불가능해진다**
  - 분석과 설계가 동떨어져, 각자 활동에서 얻은 통찰력이 전해지지 않는다

분석: 도메인의 근본 개념을 알기 쉽고 표현력 있는 방식으로 포착  
설계: 배포 환경에서 효율적으로 수행되고 애플리케이션에서 다뤄야 할 문제를 올바르게 해결할 구성요소 기술  
구성요소: 프로그래밍 도구로 구현할 수 있어야 함

#### 도메인 추상화 + 애플리케이션의 문제를 해결하는 설계 방법은 여러가지
기술적인 내용 때문에 분석이 심각하게 타협된 상태는 안됨  
반대로 도메인 아이디어는 반영하지만 소프트웨어 설계 원칙을 따르지 않는 서툰 설계를 받아들여도 안됨

모델이 구현 관점에서 비현실적? -> 새로운 모델  
모델이 도메인의 핵심 개념이 부실? -> 새로운 모델

모델링과 설계 프로세스가 하나의 반복 고리

#### 도메인 모델을 설계에 밀접하게 연관시키는 원칙을 강제하면
각종 모델 가운데 좀 더 유용한 것을 선택하는 기준이 만들어짐

여러 iteration, reactoring 과정을 거쳐 관련성 있는 모델이 만들어짐

### 소프트웨어 시스템의 일부를 설계할 때는
1. 도메인 모델을 있는 그대로 반영해서 설계와 모델의 대응을 분명하게 하자
2. 모델을 재검토하여 더 자연스럽게 소프트웨어로 구현될 수 있게 수정하자

=> 견고한 UBIQUITOUS LANGUAGE 를 지원하는 것 + 분석과 설계의 두 가지 측면을 충분히 만족하는 단 하나의 모델을 만들어야 함

### 모델로부터 설계와 기본적인 책임 할당에 필요한 용어 도출하자
코드를 작성할 때 용어를 사용하면 코드가 모델을 표현한 것  
코드의 변경이 곧 모델의 변경으로 이어짐

### 구현을 모델과 묶으려면 OOP 와 같은 모델링 패러다임을 지원하는 소프트웨어 개발 도구와 언어가 필요하다

---
코드에서 요구사항 분석에 이르기까지 단일 모델만 적용
- 단일 모델은 오류를 일어날 확률을 줄임
  - 설계가 주의 깊게 고려한 모델의 직접적인 결과물에 해당하기 때문

모델은 실제적인 구현을 위해 정성스럽게 만들어져야 함
- 설계와 구현 기법을 활용 -> 코드가 모델을 효과적으로 표현 (2부)
- 지식 탐구자는 모델의 선택사항들을 파악, 정제하여 실제적인 소프트웨어의 구성 요소로 만듦
- 개발은 모델, 설계, 코드를 단일한 활동으로 정제하는 반복적인 과정 (3부)

## 모델링 패러다임과 도구 지원
MODEL-DRIVEN DESIGN 이 성과를 내려면 정확하게 **모델과 구현이 직접적으로 대응해야 한다**  
모델과 설계 간 밀접한 대응: 모델링 패러다임 내에서 업무 -> 객체지향 프로그래밍이 효과적 (모델링 패러다임에 근거 + 모델의 구성요소에 대한 구현 제공)

## HANDS-ON MODELER
1. **코드의 변경 = 모델의 변경이다**  
2. **모델이 효과적인 구현을 뒷받침하고, 핵심 도메인의 지식을 추상화한다**

#### 개발자는
코드를 접하는 데 어느 정도 시간을 투자해야 한다  
코드를 통해 모델을 표현하는 법을 배워야 한다  
모델에 관한 토의에 깊이 관여하고 도메인 전문가와도 접촉해야 한다  
UBIQUITOUS LANGUAGE 를 토대로 모델의 아이디어를 나눠야 한다