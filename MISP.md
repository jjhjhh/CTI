## Malware Information Sharing Platform 개요

사이버 보안 지표를 포함한 위협 인텔리전스의 정보 공유를 돕는 무료 오픈소스 소프트웨어

표적 공격, 위협 인텔리전스, 금융 사기 정보, 취약점 정보 뿐만 아니라 테러 방지 정보를 수집, 공유, 저장

<br>

**목적**

보안 커뮤니티 및 해외에서의 구조화된 정보의 공유를 촉진하여 자동으로 중복 작업을 줄이는 것

<br>

**장점**

- MISP 는 플랫폼 간 정보 공유와 업데이트가 유용하다는 점에서 유연성이 높음
- 정보를 실시간으로 교환하면서 표적형 공격의 **탐지 속도**가 빨라지고, **탐지비율이
향상**되는 동시에 잘못된 긍정(거짓 긍정)도 감소
- 다른 조직이 이미 특정 악성코드를 분석했다는 것도 빨리 파악할 수 있기 때문에 유사한 악성코드를 되돌리는 것도 피할 수 있음

<br>


## MISP 설치

https://vm.misp-project.org/  에서 vmware 이미지 설치가 가능하다

나는 최신 버전인 [MISP_v2.4.158@3aad442-VMware.zip](mailto:MISP_v2.4.158@3aad442-VMware.zip) 를 설치해주었다 (상당히 오래걸린다)

스냅샷 찍고 VM 실행시키면 IP가 보인다


![Untitled (30)](https://github.com/user-attachments/assets/b4e61f8e-0617-452b-b2b3-7be5130a70ae)


<br>

IP address 에 적힌 주소로 이동하면 MISP 사이트가 뜬다 

<br>

![Untitled (31)](https://github.com/user-attachments/assets/e95e1388-042e-46eb-b717-b8a66dd0c875)


 [admin@admin.test](mailto:admin@admin.test) / admin 으로 로그인이 가능하다

<br>

### Event 추가

![Untitled (32)](https://github.com/user-attachments/assets/544c04c9-ec04-498d-b2c0-1725a7ae60d8)

### **Event 관련 위협 지표 추가**

Event Actions → List Event → ID 선택 → Attribute 추가
