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

* IP address
	- 내부 ip주소 : 공유기로 부터 할당받은 IP address
	- 공인 ip주소 : 인터넷을 되게 해주는 실제 IP address

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

아직까지는 과정만 살펴보았고, 조금 헷갈린다.
apt-key 설정 <br>
apt-get update<br>
install ros  full로, <br>
ros rosdep init??<br>
환경 설정 echo "source /opt/ros/ ..... .... ..... bashrc<br>
API 잘 이해가 안감. 모바일 앱 개발이 하드워어나 그런거 몰라도 API를 제공한다. Hardware는 통합되어 있음.

