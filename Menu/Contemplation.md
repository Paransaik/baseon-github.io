---
---
# About IP Camera
Update: 2020.6.25.

made by: Taeyeong, Jeong

## 1. 서론


### 가. 머리말
  사물인터넷 세상은 지능화된 사물들이 인터넷을 통해 연결되어 상호 소통하며, 지능화된 인프라와 서비스 기술을 제공하고, ICT(Information & Communication Technology)를 기반으로 모든 사물들이 초연결된 상태에서 정보를 공유하여 인간의 삶의 질을 높여주고 있다. 가트너에서 발간한 보고서에 보면 PC, Tablet, SmartPhone을 제외한 사물인터넷 기기가 2020년에 260억대에 달할것으로 전망되고, 맥킨지는 2025년까지 인류의 삶을 변화시킬가능성이 큰 기술을 사물인터넷 기술로 꼽고 있으며, 사물인터넷 기술이 모든 산업에 적용 될 것으로 전망하고 있다. 하지만 우리에게 다양한 편의만을 제공할 것 같은 사물인터넷의 발전은 효과성 뿐만아니라 그 밖의 다른 문제점이 예상된다. 정보통신 분야의 연장선상에서의 사물인터넷은 개인정보 침해나 해킹과 같은 사이버관련 범죄에 핵심적이고도 치명적인 매개가 될 수 있다. 나아가 매개체 뿐만 아니라 개인 실생활의 기반을 침해하는 범죄의 도구로써 활용될 가능성이 예상된다.

### 나. IP Camera
![Contemplation_1](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_1.png)

[그림1] CCTV, IP Camera 증감 추이

  IP Camera는 Camera 본체, Camera 모듈, CPU로 구성된 영상입력 장치와 디코더, 영상 입출력, 네트워크 전송 장치로 구성된 영상전송 장치로 디지털 비디오Camera의 일종이다. 아날로그 방식의 CCTV의 문제점인 저화질, 복잡한 배선, 비용 문제 등을 극복하여 별도의 DVR장치가 없더라도 손쉽게 영상을 녹화하고 캡처가 가능하다는 점과 어느 공간에서든 네트워크에 연결 할 수 있어서 실시간으로 영상을 모니터링과 제어가 가능하다는 점 등이 장점으로 부각되고있다. 이러한 장점들 때문에 기업들뿐만 아니라 최근 들어서는 홈오토메이션에 관심이 있는 가정, 어린아이들을 키우고 있는 가정, 몸이 불편한 노인이 있는 가정, 그리고 애완동물을 키우고 있는 가정들 사이에서도 IP Camera의 수요가 나날이 증가하고 있다. [그림1]에서 보듯이 아날로그 Camera에 비해 IP Camera의 증가 속도는 매우 빠른 속도로 늘어나고 있음을 알 수 있다[1].

---


## 2. 본론


### 가. 사례
  #. 2018년 6월, 미국 사우스 캐롤라이나에 거주나는 24살의 제이미 서밋은 어느 날 잠에서 깼을 때 베이비 모니터가 자신을 향해 있는 것을 발견했다. 그녀는 이상하게 생각했지만 넘겼다. 이후 아이에게 모유 수유를 하고 있는데 Camera가 자신을 향해 저절로 움직이는 것을 발견했다. 그제서야 서밋은 누군가 자신의 사생활을 엿보고 있다는 사실을 알아챘다.
  #. 2018년 11월. 국내에서 반려동물용 IP Camera를 해킹해 사생활을 엿보고 불법 촬영한 일당이 경찰에 적발됐다. 이들이 엿본 Camera는 2912대, 녹화 영상은 2만7328대에 달했다. 해커들은 반려동물 사이트를 통해 가정 IP Camera에 접속했다. 이후 3만9706회에 걸쳐 여성의 나체와 성관계 장면 등을 녹화했다[2].
  위 사례와 같이 국내 IP Camera 해킹 범죄가 최근 들어 급격히 증가하고 있는 추세이다. 수 십대의 IP Camera를 해킹한 20대가 징역을 선고 받기도 했으며, IP Camera 해킹을 통해 녹화한 성관계, 탈의실 영상 등을 버젓이 성인사이트 및 P2P사이트에 유포 및 판매한 범죄자들이 무더기 입건되기도 하였다. 뿐만 아니라, 중국 한 사이트에선 자신들이 해킹한 IP Camera를 국가와 장소별로 분류하여 이를 실시간 영상송신 및 구글맵 서비스와 연계해 상세주소까지 제공하고 있어 피해가 더욱 증가될 것으로 판단된다[3].

### 나. 해킹 사고 배경
[표1] IP Camera 취약 제품 수
![Contemplation_2](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_2.png)

  한국인터넷진흥원에 따르면 우리나라에 유통 중인 IP Camera 53개 제조사, 400개 제품을 대상으로 공장 출하 시 초기에 설정된 ID 및 비밀번호의 취약점을 조사한 결과, 국내 제품인 경우 48개 제품, 해외 제품인 경우 78개 제품에서(총 31.5%) 보안취약점이 발견됐다고 전했다. 실제 국내에서도 IoT 보안 취약점 신고 및 조치 건수가 해마다 증가하고 있으며, 이로 인해 IP Camera에서 수집된 다양하고 수많은 데이터들이 개인정보 유출로 인한 프라이버시 침해를 낳고 있어 현재 다양한 사회적 문제가 발생하고 있다[4]. 이는 사용자들의 보안 인식이 턱없이 부족해 전문가가 아니더라도 손쉽게 프로그램과 사이트를 이용하여 해킹이 가능하기 때문인 것으로 사료된다.

### 다. 원인
![Contemplation_3](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_3.png)

[그림2] 보안사고 발생 원인

  IP Camera 및 보안사고 발생 원인의 핵심적인 요인은 개별 이용자의 미숙이라는 응답이 40.10%이고 정보시스템의 취약성이라는 응답이 38.02%로, 이 두 가지가 가장 주요한 요인으로 꼽혔다. 그 밖에 정보시스템 운용자의 역량 부족이라는 응답이 8.85%, 정보보호제품 및 서비스의 성능 부족이라는 응답이 6.77% 등의 순으로 나타났다. 실무적 관점에서 사고 발생 시 가장 긴급하게 수행되어야 할 활동은 복구가 35.42%로 가장 많은 응답률을 보였고, 관계기관 신고와 내부 전파가 동일하게 17.19%, 기관장 보고가 14.06% 등으로 그 뒤를 이었다[5].

### 라. 해킹 방법
#### 1) Angry Ip Scanner 다운로드
![Contemplation_4](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_4.jpg)

[그림3] Angry Ip Scanner
  
  Angry Ip Scanner는 매우 강력한 GUI 포트 스캐너로 모든 OS서 사용 가능하다.

#### 2) IP 주소 범위를 선택
![Contemplation_5](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_5.jpg)

[그림4] My IP

  IP Camera 해킹에 적합한 IP 주소 범위를 선택하는 방법이 중요하다. IP Camera는 광대역 인터넷 연결로 연결된다. Google 또는 Bing 검색 창에 'My ip'를 입력하면 IP 주소가 표시된다. 사진에 나온 IP는 이다. 따라서 IP 범위는 77.247.181.1~77.247.181.255이다.

#### 3) IP Camera 해킹을위한 Angry Ip 구성
![Contemplation_6](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_6.jpg)

[그림5] Angry Ip 구성

  도구> 환경 설정> 포트, 포트 선택 탭에서 80, 8080, 23 포트를 추가하고 스캔한다.
  
![Contemplation_7](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_7.jpg)

[그림6] Angry Ip Web Detect

  또, 도구> 가져 오기> 웹 감지 추가로 이동하여 IP Camera 모델명, 이름, 라우터 이름 또는 라우터 모델 이름를 웹 감지에 추가(<<) 해준다.

#### 4) IP 범위 스캔
![Contemplation_8](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_8.jpg)

[그림7] IP Range scan

  IP 범위 탭에서 IP 범위를 추가하고 시작을 클릭한다. 스캔이 완료되면 검색된 IP Camera 와 IP 주소를 브라우저의 Enter 키에 복사한다.

#### 5) 기본 사용자 이름 및 비밀번호
  대부분의 IP Camera와 라우터는 다음과 같은 기본값을 사용하고 있다.
사용자 이름: admin | 비밀번호: 공백
사용자 이름: admin | 비밀번호: 12345
사용자 이름: admin | 비밀번호: 9999
이 외에 인터넷에 검색해본다면 더 많은 사용자 아이디, 비밀번호를 검색할 수 있다.

#### 6) Hydra를 사용하여 IP Camera 암호 해독
![Contemplation_9](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/Contemplation_9.jpg)

[그림8] Hydera

  기본 암호가 작동하지 않으면 암호를 해독해야한다. 암호 해독에는 Hydra를 사용한다. Kail linux를 열고 다음 구문을 입력한다.
  
    # hydra -s 80 -l admin -P /root/Desktop/wl/cctvpass.txt -e ns -t 16 targetIP http *
    
다음 구문에는 아래와 같은 뜻이 있다[7].

- s: 80 포트 번호
- l: admin-기본 로그인 이름
- P: /root/desktop/worldlist.txt 브루트포싱을 위한 워드 리스트
- e: empty 패스워드
- ns: 빈 패스워드로 로그인 시도
- http: 공격을 하려는 포트 이름

### 마. 해킹을 막을 수 있는 방안
#### 1) Camera 펌웨어 업데이트
  대부분의 최신 IP 보안 Camera는 사용자가 업그레이드할 수 있는 펌웨어를 갖추고 있다. 보안 취약성이 발견되면 IP 보안 Camera 제조업체에서 펌웨어 업데이트를 실행하여 취약성을 수정하는 경우가 많다. 보통 관리 콘솔에서 웹 브라우저를 통해 Camera 펌웨어를 업데이트할 수 있다.

#### 2) Camera를 로컬로 유지
  개인 정보 보호가 최우선이라면 Camera를 로컬 네트워크에 유지하고 경로 지정이 불가능한 내부 IP 주소(예: 192.168.0.5 또는 이와 유사한 주소)를 할당해야 한다. 라우팅할 수 없는 IP 주소를 사용하더라도 포트 포워딩을 설정하거나 UPNP를 사용하여 Camera를 인터넷에 노출하는 소프트웨어에 의해 Camera가 노출될 수 있다.

#### 3) Camera에 암호 할당
  많은 IP Camera에는 기본적으로 암호 보호 기능이 설정되어 있지 않다. 그러나 일부 사람들은 초기 설정 후에 암호 보호를 추가하는 것을 잊어버리고 결국 모든 사람이 접근할 수 있도록 Camera를 활짝 열어둔 채 내버려둔다. 대부분의 Camera는 최소한 어떤 형태의 기본 인증을 제공한다. 그것은 안전하지는 않을지 모르지만 적어도 전혀 없는 것보다는 낫다. 사용자 이름과 암호를 사용하여 Camera를 보호하고 주기적으로 변경해야 한다.

#### 4) 기본 관리자 계정 이름 변경 및 새 관리자 암호 설정
  제조업체에서 설정한 Camera의 기본 관리자 이름과 암호는 일반적으로 웹 사이트를 방문하여 Camera 모델의 지원 부분으로 이동하면 사용할 수 있다. 관리자 이름과 암호를 변경하지 않으면 가장 초보적인 해커라도 기본 암호를 검색하여 Camera를 제어할 수 있다.

#### 5) IP Camera를 집안에 배치하지 말 것
  집 안에 IP 보안 Camera를 두지 않는다. 가능한 한 모든 방법으로 Camera의 보안을 확보했다고 생각하더라도 제조사가 아직 찾지 못한 제로 데이 취약성에 의해 사각지대에 놓일 가능성은 항상 존재한다[7].

---

## 3. 결론


### 가. 맺음말
  IP Camera의 수요가 증가함에 따라 국내 이용자들의 피해도 커지고 있으므로, 정부에서도 최근 IoT 보안 인증 서비스를 시행했다. 과기정통부에 따르면 최근 사이버공간의 복잡성, 초연결성 등으로 인해 해커들의 공격기법은 정교화, 다양화되고 있지만, 기업의 보안관리 수준과 대응체계는 이를 따라가지 못하고 있어 침해사고가 지속해서 발생하고 있다. 이처럼 기업 대상의 사이버 공격 활동들은 지속해서 고도화되고 있어, 전통적인 보안 체계의 한계를 극복할 수 있는 대응활동이 요구된다고 과기정통부는 강조했다. 하지만 이것들은 기업에 대한 대책일 뿐 소비자 개개인 스스로 IP Camera에 대해 이해하고 관리가 필요하다. 
  소비자들은 CCTV와 달리 값도 저렴하고 네트워크와 연결돼 PC와 스마트 폰을 통해서 실시간 조회 및 제어를 할 수 있는 IP Camera 사용을 채택했고, 이에 따라 해킹을 통한 사생활 침해 문제도 같이 증가하고 있다. 이 장치들은 24시간 내내 인터넷 송수신 데이터와 연결돼 있으며, 이 장치 중 하나에서 발생하는 보안 침해나 사생활 노출은 공포 영화보다 더 많은 악몽을 초래할 수 있다. 이는 사용자들의 보안 인식이 턱없이 부족해 전문가가 아니더라도 손쉽게 프로그램과 사이트를 이용하여 해킹할 수 있기 때문으로 생각한다. 
  이처럼 보안사고 발생 요인 중 가장 큰 원인이 개별 이용자의 미숙인 만큼 개개인의 정보보호 인식제고가 중요하다. 온 국민이 다 함께 정보보호를 실천하고 건강한 사이버 방역체계를 만들어 보안사고를 예방해야 한다. 아직 해결해야 할 과제가 많이 남아 있지만, 사용자는 보안 없는 IoT 기기의 위험을 알고 원치 않는 노출을 방지하기 위해 깨어있는 소비자가 되는 것이 바람직하다.

---


## 4. 참고문헌


### 가. 국내 논문
[1] Hong Soon Ho, "IP Camera Market and Trend in the Video Security Industry", REVIEW OF KIISC, Vol. 20, No. 3, pp. 18-23, 2010.

[3] Sang Hoon Han, "IP Camera Hacking Analysis And Measure", Vol. 26, No. 1, pp. 1, 2018

[5] National Information Protection White Paper, 305p, 2019

### 나. 인터넷 사이트
[2] Dong-A news, www.donga.com/news/View?gid=93988191&date=20190205, 2020. 6. 27.

[4] Metroseoul news, www.metroseoul.co.kr/article/2018101500175, 2020. 6. 27.

[6] How to hack, null-byte.wonderhowto.com/forum/hack-cctv-private-cameras-0159437, 2020. 6. 27.

[7] Secure your ip security cameras, www.lifewire.com/secure-your-ip-security-cameras-2487488, 2020. 6. 27.
