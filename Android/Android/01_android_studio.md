# 안드로이드 스튜디오 투어

## Manifests
> 앱의 지도 역할, 어떤 화면이 있는지 어떤 기능을 하는지 나타낸다.  

![image](https://user-images.githubusercontent.com/86659995/130260079-eb796c82-fc26-444a-99f9-0821500d1613.png)

#### package
앱의 이름, 앱을 구분하는 용도로 쓰이기때문에 패키지명은 고유해야 한다.

#### \<application>~\</application>
앱에 대한 내용들을 적어놓는 곳

#### allowBackup
true로 설정해놓으면 앱을 삭제하더라도 지정된 내용들은 저장되어 재설치시 복구된다.

#### label 
앱 이름

#### roundIcon
휴대폰마다 앱을 그리는 모양이 다른데 둥근 모양을 그릴 때 이 이미지를 참조한다

#### supportRrl
글을 오른쪽에서 왼쪽으로 읽는 지역에서 사용된다, right to left

#### theme
style은 앱의 기본값들을 모아놓은 것이다

#### launcher
activity를 런처(앱을 켜자마자 나오는 화면)로 만들어주는 속성
