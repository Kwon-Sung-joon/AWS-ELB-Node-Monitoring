# AWS-ELB-Node-Monitoring

Application Load Balancer는 트래픽에 따라 노드를 추가하거나 제거하며, 노드를 교체하기도 한다.<br>
노드를 교체할 때 트래픽의 이슈가 생겼던 경험을 바탕으로 ALB의 노드 교체 또는 추가를 모니터링하여 데이터를 수집한다면, 비정상 적인 노드 교체가 일어났을 때 알 수 있을 것이다. <br>
ALB 노드 모니터링 방법은 CloudTrail, AWS EventBridge, CloudWatch LogGroups을 사용하여 구성할 수 있다.<br>
