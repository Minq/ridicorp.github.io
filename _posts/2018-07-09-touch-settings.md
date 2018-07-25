---
layout: blog_post
title: "리디북스 뷰어 터치 설정 개선"
description: "터치 제스처의 문제점과 개선 과정을 공유합니다."
header-img: "blog/img/2018-07-09/bg-16-3.png"
date: 2018-07-25
author: "sunha.kim"
category: design
published: true
---

리디북스 앱은 페이지를 넘길 때 다음과 같은 제스처를 사용합니다. <br>

> 화면의 **오른쪽**을 터치하면 **다음 페이지**로 넘어간다.<br>
> 화면의 **왼쪽**을 터치하면 **이전 페이지**로 돌아간다. 

전자책 사용자에게는 익숙하고 직관적인 제스처입니다. 하지만 특정 콘텐츠나 사용자의 독서 습관에 따라 이런 제스처가 불편할 수 있음을 알게 되었습니다.
이 글에서는 사용자가 터치를 사용하며 겪은 문제점들을 정리하고 두 차례에 걸쳐 개선한 과정을 공유하고자 합니다.

---
# 문제 상황
## 1) 반대 방향(←)으로 보는 책을 읽을 때

우리나라의 책은 왼쪽에서 오른쪽으로 (→) 시선을 이동하며 읽습니다. 그러나 일본 만화같이 우철 [^1] 로 만든 책은 내용이 오른쪽에서 왼쪽으로 (←) 진행되기 때문에 반대 방향으로 책을 읽습니다. 종이 만화책을 거꾸로 맨 뒷장부터 읽듯이 전자책도 마찬가지입니다.

일반 책들과 달리 일본 만화책을 볼 때는 반대로 제스처를 사용해야 합니다.

> 화면의 **왼쪽**을 터치하면 **다음 페이지**로 넘어간다. <br>
> 화면의 **오른쪽**을 터치하면 **이전 페이지**로 돌아간다. 

만약 오른손으로 일본 만화책을 본다면, 다음 페이지를 보기 위해 화면의 왼쪽을 터치하는 것이 다소 불편하게 느껴질 수 있습니다. 아래는 이와 관련한 사용자 의견입니다.

> _"만화책을 보는데 일본 만화라서 좌우가 반대네요. 보기가 엄청 불편해서 터치 좌우를 바꾸려고 하니 뷰어에 기능이 없는 것 같습니다. 기능 좀 추가해주세요."_

> _"한국 책은 오른쪽 화면을 탭 하면 다음 페이지로 넘어가는데 일본 책은 반대로 탭 해야 하는 게 불편합니다. 한국 책처럼 넘길 수 있으면 좋겠어요."_


## 2) 왼손으로 파지할 때

고정된 페이지 넘김 방향이 불편한 사용자는 반대 방향으로 보는 책을 읽는 사용자뿐만이 아니었습니다. 왼손으로 책을 보는 사용자들은 이미 비슷한 불편을 겪고 있었습니다.

> _"제가 왼손잡이여서 왼손에 주로 파지하고 보는데요. PAPER에는 페이지 넘김 버튼의 방향을 바꾸는 설정이 있는데 스마트폰 앱에는 이 기능이 없어서 불편합니다."_

> _"주로 오른손으로 지하철이나 버스 손잡이를 잡고 왼손으로만 책을 보는데, 페이지 넘길 때 오른쪽 터치가 힘듭니다. 좌우 터치 조작을 바꿀 수 없을까요? "_



# 문제 해결하기

위와 같은 문제들을 미루어 볼 때 사용자들이 원하는 목표를 정리하자면 이렇습니다.

* 일본 만화책을 볼 때, 편하게 페이지를 넘겨보고 싶다.
* 왼손으로 파지하고 책을 읽을 때, 편하게 페이지를 넘겨보고 싶다.
<br>

요약하자면, 사용자는 특정 콘텐츠나 상황에 국한되지 않고 어떤 책이든 편하게 페이지를 넘길 수 있기를 원했습니다.


## 터치 설정을 바꿀 수 있는 옵션 추가하기
### 1. 개선 전 방법: 상/하 터치로 페이지 이동하기
기존에는 뷰어 설정에 **'상/하 터치로 페이지 이동'**이라는 ON/OFF 토글 기능이 있었습니다. 앞서 말한 문제들처럼 기본 좌/우 제스처로 책 읽기가 불편했던 사용자를 위한 기능입니다. 이 기능을 사용하면 책의 종류, 좌/우 방향과 상관없이 화면 하단의 일정 영역을 터치하면 다음 페이지로 이동할 수 있습니다.

해당 기능이 있음에도 불구하고 사용자들은 왜 여전히 불편해했을까요?

기능적으로 보면 상/하 터치 방식이 문제 상황을 모두 해결하는 것 같지만 편리하게 사용할 수만은 없었습니다. 상/하 터치 방식은 좌/우 터치 방식에 비해 생소한 까닭에 익숙해지기 어렵습니다. 또한, 화면이 넓은 모바일 기기에서는 이전 페이지로 돌아가려면 한 손으로 조작이 힘들어서 두 손을 사용해야 합니다. 

### 2. 설정에 추가할 옵션 결정하기
타 서비스와 그동안 수집한 사용자 의견을 적극적으로 참고하여, 필요한 페이지 넘김 옵션은 무엇인지 고민했습니다. 또한 전반적인 사용자를 기준으로 보았을 때 기능을 익히는데 복잡하거나 어렵지 않은 옵션을 찾고자 했습니다.

### 좌/우 터치로 페이지 이동

수집한 데이터에 따르면 대부분의 사용자는 그저 페이지 넘기는 방향의 좌/우를 반대로 설정하고 싶어 합니다. 책을 볼 때 상/하보다는 좌/우로 페이지를 넘기는 행동이 더 익숙하기 때문입니다.

그리고 데이터를 통해 사용자가 책을 볼 때는 **'이전 페이지'**로 이동하는 것보다 **'다음 페이지'**로 이동하고자 하는 경우가 24배 많다는 것을 확인할 수 있었습니다. 

![GA_ViewerPagingKeyEvent](/blog/img/2018-07-09/1.GA_ViewerPagingKeyEvent.png){:data-action="zoom"}

따라서 단순하게 **좌/우를 바꾸는 옵션**과 더불어 좌/우 터치 영역 **모두 다음 페이지로 이동**할 수 있는 옵션도 제공하기로 했습니다.

### 상/하 터치로 페이지 이동
위와 같이 좌/우 터치와 관련한 세 가지 옵션을 결정한 뒤 기존에 ON/OFF 토글로 제공하고 있던 상/하 터치 옵션을 어떻게 할지 고민했습니다. 잘 쓰이지 않는다고 생각했지만, 옵션을 한순간에 없애기엔 잘 쓰고 있던 사람에겐 또 다른 불편으로 여겨질 수도 있었습니다. 

당시에는 이 기능에 대한 데이터를 수집하지 않고 있어서 정확한 사용률을 파악할 수는 없었습니다. 따라서, 바로 옵션을 빼는 것은 보류하고, 이따금씩 태블릿과 같은 큰 기기를 쓰는 사용자에게 요청이 오던 상/하 터치를 반대로 하는 옵션도 추가하기로 했습니다.

### 3. 최종 시안
최종 확정된 5가지 옵션을 토대로 결정한 시안입니다.
![기존_터치로 페이지 이동](/blog/img/2018-07-09/2.before.png){:data-action="zoom"}
<figcaption>'터치로 페이지 이동'이라는 메뉴를 추가하고, 옵션을 이해하기 쉽도록 일러스트를 넣었습니다.
</figcaption>


이렇게 터치 설정을 바꿀 수 있는 옵션을 추가한 후, 정확한 사용률을 파악하기 위해 이벤트별 데이터를 수집하기 시작했습니다. 

# 문제 '다시' 해결하기
## 1) 사용성 테스트(Usability Test; UT)로 파악한 문제
2017년 말, 리디북스 사용자들을 대상으로 UT를 진행했습니다. 이를 통해 전반적인 서비스 이용 모습을 관찰할 수 있었고 새롭게 추가된 **'터치로 페이지 이동'** 기능에 대한 실제 사용 패턴도 엿볼 수 있었습니다.

**터치로 페이지 이동** 기능이 추가되고 여러 사용자로부터 터치의 방향을 바꿀 수 있어서 편해졌다는 피드백을 받았습니다. 하지만 UT를 진행하고 나니 여전히 몇몇 문제가 있다는 것을 알 수 있었습니다.

테스트 중, 일본 만화책을 보는 사용자에게 좌/우로 페이지 넘기는 방향을 바꾸어서 사용해보길 요청했고, 다음과 같은 문제들을 발견할 수 있었습니다.

![문제점](/blog/img/2018-07-09/3.problems.png){:data-action="zoom"}


이러한 문제들로 인해 다시 해당 기능을 개선하기로 했습니다.


## 2) 문제 해결 과정
### 1. 제공 옵션 줄이기
한 번에 다섯 가지나 되는 옵션을 제공하다 보니 원하는 옵션을 바로 고르기가 어려웠습니다. 따라서 불필요한 옵션을 제거하여 최적의 선택지만을 남기기로 했습니다.
![GA_PageMoveMode_LTR&RTL](/blog/img/2018-07-09/4.GA_PageMoveMode_LTR&RTL.png){:data-action="zoom"}

Android, iOS 각 플랫폼별로 수집된 데이터에 따르면, 대부분 옵션을 바꾸지 않고 기본 설정을 그대로 사용하고 있었습니다. 잘 쓰지 않을 것이라 예상했던 **위: 이전/ 아래: 다음** 옵션은 예상 보다 많이 쓰이고 있었고, **위:다음 / 아래:이전** 옵션은 예상 보다 쓰이지 않았습니다. 사용률이 적은 옵션을 선택지에 계속 남겨두는 것은 사용자에게 불필요한 고민을 줄 수도 있다고 생각했습니다. 따라서 해당 옵션을 과감히 없애기로 했습니다.

### 2. 명확한 레이블로 바꾸기
기존에 **상/하 터치로 페이지 이동**이라는 메뉴가 있었기 때문에, **터치로 페이지 이동**이라는 레이블이 좌/우, 상/하 옵션들을 모두 아우를 수 있다고 생각했습니다. 그러나 일반적인 사용자가 해당 레이블을 봤을 때 기능을 예상하기 어렵고 모호하게 느낄 수 있다는 의견이 있었습니다.

게다가 **페이지 설정** 섹션에 메뉴가 너무 많아져서 서로 구분이 잘되지 않았습니다. 따라서 **터치 설정**이라는 별도의 섹션으로 분리하고 '좌/우 터치 옵션'과 '상/하 터치 옵션'을 나누게 되었습니다.

### 3. 보다 정확한 일러스트로 안내하기
설정을 적용했을 때 결과를 쉽게 예측할 수 있도록 더 친절하고 정확한 일러스트가 필요했습니다.

기존의 일러스트는 한 줄에 여러 개를 보여주고 페이지 넘김 방향을 표시하는 화살표의 크기도 작아서 한눈에 인지하기 어려웠습니다. 이에 일러스트의 크기를 키우고 이전/다음 화살표의 방향을 보다 크게 표시해주었습니다. 그리고 다음과 같은 두 가지 방식으로 문제를 해결해 보고자 했습니다.
![개선_좌우 터치 영역 AB](/blog/img/2018-07-09/5.after_AB.png){:data-action="zoom"}
<!-- <figcaption>A.옵션을 선택하면서 기능을 익힐 수 있는 방법 / B.크고 직관적인 일러스트 버튼 방법</figcaption> -->

 - `A`: '왼쪽을 터치했을 때', '오른쪽을 터치했을 때'로 영역을 구분해 직접 조작하며 기능을 익힌다는 느낌을 줄 수 있습니다. 
 - `B`: 큼직하고 단순한 세 가지 일러스트 버튼을 제공하여 보다 빠르게 설정을 바꿀 수 있습니다.

### 4. 프로토타입으로 실험하기
위 시안들을 바탕으로 간단한 프로토타입을 만들고 내부 고객, 주변 지인을 포함한 총 8명을 대상으로 간단한 실험을 진행했습니다. 자유롭게 두 방식을 사용하게 해본 뒤, 어떤 방식이 더 편한지, 쉽게 쓸 수 있는지 등을 물었습니다.

그 결과 A 안은 이미 리디북스를 잘 알거나 고급 기능을 익히는 것에 어려움이 없는 사용자들이 선택했고, B 안은 리디북스 사용 경험이 많지 않거나 복잡한 조작을 원하지 않는 사용자들이 더 많이 선택했습니다.

즉, 고민 없이 직관적으로 옵션을 바꿀 수 있는 B 안이 더 적절한 방법임을 알 수 있었습니다.

### 5. 최종 개선된 시안
최종적으로 개선된 방법은 아래와 같습니다.
![개선_최종](/blog/img/2018-07-09/touch.gif){:data-action="zoom"}

1) 책을 보다 **'뷰어 설정'**을 들어갑니다. <br>
2) 맨 위 **'좌/우 터치 영역'** 메뉴를 누른 후, 원하는 옵션을 선택합니다. <br>
3) **'뷰어 설정'**을 닫고 뷰어로 돌아가면 원하는 방향으로 페이지를 넘길 수 있습니다. 


# 마치며
이번 작업을 진행하면서 기존에는 시도하지 않았던 다양한 방법으로 문제를 풀어나갈 수 있어서 뿌듯했습니다. 
특히, 가설의 검증을 위해 명확한 데이터를 참고한 것이 디자인 의사 결정에 많은 도움이 되었습니다.

사용성 테스트를 통해 실제 사용 패턴과 습관을 관찰함으로써 고객을 보다 폭넓게 이해하는 계기도 되었습니다. 만든 이가 제시한 방법이 항상 정답일 수는 없으며, 사용하는 입장에서 한 번 더 생각해보는 것이 중요하다는 것을 다시금 깨달았습니다.

Android 버전 8.10.0 이후부터 **'터치 설정'**을 조금 더 직관적으로 이용할 수 있게 되었습니다. 이렇게 또 한 차례 개선이 이루어진 만큼 더 많은 분들이 편하게 책을 보는 데 도움이 된다면 좋겠습니다.


---
[^1]: [우철](https://ko.wikipedia.org/wiki/%EC%A2%8C%EC%B2%A0%EA%B3%BC_%EC%9A%B0%EC%B2%A0)은 페이지의 오른쪽을 묶어서 책을 만드는 방식을 말합니다. 일본에서는 주로 세로쓰기를 사용하고 오른쪽부터 읽어 내려가기 때문에 주로 책을 우철로 묶습니다. 