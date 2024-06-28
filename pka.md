# 2017 정보통신과 네트워크 경진대회

1. 기본 구성

- 모든 라우터의 이름 변경(R3는 IOS 이미지 파일 복구 후에, R5는 잠겨있음)
- 라우터에서 **configuration 모드**로 들어가서 **hostname** 을 통해 라우터의 이름 변경

2. IP 주소 할당

- PC는 서브넷의 첫 번째
- Server는 서브넷의 10 번째
- default gateway는 서브넷의 마지막
(서브넷팅은 각자 하세요)

3. R1 라우터의 Gig0/0 포트에 description 설정
- This is Private Network 로 설정
- 라우터에서 **interface GigabitEthernet0/0** 으로 들어가서 **description This is Private Network** 로 description 설정

4. R3 라우터에 배너 설정
- Check your access permissions. 로 설정
- 라우터에서 **configuraion 모드** 에서 **banner motd ?Check your access permissions.?** 로 설정
(? 자리에는 다른 특수문자도 넣을 수 있음)

5. R2, R3, R4, R7에 **2017yyent** 라는 secret 사용
- 각 라우터의 **configuration 모드** 에서 **enable secret 2017yynet** 으로 비밀번호 설정

6. R1, R4, R8, R9에 username 설정
- 각 라우터의 **configuration 모드** 에서 **username {라우터의 hostname} password Skills39@@** 로 설정