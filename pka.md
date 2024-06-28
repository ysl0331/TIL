# 2017 정보통신과 네트워크 경진대회

## 1. 기본 구성

- 모든 라우터의 이름 변경(R3는 IOS 이미지 파일 복구 후에, R5는 잠겨있음)
- 라우터에서 **configuration 모드**로 들어가서 **hostname** 을 통해 라우터의 이름 변경

## 2. IP 주소 할당

- PC는 서브넷의 첫 번째
- Server는 서브넷의 10 번째
- default gateway는 서브넷의 마지막
(서브넷팅은 각자 하세요)

## 3. R1 라우터의 Gig0/0 포트에 description 설정
- This is Private Network 로 설정
- 라우터에서 **interface GigabitEthernet0/0** 으로 들어가서 **description This is Private Network** 로 description 설정

## 4. R3 라우터에 배너 설정
- Check your access permissions. 로 설정
- 라우터에서 **configuraion 모드** 에서 **banner motd ?Check your access permissions.?** 로 설정
(? 자리에는 다른 특수문자도 넣을 수 있음)

## 5. R2, R3, R4, R7에 **2017yyent** 라는 secret 사용
- 각 라우터의 **configuration 모드** 에서 **enable secret 2017yynet** 으로 비밀번호 설정

## 6. R1, R4, R8, R9에 username 설정
- 각 라우터의 **configuration 모드** 에서 **username {라우터의 hostname} password Skills39@@** 로 설정

## 7. R5의 정보 확인
- R4에서 R5와 연결된 시리얼 포트(**Serial 0/0/0 or Serial 0/0/1**)로 들어가서 **cdp enable** 로 cdp 활성화
- 그리고 나서 **configuration 모드** 에서 **cdp run** 입력
- 마지막으로 **privilege 모드** 에서 **show cdp neighbors** 과 **show cdp neighbors detail** 입력해서 R5의 정보 확인

## 8. 모든 시리얼 포트의 clock rate 는 64000
- 라우터와 연결된 모든 시리얼 포트로 들어가서 **clock rate 64000** 입력