# Android_interview
안드로이드 면접 대비 정리

<br>

## Android
* 안드로이드 4대 컴포넌트 <br>

### Activity
   
액티비티는 사용자 인터페이스를 화면을 관리하는 컴포넌트이다.

<br>

#### Activity LifeCycle
<br>
<br>
<img src="https://kairo96.gitbooks.io/android/content/pic2/2-4-1-1.jpg" width="70%" height="70%"></img><br/>
<br>

|    메소드   |                                                            설명                                                           |          다음 메소드         |
|:-----------:|:-------------------------------------------------------------------------------------------------------------------------:|:----------------------------:|
| onCreate()  | 액티비티가 생성될 때 호출되며 사용자 인터페이스 초기화에 사용됨.                                                          | onStart()                    |
| onRestart() | 액티비티가 멈췄다가 다시 시작되기 바로 전에 호출됨.                                                                       | onStart()                    |
| onStart()   | 액티비티가 사용자에게 보여지기 바로 직전에 호출됨.                                                                        | onResume() 또는 onStop()     |
| onResume()  | 액티비티가 사용자와 상호작용하기 바로 전에 호출됨.                                                                        | onPause()                    |
| onPause()   | 다른 액티비티가 보여질 때 호출됨. 데이터 저장, 스레드 중지 등의 처리를 하기에 적당한 메소드.                              | onResume() 또는 onStop()     |
| onStop()    | 액티비티가 더이상 사용자에게 보여지지 않을 때 호출됨. 메모리가 부족할 경우에는 onStop() 메소드가 호출되지 않을 수도 있음. | onRestart() 또는 onDestroy() |
| onDestroy() | 액티비티가 소멸될 때 호출됨. finish() 메소드가 호출되거나 시스템이 메모리 확보를 위해 액티비티를 제거할 때 호출됨.        | 없음                         |
<br>

* onCreate() : Activity가 생성될 때 최초로 한번 불림(초기화 작업 이용), 보관 상태의 Activity가 있는 경우, Bundle을 받아서 사용됨
* onRestart() : onStop()이 불린 후, 다시 시작하기 전에 불림
* onStart() : 사용자에게 Activity가 보여지기 직전에 호출됨 
* onResume() : focus를 얻기 위해 불림. 사용자와 상호작용하기 직전에 호출되며, 스택의 최상단에 위치함
* onPause() : 다른 Activity가 활성화될 때 호출됨 => ex) 알람, 전화 : onPause()
* onStop() : 기존 Activity가 완전히 가려지면 호출됨 
* onDestroy() : Activity가 완전히 삭제되기 직전에 불림

<br>

### Service

Service는 화면없이 백그라운드에서 실행되는 프로세스를 의미한다. <br>
Service는 총 두가지로 분류할 수 있는데, 로컬 서비스와 원격 서비스(bind)로 구분할 수 있다.<br>
원격 서비스의 경우, 같은 기기에 실행되고 있는 다른 애플리케이션에서 서비스를 실행할 수 있다.

#### 로컬 서비스
* onCreate() : 서비스 생성시 호출
* onStart() : startService()에 의해 서비스가 시작될 때마다 호출
* onDestroy() : 서비스가 종료될 때 호출

#### 원격 서비스
* onCreate() : 서비스 생성시 호출
* onBind() : bindService()에 의해 서비스가 시작될 때 호출
* onUnbind() : 서비스와 연결이 끊겼을 때 호출
* onDestroy() : 서비스가 종료될 때 호출

<br>

#### Service LifeCycle
<br>
<br>
<img src="https://kairo96.gitbooks.io/android/content/pic2/2-5-1-1.jpg" width="70%" height="70%"></img><br/>
<br>

<br>

### BroadCast Receiver

BroadCast Receiver는 사용자 인터페이스를 가지고 있지 않다. 전역인 이벤트를 받는 컴포넌트이다. <br>
예를 들어 시간대 변경, 배터리 부족, 언어 설정 변경 들이 있고 이를 BroadCast Receiver가 처리한 후 다시 대기 모드로 진입한다.

<br>

### Content Provider

Content Provider는 애플리케이션 간의 데이터 공유를 위한 인터페이스를 제공하는 컴포넌트이다. <br>
Content Provider가 제공하는 실제 데이터는 파일 시스템이나 데이터베이스 등에 있을 수 있다. 

<br>
<img src="https://kairo96.gitbooks.io/android/content/pic2/2-7-1.jpg" width="70%" height="70%"></img><br/>

<br>

