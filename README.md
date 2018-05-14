# Azure 101 IaaS, PaaS 기초

### IaaS: Azure 사용의 기초가 되는 Virtual Machine 배포부터, Load Balancer를 이용한 Load Balancing의 기본 실습을 다룹니다.

### PaaS: Web app 생성 및 Flask Hello World 예제를 배포해봅니다.

#### VM 생성

1. Azure Portal에서 New resource 선택후 Ubuntu 혹은 Windows Serve OS 선택하여 생성. 

    - 리소스 그룹: 논리분류그룹 
    - 가용성집합(availability set): Load Balancer 실습을 위해 생성
    - 기타 설정 그대로

2. 동일한 spec의 VM을 생성하며, 1번에서 생성했던 리소스그룹/가용성집합 선택
3. Load Balancer(부하분산장치) 새로 생성 
    - Public (공용) IP 사용 설정
    - 리소스그룹은 동일하게
    - 세부 메뉴에서 Backend Pool (백 엔드 풀) 추가
        - '가용성집합'에 연결, 위의 가용성집합 선택
        - 추가된 Backend Pool 이름을 클릭하여 대상 네트위크 IP 추가, 2대 VM의 네트워크 선택추가
    - 세부 메뉴에서 상태 프로브 선택/추가
        - 기본값으로 '확인'
    - 세부 메뉴에서 부하 분산 규칙 선택/추가
        - 기본값으로 '확인'
    - Load Balancer의 IP 확인

4. PaaS Web App

    https://docs.microsoft.com/en-us/azure/app-service/app-service-web-get-started-python  

    - 생성한 Web App의 세부 메뉴에서 'Advanced Tool' 선택
    - 우측화면에서 'Go' 클릭
    - 상단 메뉴에서 'Debug Console' > 'CMD' 혹은 'PowerShell' 선택
