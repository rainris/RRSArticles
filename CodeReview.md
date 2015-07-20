#Code Review

개발1실 세미나
권오진

##Code Review를 주제로 정한 이유

* iOS와 안드로이드가 하는 공통의 작업
* 우리가 제일 많이 하는 일중에 하나
* 모두가 아는 이야기들
* 하지만 정말 잘 하고 있을까?
* 많은 시간을 투자하고 있는만큼 적극적인 Code Review를 통해 최대 케미를 얻을 수 있도록 한다.

##Code Review를 왜 하는가?

* Code Quality를 굉장히 빠른 시점에서 높이는 방법이다.
* 코드에서 숨겨진 버그를 찾는다. (Bad Code Smell)
* 디자인과 구현의 일관성 레벨을 유지한다.
* 재작업을 줄인다.

>하지만 위의 것들은 보장되지 않는다.

##진정한 목표는

* 서비스 도메인 지식의 공유가 가능하다.
* 팀원들 서로에게 배움의 기회가 제공된다.
* 팀원 개개인의 능력을 높이고, 나아가 팀의 능력을 높인다.
* 더 나은 지식공동체를 만들어간다.
* 자신의 코딩 기량 인정받음으로써 개발자들에 대한 보상이 된다.

##Code Review Spectrum

* Code Inspection
* Team Review
* Walkthrough
* Peer Review
* Passaround

###Code Inspection

>Moderator, Reader, Designer/Coder, Tester로 구성된다.

* ![Code Inspection](https://github.com/rainris/RRSArticles/blob/master/Images/CodeReview/Fagan_Inspection_Simple_flow.jpg)
* Planning
  * Code Inspection에 대한 계획을 수립한다.
  * 기간, 대상, 종료조건등을 설정
  * Inspection Team이 Setup된다.
* Overview
  * Inspection Team에 Review할 시스템과 배경에 대한 교육이 이루어진다.
  * 팀원간의 역할이 정의된다.
* Preparation
  * Inspection을 위한 사전준비단계이다.
  * 각자의 역할별로 필요한 문서등을 습득해 이해한다. 필요하면 인터뷰를 진행한다.
  * Test 환경을 구축한다.
* Meeting
  * 각자의 역할에 따라 Inspection을 수행한다.
  * 발견되는 모든 결함은 개발자에게 전달된다.
  * 필요할 경우 Designer/Coder에 의해 작성된 수정방향이 전달되기도 한다.
* Rework
  * 발견된 결함을 수정한다.
* Follow-up
  * 발견된 모든 결함이 수정되었는지 확인한다.
  * Inspection을 종료한다.

> 가장 정형화된 방법

###Team Review

* 장소, 시간, 리뷰의 주제를 선정해서 리뷰를 진행한다.
* Author와 Moderator는 필수로 구성한다.
* Author가 코드에 대해 설명한다.
* 팀원은 결함이나 개선점을 찾는다.
* 나온 의견은 Action Item으로 정리한다.
* Moderator는 Action Item을 Task로 관리한다.
* Short Release에 수행한다.
  * Short Release - 특정 모듈이나 기능이 완료되는 시점
* 일주일에 한번정도가 적당하다.
* Risk가 크다고 판단되는 경우 수행한다.

###Walkthrough

* Author만 존재한다.
* Author는 리뷰의 주제와 시간을 정해서 발표하고, 동료들은 자유롭게 의견을 개진한다.
* 디테일한 Code Review보다 정보공유성격에 유리하다.
* 정기적으로 진행할 수도 있고, 이슈가 있을 경우 비정기적으로도 진행할 수 있다.

###Peer Review

* Peer Desk Check, Over the shoulder review
* 2~3명이 진행한다.
* Commit 하기전에 동료와 나란히 앉아 Change List를 Review한다.
* 고칠 것이 있으면 바로 고칠 수 있다.
* 필요할 때마다 자주, 바로 진행할 수 있다.
* Junior 개발자의 멘토링으로 사용될 수 있다.
* Reviewer의 비용이 크다.

###Passaround

* Code Review Spectrum에는 포함되지 않는다.
* 오프라인 위주로 진행되는 리뷰.
* Author가 리뷰할 부분을 메일이나 시스템에 등록한다.
* 참여자는 메일이나 시스템을 통해 자유롭게 리뷰한다.
* 시간과 장소의 구애를 받지 않는다.
* 커뮤니케이션 속도가 느리다.
  * 이를위해 Reviewer를 지정한다.

##Code Review는 상황에 따라 다르게 실행되어야 한다.

###스타트업의 경우
* 서비스가 시장에서 검증되지 않은 상태
* 기술적인 빚(Technical Debt)을 가지고가는게 낫다.
* Code Quality 기준을 낮게 잡고, Code Review를 느슨하게 유지한다.
* http://estimastory.com/tag/린스타트업/
  * “쉽게 말해 누가 나의 고객이 될지, 내가 시도하는 이 방법이 먹힐지 알 수 없는 불확실한 상황에서 성공하기 위한 새로운 과학적 접근의 방법론이다.
  * 낭비를 최소화하고 효율성을 극대화한 도요타의 ‘린(Lean·슬림) 제조방식’ 아이디어를 스타트업의 관리에 접목한 것이다.
  * 전통적 경영에서는 엄밀한 시장조사를 거쳐 완성도 높은 제품을 개발해 내놓지만, 스타트업 같은 소규모 조직에서는 자원이 제한적이어서 불가능하다.
  * 린스타트업은 기존 방식과 달리 신속한 피드백을 통한 제품 개발, 빠른 실험, 그 결과에 따른 실천을 빠르게 반복하는 것이 핵심이다.
  * 무의미한 지표에 의지하지 않고 실제 성과를 측정해 고객이 원하는 바에 집중하자는 것이다.”

###LINE의 경우
* 이미 대규모로 서비스 되고있다.
* 코딩에 많은 개발자들이 참여하고 있다.
* 강한 코드리뷰가 필요하다.

###Prototype의 경우
* Code Quality보다는 속도가 중요하다.
* 느슨한 코드 리뷰가 필요하다. (혹은 안한다)
* 다만 Branch 분리가 명확히 이루어져야한다.
* Code Quality가 낮은 Prototype 임을 모든 팀원이 숙지해야한다.

##Code Review in Google (Silicon Valley)

* 한명 혹은 그 이상이 코드 리뷰에 참여할 수 있다. 
* 어떤 사람들은 다른 사람들보다 더 강하게 리뷰하는 사람들이 있다.
* 리뷰는 코드를 완성하고 몇 분 혹은 몇 시간 이내에 진행되어야한다. 
* 리뷰는 내가 작성하지 않은 코드 변경에 대해서도 요청받을 수 있다.
* 조금이라도 막힌다는 느낌이 들면 직접 찾아가서 말로 한다. 
* 대화로 주고받은 내용은 반드시 리뷰시스템에 기록한다.
* 리뷰 요청을 받으면 가능하면 자기일보다 먼저 리뷰를 진행해준다.
* 최초 리뷰, 그리고 수정 리뷰 모두 
* 일반적인 룰은 24시간 안에 리뷰
* 대개 당일 리뷰해준다. 
* 리뷰가 늦어질 경우 리뷰어는 요청자에게 언제까지 리뷰해줄 것임을 알려준다.
* Comment는 최대한 친절하게 추가한다.
* Could you…, How about…, Please...
* 코딩 컨벤션은 철저히 지킨다.

##그럼 어떻게 해야할까?

1. Reviewer
1. Author

###Actions - Reviewer

* 코드에게는 불친절해도 Author에게는 친절해야한다.
  * Comments는 최대한 부드럽게 작성한다.
  * 코드를 사람과 일치시켜서 이야기하지 않는다.
  * BAD: 이렇게 이렇게 코드를 짜세요. 이건 아닌거같아요.
  * GOOD: 이렇게 저렇게 코드를 작성하는게 더 낫지 않을까요? 이런 코드는 어떠세요?
* 내 스타일을 고집하지 않는다.
  * 정해진 Style Guide는 지켜야한다.
  * Comment가 Code Quality 향상을 위한 것인지, 스타일의 차이인지 생각해본다.
* 논쟁으로 시간을 소모하지 않는다.
  * 타당한 Comment임에도 받아들여지지 않는다면 한두번 이야기해보시고 포기하자.
  * Code Quality가 떨어지는게 팀원들 사이에 감정이 상하는 것보다 낫다.
  * 깨진 유리창 이론 - https://ko.wikipedia.org/wiki/깨진_유리창_이론
    * 깨진 유리창 하나를 방치해 두면, 그 지점을 중심으로 범죄가 확산되기 시작한다는 이론으로, 사소한 무질서를 방치하면 큰 문제로 이어질 가능성이 높다는 의미를 담고 있다.
* Change List 범위가 아닌 것들에 대해서는 리뷰하지 않는다.
  * 기존 코드가 가지고 있는 문제에 대한 수정 요청하지 않는다.
  * 무리한 작업을 요청하지 않는다.
* 더 나은 디자인을 제안할 경우는 관련 문서를 Link해준다.
* 잘 한 부분은 칭찬의 Comment를 남긴다.
* 최종 결정은 Author가 한다.

###Actions - Author

* 좋은 P/R이 좋은 리뷰를 만든다.
* Reviewer는 할 일이 많다.
  * Coding Convention, Unit Testing, Error Handling, Resource, Thread Safe, Performance, Security, ...
  * Reviewer의 시간을 소중히 여겨야한다.
  * Reviewer를 지정하기전 먼저 셀프리뷰를 진행 
  * Reviewer로부터 Comment를 받으면 수정하겠다는 생각은 버려야 한다.
  * 내 시간이 소중한만큼 Reviewer의 시간도 소중히 생각해야한다.
  * 최대한 완성된 P/R을 요청 
* Analyzing이 아니라 Reading이 되도록 코드를 작성, 소스코드분석이 아니라 코드리뷰가 될 수 있도록 한다.
* 모아서 Review를 받기보단 지속적인 리뷰를 받는다.
  * 설계중에는 중간중간 지속적으로 Review를 받는다.
  * 리뷰시간은 1시간 이내로 가능하도록 한다.
  * 200-400 Line 언더로 요청한다.
* Change List의 디자인이 괜찮은지 점검한다.
  * Reviewer가 알아보기 쉽게 작성
  * 스펙과 설계에 대한 이해가 필요한 경우 Wiki 문서를 작성하여 P/R에 첨부한다. 
  * 1 CL 1 Function
    * 빠르고 명확한 리뷰가 가능 
    * Code 관리가 수월해짐 
* Reviewer 지정
  * 코드를 수정하였을 경우에는 해당 코드의 최종 커미터
  * Reviewer가 명확하지 않은 경우에는 이 코드를 제일 잘 짰을 것 같은 사람
  * 나와는 다르게 작성했을 것 같은 사람도 좋은 리뷰어
* Extra Space는 모두 제거하는게 좋다.
  * 바꾸지 않은 경우에도 바뀌었다고 나올 수 있다.
  * Xcode의 경우 White Space Trim을 켜두면 불필요한 라인 커밋을 줄일 수 있다.
  * ![Remove Extra Space in Xcode](https://github.com/rainris/RRSArticles/blob/master/Images/CodeReview/스샷%2024.png)
* 상의없는 코드재작성은 하지 않는다. (코드수정과는 다르다.)
  * 코드수정과 코드재작성은 다르다.
* 리뷰받고싶은 포인트에 미리 코멘트를 작성하는 것은 좋은 습관이다.
* 본인이 실수할 수 있다는 마음가짐을 갖는다.

##Reference Links

* http://blogs.atlassian.com/2010/03/code_review_in_agile_teams_part_ii/
* http://www.oracle.com/technetwork/issue-archive/2013/13-jan/o13upclose-1886634.html
* http://www.slideshare.net/krotondo/an-apple-a-day-8083652
* http://sv-story.blogspot.kr/2013/04/blog-post_28.html
* http://junoyoon.tistory.com/entry/구글의-QA-활동
* https://realgsong.wordpress.com/tag/코드-리뷰/
* http://www.zdnet.co.kr/column/column_view.asp?artice_id=20131223174623
* http://bcho.tistory.com/276
