
### Morai_Simulation 내부의 GPS을 이용해서 Mapping & Navigation

1. Mapping 
    - 모라이 시뮬레이션 시작
    - 로봇에 GPS 장착 후 connect
    - 아래 launch 파일 실행
    ```
    roslaunch rosbridge_server rosbrigde_websocket.launch
    roslaunch scout_ros path_maker.launch

    ```
    - 실행 하면 **[xx.xxxx, xx.xxxx]** 이렇게 나오면 맵이 저장되고 있다는 것
    - 0.5m씩 이동할때마다 좌표값이 출력되고 로봇을 이동시켜 Path를 만든다.
    - 다 만들고 path_maker.launch 종료하면 scout_ros 패키지의 path 폴더에 xxx.txt 파일이 생성

2. Path Planning and Following
    - Mapping에서 path_maker 런치 파일만 끈 상태에서 시작
    - 로봇에 IMU를 설치 한후 Connect
    
    ```
    roslaunch scout_ros planner.launch
    ```

    - 실행 하면 **(예)** [False,True,True,False] 등 상태가 나온다.
    - GPS, IMU Connect/ Disconnect 한번씩 눌러서 False -> True로 바뀌는 지 확인
    - F4 눌러서 로봇의 Pulblish, Subscirbe 쪽 Connect 버튼 한번씩 눌러주기
    - 실행 화면에서 모두 [True, True, True, True]가 되면 어떤 값이 나옴
    - 켜진 Rviz 화면에서 형성된 Path 확인
    - Morai에서 AutoMode로 변경하면 Path를 따라서 로봇이 이동


3. Parameter 및 launch 파일 설명


4. 영상

    <img src="./gif/path_making.gif">
    
    ---
   
    <img src="./gif/path_planner.gif">
