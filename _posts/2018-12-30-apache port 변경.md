---
categories: Linux
---

## apache Service Port 변경
apache 2 버젼 기준으로.

    1. 아파치의 포트 관련 환경설정 파일 수정
    $sudo vi /etc/apache2/ports.conf
    안에 Listen 80 을 원하는 포트 no로 수정
    ex: Listen 8080
    
    2. 아파치의 가상호스트 환경설정 파일 수정
    $sudo vi /etc/apache2/sites-available/000-default.conf
    안에 <VirtualHost *:80> 을 원하는 포트 no로 수정
    ex: <VirtualHost *:8080>
    
    
    3. 아파치 서비스 재시작
    $sudo /etc/init.d/apache2 restart
    
    4. 만약 아파치 서비스에서 에러시
    $apache2ctl configtest
    를 실행하면 apache가 실행되는 동안 문제가 되는 파일과 내용이 출력된다.

<img src="https://postfiles.pstatic.net/MjAxODEyMzBfNzEg/MDAxNTQ2MTc3NTg1NjQ5.b7FFqt-uldM2-O7aUR1naRMwIc8AlxMiWYaMmbkc0zgg.IHUwYMQELEwf5fiCLBwHLKTb-2NIcy1M_LwIqlLTlzIg.PNG.mdaengv/image.png?type=w773" width="90%">
