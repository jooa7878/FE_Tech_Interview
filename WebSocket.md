# Web Socket

서버와 클라이언트 사이의 **socket connection**을 유지해서 언제든 양방향 통신 또는 데이터 전송이 <br/>
가능하도록 하는 기술 (Real-time web application 구현을 위해 널리 사용)

---

- 사용 이유

  - 기존의 서버와 클라이언트 간 통신은 대부분 HTTP를 통해 이루어짐
    - Socket connection 같은 영구적인 연결이 아니라 클라이언트의 request에만 <br/> 서버가 response를 하는 방식(단방향)
    - 서버쪽 데이터의 변경이 발생해도 클라이언트는 refresh 하지 않는 이상 <br/> 변화를 감지할 수 없음
    - 데이터의 빠른 업데이트가 중요한 real-time web app의 경우 web socket이 매우 중요하다.
  - HTTP와는 다른 Stateful protocol이기 때문에 한 번 연결이 되면 계속 같은 라인을 사용
    - HTTP 사용 시 발생하는 필요 없는 HTTP와 TCP 연결 트래픽을 방지
  - HTTP와 같은 80번 포트 사용
    - 기업용 어플리케이션에 적용 시 방화벽을 따로 설치하지 않아도 됨

- 작동 원리

  - Web socket 연결은 HTTP를 통해 이루어진다.
  - 정상적으로 연결 시 Websocket 연결이 이루어지고 <br/> 일정 시간이 지나면 HTTP 연결은 자동으로 끊어진다.

- HTTP와 차이점
  - 결정적으로는 'Protocol'
  - 접속 시에 HTTP, 그 이후에는 Web Socket만의 독자적인 프로토콜 사용
    - header가 작아서 overhead가 낮음
    - 데이터 송수신에 각각 커넥션을 맺을 필요가 없음
    - 양방향
