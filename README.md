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

### Service
### Content Provider
### BroadCast Receiver
