# AWS-ELB-Node-Monitoring

Application Load Balancer는 트래픽에 따라 노드를 추가하거나 제거하며, 노드를 교체하기도 한다.<br>
노드를 교체할 때 트래픽의 이슈가 생겼던 경험을 바탕으로 ALB의 노드 교체 또는 추가를 모니터링하여 데이터를 수집한다면, 비정상 적인 노드 교체가 일어났을 때 알 수 있을 것이다. <br>
ALB 노드 모니터링 방법은 CloudTrail, AWS EventBridge, CloudWatch LogGroups을 사용하여 구성할 수 있다.<br>

ALB 모니터링 구성의 사전 조건은 CloudTrail 추적을 활성화 시킨 후 진행한다.<br>
![image](https://user-images.githubusercontent.com/43159901/168460777-3fc8d377-44cf-44c0-b0e4-ac4c7cf6e183.png)


EventBridge 구성 

![image](https://user-images.githubusercontent.com/43159901/168460803-5f14b35f-d5fe-4a26-9ad1-0d66684e1695.png)

ALB가 노드를 교체하거나 추가할 때, CreateNetworkInterface 이벤트가 발생하는 것을 기반으로 이벤트 패턴 생성
![image](https://user-images.githubusercontent.com/43159901/168462854-e98fc8ed-b48f-4c7b-bedc-d099ee3916d6.png)


이벤트 발생 시 CloudWatch LogGroups으로 전송하도록 설정
![image](https://user-images.githubusercontent.com/43159901/168461130-c72563c4-e225-4861-96f8-34d204b11744.png)



Test. ALB의 서브넷을 조정해보며 테스트 가능<br>
![image](https://user-images.githubusercontent.com/43159901/168461924-5fcec3d3-7ffb-46f0-8947-1a81614adfb8.png)

CloudWatch LogGroups 확인
![image](https://user-images.githubusercontent.com/43159901/168462233-321339c3-2c00-422a-b9c0-2291d68f7d85.png)




