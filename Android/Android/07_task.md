# Task

Activity와 비슷한 개념, Activity는 Stack으로 관리가 된다
Stack는 햄버거처럼 아래에서 위로 task가 쌓이는 것을 의미

* 켜지는 방법을 자체 속성으로 가지고 있는 경우 - LaunchMode
* 켜지는 방법을 지시하는 경우 - IntentFlag

| LaunchMode| 다중허용 |
|-----------|----------|  
| Standard | O | 
| singleTop | 조건부 -> 열고자 하는 Activity가 현재 Activity라면 onNewIntent를 호출 | 
| singleTask | X | 
| singleInstance | X | 

<img src="https://user-images.githubusercontent.com/86659995/130602809-7aa3403c-7949-48a4-8bd2-c50b55f07775.png" width="200" height="400"/>

#### 인텐트 플래그
FLAG_ACTIVITY_NEW_TASK  
FLAG_ACTIVITY_SINGLE_TOP  
FLAG_ACTIVITY_CLEAR_TOP

정말 필요하지 않은 이상 런치모드와 인텐트 플래그는 변경하지 않는 것이 좋다

> 참고 - [Android Developers, 작업 및 백 스택 이해](https://developer.android.com/guide/components/activities/tasks-and-back-stack?hl=ko)
