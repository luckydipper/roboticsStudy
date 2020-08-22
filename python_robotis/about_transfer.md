# 통신 방법에 대하여.

1. XMLRPC
(xml : adgasghasfhasfg. RPC : Remote Procedure Call )
처음에 소개팅 담당자인 master node는 name server(도메인 만들어)와 같은 역할을 한다.<br>
필요할 때만 접속하여 정보를 등 요청하여 수신받을 수 있다.록 평상시에는 접속상태 점검하지 않음. 동기적. 다양한 언어를 지원함. 가벼움.<br>
XML-RPC란, RPC 프로토콜의 일종으로서, 인코딩 형식에서는 XML을 채택하고, 전송 방식에서는 HTTP 프로토콜을 사용하고 있다.<br>
<img src="https://t1.daumcdn.net/cfile/tistory/15161F404E639B0830">

2. TCP IP (소켓 통신?)
(Transmission Control Protocol)
호스트 : 응용프로그램을 수행하는 주체
라우터 : 호스트에서 생성된 데이터를 여러 네트워크를 거쳐 전홍함. 서로 다른 네트워크에 속한 호스트간의 데이터 교환할 수 있게 해주는 장비.

노드(인터넷 연결된것 허브랑,모뎀(복호화암호화 역할, 라우터와 다름) > 호스트(ip를 갖고 인터넷 연결하는거) > 서버<br>
포트와 소켓은 다르다. 앚기 와닿지 않는다. 구글링 필요!<br> 
hw -> kernel ->shell -> aplication<br>

* IP address
IP는 사실, 32자리로 이루어진 2진수. xxx.xxx.xxx.xxx
IP주소의 사용이유는 각각의 Host들을 구분하기위해 사용된다.

	- 내부 ip주소 : 공유기로 부터 할당받은 IP address
	- 공인 ip주소 : 인터넷을 되게 해주는 실제 IP address

	ip에는 여러가지 class가 존재한다. 컴퓨터에는 각자 ip가 할당되어 있다. 이 아이피는 유동적으로 변한다. DHCP(dynamic host configuration protocol) Server를 이용해서 전원이 켜져 있는 컴퓨터에만 IP를 할당하고, 꺼지면 회수한다.<br>
한 컴퓨터에 여러 개의 NIC(Network Interface Card / 흔히 랜카드라 불리는 장치)를 장착하여 여러 개의 IP를 사용하는 형태


	* 논리적 주소 체계
		ㅁㄴㅇㄹ
	
	* 물리적 주소 체계
		MAC (Media Access Control) 주소. MAC address는 LAN(Local Area Network) 또는 Ethernet 이라 불리는 망에서 통신을 하기 위하여 사용된다.

	+ network id
		Network의 범위를 지정하여 관리하기 쉽게 만들어 낸 것입니다
	+ host ID
		Host ID는 호스트들을 개별적으로 관리하기 위해 사용하게 된 것입니다
따라서 우리가 인터넷을 사용할 때 Routing으로 목적지를 알아내고 찾아가는 등의 역할을 할 때에는 NetworkID와 HostID가 합쳐진 IP주소를 보게 됩니다.<br>

IP Class의 경우 A, B, C, D, E Class로 나누어 Network ID와 Host ID를 구분하게 됩니다. <br>
<img src ="https://2.bp.blogspot.com/-VWm-qwzH5I8/Vm0_vc2F4tI/AAAAAAAAAKE/ccxmdlSrwVQ/s640/IP%25EC%25A3%25BC%25EC%2586%258C%2B%25EC%25B2%25B4%25EA%25B3%2584.png">
IP 주소에서 쓸  수 있는 숫자의 범위는 0~255로 되어 있기에 첫 번째 Octet에서 0~255까지의 숫자를 5개로 나누어서 A, B, C, D, E Class로 구분 되는 것입니다.

    A Class : 0 ~ 127 (0.0.0.0 ~ 127.255.255.255)
    B Class : 128 ~ 191 (128.0.0.0 ~ 191.255.255.255)
    C Class : 192 ~ 223 (192.0.0.0 ~ 233.255.255.255)
    D Class : 224 ~ 239 (224.0.0.0 ~ 239.255.255.255)
    E Class : 240 ~ 255 (240.0.0.0. ~ 255.255.255.255)

<a href = "http://korean-daeddo.blogspot.com/2015/12/ip.html">click link</a>


2. 인터넷의 원리
라즈베리파이에서 아이피를 고정하기 위해 설정하던 중, ip고정하기 위한 라우터와 dns ip에 대해서 궁금증이 생겼다. <br>
특히 dns는 도메인을 연결하는 것인데, 서버를 등록하면서 자동으로 해주는 것으로 알고 있었는데, dns에 ip?? 이런 궁금증이 생겼다.<br>
인터넷이 연결되면, dcpd(dynamic host configuration protocol)에 의해서 자동으로 인터넷 ip를 주고, nds ip 서버와 연결해 준다.<br>
<img src = "https://s3-ap-northeast-2.amazonaws.com/opentutorials-user-file/module/3421/8338.jpeg"><br>
여기서 도메인을 나누어지는데 각 나누어지는 부분마다 담당하는 도메인 서버가 다르다.
<img src = "https://s3-ap-northeast-2.amazonaws.com/opentutorials-user-file/module/3421/8343.jpeg"><br>
내 컴퓨터에서 host에서 dns 도메인을 먼저 확인한다. 1순위로 확인한다. 그런데 host에 모든것을 저장하는 것은 불가능하다.(잘 못 설정하면 피싱을 당할 수 있다.) 그래서 인터넷을 연결함과 동시에 dhcp에서 동적인 아이피중 하나를 주고, 공용 dns서버에 연결시켜준다. 이걸 통신사가 맡는다. kt, lg-u+, google 이 도메인 서버를 맡는다. 여기서 root name서버에게 물어보고, root name서버에서 top-lever서버에 대한 정보를, top-level 서버에서 sub level 서버의 정보를 얻는다. sublevel에 서버의 ip가 등록되어있다.



3. putty vnc


4. ssh <- 다름 -> ssl 인증서
(security shell prompt)<br>
서버와 클라이언트가 안전하게 소통할 수 있도록, public key와 private key가 존재한다. public key로는 인코딩 가능하고, private key로 디코딩 한다.
SSH ternnel

5. IP란?
Linux OS에서,```$ ifconfig```를 쳐보면 나옴.<br>
네트워크 환경에서 컴퓨터 노드간 통신하기 위한 네트워크 주소.<br>
<a href="https://limkydev.tistory.com/167">https://limkydev.tistory.com/167</a>
<a href="https://velog.io/@hidaehyunlee/IP-address%EB%9E%80">https://velog.io/@hidaehyunlee/IP-address%EB%9E%80</a>
하스팟에서 192.168은 네트워크 주소임. 43.28을 호스트 주소라고 함.
ABC class


cpu<br>
c코어 쓰레드<br>
핑<br>
port<br>
redirect<br>

## 우분투에 ROS 설치하는 법.
sudo sh -c 'echo "http://" > /etx/apt'.<br>
sh -c에서 sh는 interpreter를 호출, /bin/dash에 연결되어있음.
-c 플래그는 표준 입력 대신 command_string 피연산자에서 명령을 읽는다. 프로그램이 해석한 대로.
- ex
```
sudo sh -c\
'echo "deb http://asdfasdf" > \
/etc/apt/sources.list.d/ros-lastest.list'
```
```
$ python3 -c print (35/7)<br>
bash: syntax error near unexpected token `('<br>
$ python3 -c 'print (35/7)'<br>
5.0<br>
```
bash는 shell의 한 종류이다. shell은 os와 이야기할 때 쓰이는 cmd창 같은것이다. bashrc는 bash에서 처음 지정된 것을 모아놓은 것이다. 그러므로 이곳에서 환경변수 설정을 할 수 있다. window에서 쓰는 comend랑 dos가 shell에 해당한다.<br>
환경변수는 컴퓨터 shell창에서 컴퓨터가 모든 곳을 찾아보는 것은 비효율적이다. 그러므로 환경변수에 지정된 곳을 확인하라고 하는 것이다.<br>


아직까지는 과정만 살펴보았고, 조금 헷갈린다.
apt-key 설정 <br>
apt-get update<br>
install ros  full로, <br>
ros rosdep init??<br>
환경 설정 echo "source /opt/ros/ ..... .... ..... bashrc<br>
API 잘 이해가 안감. 모바일 앱 개발이 하드워어나 그런거 몰라도 API를 제공한다. Hardware는 통합되어 있음.
kernel
UDP???
