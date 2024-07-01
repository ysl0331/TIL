# 2017 정보통신과 네트워크 경진대회

## 1. 기본 구성

ex)

Router>enable

Router#configure terminal

Router(config)#**hostname R1**

R1(config)#

## 2. IP 주소 할당

- PC는 서브넷의 첫 번째

- Server는 서브넷의 10 번째

- default gateway는 서브넷의 마지막

(서브넷팅은 각자 하세요)

## 3. R1 라우터의 Gig0/0 포트에 description 설정

- This is Private Network 로 설정

R1>enable

R1#configure terminal

R1(config)#interface GigabitEthernet0/0

R1(config-if)#**description This is Private Network**

## 4. R3 라우터에 배너 설정

- Check your access permissions. 로 설정

R3>enable

R3#configure terminal

R3(config)#**banner motd ?Check your access permissions.?**

(? 자리에는 다른 특수문자도 넣을 수 있음)

## 5. R2, R3, R4, R7에 **2017yyent** 라는 secret 사용

ex)

R2>enable

R2#configure terminal

R2(config)#**enable secret 2017yynet**

## 6. R1, R4, R8, R9에 username 설정

ex)

R1>enable

R1#configure terminal

R1(config)#**username R1 password Skills39@@**

## 7. R5의 정보 확인

R4>enable

R4#configure terminal

R4(config)#interface Serial0/0/1

R4(config-if)#**cdp enable**

R4(config-if)#exit

R4(config)#**cdp run**

R4(config)#exit

R4#**show cdp neighbors**

R4#**show cdp neighbors detail**

(안되면 아래 두 가지 반복해보고 packet tracer 껐다 켜보기)

## 8. 모든 시리얼 포트의 clock rate 는 64000

ex)

R2>enable

R2#configure terminal

R2(config)#interface Serial0/0/0

R2(config-if)#**clock rate 64000**

(반대쪽 포트에서 clock rate 설정하면 안되는 걸로 알고 있으니 
안되면 반대쪽이 된걸로 생각하세요)

## 9. 토폴로지에 나온대로 VLAN 설정

ex)

SW1>enable

SW1#configure terminal

SW1(config)#**vlan 10**

SW1(config-vlan)#**name chrome**

## 10. SW3, SW4 이더채널 구성하기

ex)

SW3>enable

SW3#configure terminal

SW3(config)#interface range fastEthernet 0/23-24

SW3(config-if-range)#**channel-protocol pagp**

SW3(config-if-range)#**channel-group 1 mode desirable**

## 11. IOS 이미지 파일 복구

SW2 설정

SW2>enable

SW2#configure terminal

SW2(config)#interface fastEthernet 0/1

**SW2(config-if)#spanning-tree portfast**

R3 설정

**rommon1 > IP_ADDRESS=2.5.2.254**

**rommon2 > IP_SUBNET_MASK=255.255.255.0**

**rommon3 > DEFAULT_GATEWAY=2.5.2.10**

**rommon4 > TFTP_SERVER=2.5.2.10** 

**rommon5 > TFTP_FILE=c2800nm-advipservicesk9-mz.124-15.T1.bin**

**rommon6 > tftpdnld**

(ALT + d 로 넘긴 후)

**rommon7 > boot**

(ALT + d 로 넘긴 후)

**~~(대충 뭐라고 질문하는 문장) : no**

## 12. 라우팅 설정

ex)

R1>enable

R1#configure terminal

**R1(config)#router rip**

**R1(config-router)#version 2**

**R1(config-router)#network 10.0.0.0**

**R1(config-router)#network 1.1.2.0**

## 13. WAN 설정

ex)

R8>enable

R8#configure terminal

R8(config)#interface Serial 0/0/1

R8(config-if)#**encapsulation ppp**

R8(config-if)#**ppp authentication chap**

## 14. port security

SW6>enable

SW6#configure terminal

SW6(config)#interface fastEthernet 0/2

SW6(config-if)#**switchport port-security**

SW6(config-if)#**switchport port-security violation shutdown**

## 15. R6 비밀번호 복구

- 일단 R6 라우터의 전원을 껐다 킨 다음 **ctrl + pause/break** 키로 rommon 모드 진입

rommon1 > **confreg 0x42**
rommon2 > **boot**

- 부팅이 끝나면 라우터는 초기화 상태임

Router>enable
Router#**copy startup-config running-config**
R6#configure terminal
R6(config)#

(여기서 알아서 비밀번호 설정하세요)

## 16. login block

R3>enable

R3#configure terminal

R3(config)#**login block-for 30 attempts 3 within 60**