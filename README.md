# backend-interview-questions
Backend  면접 질문 정리

### 네트워크, HTTP 기본 지식

<details>
  <summary>특정 사이트를 접속할 때 인터넷 통신이 어떻게 되는지 설명해주세요.</summary>
  <br>
  <p>클라이언트 측에서 URL로 접속하면 브라우저가 이 URL에 적힌 값을 파싱해서 HTTP Message를 만들고 서버로 요청을 보내줍니다. HTTP Message를 서버에서 받아서 처리 한 data를 HTTP Message에 담아 클라이언트에 응답해주면 요청한 사이트로 접속할 수 있게 됩니다.</p>
</details>

<details>
  <summary>IP 란 무엇인지 설명해주세요.</summary>
  <br>
  <p>Internet Protocol의 약자로, 클라이언트와 서버 사이 인터넷 통신에 필요한 정보를 수신하고 송신하는 통신 규약을 의미합니다.</p>
</details>

<details>
  <summary>클라이언트-서버 사이의 data 전송 조건은 무엇이 있는지 설명해주세요.</summary>
  <br>
  <p>첫번쨰로 클라이언트와 서버는 각각 IP 주소를 부여받아 가지고 있어야 합니다.</p>
  <p>이렇게 양쪽에 IP 주소가 있을 때, IP 패킷이라는 규칙에 맞춰서 data를 전달해줘야합니다.</p>
</details>

<details>
  <summary>IP 패킷은 무엇인지 설명해주세요.</summary>
  <br>
  <p>간단히 설명하자면 패키지와 버킷의 합성어로 인터넷 통신 규약에 맞는 data 묶음을 의미합니다.</p>
  <p>출발지와 목적지의 IP, 전송데이터를 가지고 있고 전달시 인터넷 노드들을 타고 전달됩니다.</p>
</details>

<details>
  <summary>인터넷 프로토콜 스택의 4계층, 순서에 대해 설명해주세요.</summary>
  <br>
  <p>4계층은</p>
  <p>애플리케이션 계층 (HTTP, FTP)</p>  
  <p>전송 계층(TCP, UDP)</p>
  <p>인터넷 계층(IP)</p>
  <p>네트워크 인터페이스 계층 입니다.</p>
  <p>스택 순서는</p>
  <p>먼저 프로그램(애플리케이션)을 통해 전송할 data를 생성합니다.</p>
  <p>이를 SOCKET 라이브러리를 통해 전달하고</p>
  <p>TCP 정보를 생성합니다. 이때 전송 data를 포함합니다.</p>
  <p>이후 IP 패킷을 생성합니다. 여기에 TCP 정보가 담기게 됩니다.</p>
</details>

<details>
  <summary>IP의 한계와 TCP가 무엇인지 연관지어 설명해주세요.</summary>
  <br>
  <p>IP의 한계는</p>
  <p>첫번째로 비연결성입니다. 패킷을 받을 대상이 없거나 서비스가 불능인 상태에서도 이를 감지하지 못하고 패킷이 전송되는 문제가 있습니다.</p>
  <p>두번째는 비신뢰성입니다. 전송에 중간에 패킷이 없어지거나 순서대로 가지 않는다해도 이를 알 수 있는 방법이 없습니다.</p>
  <p>세번째는 프로그램을 구분 못한다는 것입니다. 같은 IP를 사용하는 서버에서 통신하는 애플리케이션이 2개 이상이면 구분할 수 있는 방법이 없습니다.</p><br>
  <p>TCP란 이러한 IP의 한계들을 보완해주는 역할을 하는 규약입니다.</p>
  <p>비연결성을 보완하기 위해 연결지향적입니다. 이는 3 way handshake 라고 불리며, 클라이언트에서서버로 접속 요청하면 서버에서 요청 수락 후 클라이언트에 접속 요청, 그리고 클라이언트가 요청을 수락하면 데이터를 전송하는 형태로 진행되는 것을 뜻합니다.</p>
  <p>또한 데이터의 전달을 보증해 신뢰성을 가집니다. 데이터를 전송시 서버에서 데이터를 받으면 받았음을 응답해줍니다.</p>
  <p>마지막으로 순서를 보장해줍니다. 클라이언트에서 보낸 순서대로 서버에 도달하지 않으면 잘못된 부분부터 재요청을 하게 됩니다.</p>
  <p>이렇게 IP의 한계를 보완해줄 수 있는 이유는 TCP에 전송 제어 및 순서, 검증 정보, PORT 등에 대한 data를 담기 때문입니다.</p>
</details>

<details>
  <summary>UDP는 무엇인지 설명해주세요.(TCP와의 차이점)</summary>
  <br>
  <p>UDP는 사용자 데이터그램 프로토콜을 말하고, TCP와 다르게 연결지향적이지 않고 데이터 전달 보증 등 신뢰성을 가지고 있지 않습니다.</p>
  <p>기능이 적은 대신 TCP보다 최적화에 장점이 있습니다. 애플리케이션에서 추가 작업을 통해 기능을 직접 추가할 수 있습니다.</p>
</details>

<details>
  <summary>PORT 는 무엇인지 설명해주세요.</summary>
  <br>
  <p>논리적인 접속장소를 뜻하며, 하나의 같은 IP내에서 나눠지는 서버를 의미합니다.</p>
</details>

<details>
  <summary>PORT 는 무엇인지 설명해주세요.</summary>
  <br>
  <p>논리적인 접속장소를 뜻하며, 하나의 같은 IP내에서 나눠지는 서버를 의미합니다. 하나의 IP내에서 애플리케이션마다 PORT번호를 다르게하여 구분하여 사용할 수 있습니다.</p>
</details>

<details>
  <summary>DNS 는 무엇인지 설명해주세요.</summary>
  <br>
  <p>도메인 네임 시스템의 약자이고, IP 형식을 사용하는 것에 번거로움이 있기 때문에 IP 형식을 대신해 DNS 서버에 등록한 도메인을 사용함으로써 기억하기 쉽고 수정하기 쉽게 됩니다.</p>
</details>

<details>
  <summary>URI 는 무엇인지 설명해주세요.</summary>
  <br>
  <p>인터넷 자원을 나타내는 고유 식별자를 의미합니다.</p>
  <p>URL은 이 식별을 Resource Locater 즉, 자원의 경로를 사용하는 것을 의미합니다.</p>
</details>

<details>
  <summary>HTTP 는 무엇인지, 특징은 무엇이 있는지 설명해주세요.</summary>
  <br>
  <p>HyperText Transfer Protocol의 약자로써 HTML, TEXT 문서 등 대부분의 data들의 통신에 대한 규약을 의미합니다.</p>
  <p>클라이언트에서 서버로 요청 후 응답을 대기하고 서버는 요청에 대한 결과를 만들어 응답하는 구조입니다.</p>
  <p>무상태 프로토콜이어서 서버가 클라이언트의 상태를 보존하지 않습니다. 즉, 클라이언트가 요청시에 보내준 data를 서버에서는 유지, 기억하고 있지 않습니다. 따라서 요청시마다 필요한 모든 data들을 보내줘야 합니다.</p>
  <p>비연결성의 특징을 가지고 있어 요청에 대한 응답 후 연결을 끊는 형태입니다.</p>
</details>

<details>
  <summary>HTTP의 무상태 프로토콜 특징의 장점과 단점에 대해 설명해주세요.</summary>
  <br>
  <p>장점은 서버 확장성이 높다는 점입니다. 특정 서버가 data를 저장하고 있지 않고 계속 data를 주고 받기 떄문에 확장에 대해서 제약이 없습니다.</p>
  <p>단점은 클라이언트가 계속 필요한 모든 data를 전송해야 하기 때문에 전송량이 많아집니다.</p>
</details>

<details>
  <summary>HTTPS에 대해 설명하고 HTTP와 다른점이 무엇인지 설명해주세요.</summary>
  <br>
  <p>HTTPS는 HTTP에 보안계층을 추가한 것을 말합니다.</p>
  <p>HTTP 프로토콜은 인터넷 프로토콜 스택 중 전송계층의 TCP위에서 동작합니다. 여기서 SSL이라는 보안계층이 전송계층 위에 올라가 보안이 보장된 통신을 할 수 있습니다. 이 통신 방식을 SSL 암호화 통신이라고도 합니다.</p>
  <p>SSL 암호화 통신은 공개키 암호화 방식 알고리즘을 통해 구현됩니다.</p>
</details>

<details>
  <summary>공개키 암호화 방식이란 무엇인가요?</summary>
  <br>
  <p>공개키 암호화 방식에는 공개키와 개인키 두 종류의 키가 존재합니다.</p>
  <p>한쪽 키로 데이터를 암호화했다면 오직 다른쪽 키로만 복호화 할 수 있습니다.</p>
  <p>개인키는 보통 서버를 운영하는 회사가 가지고 공개키는 인증받은 기업들에서 관리합니다.</p>
  <p>인증받은 기업은 공개키를 다른 data들과 묶어서 자신들이 가지고 있는 개인키로 암호화해서 SSL인증서로 발급해줍니다.</p>
  <p>브라우저는 공개키를 보유하고 있어서 SSL 인증서를 복호화 해줍니다.</p>
  <p>복호화 된 SSL 내부에 들어있던 서버의 공개키를 가지고 요청을 암호화해서 서버로 보내면</p>
  <p>서버측은 가지고 있는 개인키로 요청을 복호화하여 해석 후 응답할 때 다시 암호화해서 보냅니다.</p>
</details>

<details>
  <summary>HTTP 메서드에 대해서 설명해주세요.</summary>
  <br>
  <p>주요 메서드로는 GET, POST, PUT, PATCH, DELETE 가 있습니다.</p>
  <p>GET은 리소스를 조회할 때 사용하고</p>
  <p>POST는 요청 데이터를 처리할 때,</p>
  <p>PUT은 리소스를 대체할 때 만약 리소스가 없으면 생성합니다,</p>
  <p>PATCH는 리소스 일부 변경할 때,</p>
  <p>DELETE 는 리소스를 제거할 때 사용하는 메서드입니다.</p>
</details>

<details>
  <summary>HTTP 메서드의 속성에 대해 설명해주세요.</summary>
  <br>
  <p>1. GET메서드는 '안전'이라는 속성이 있습니다. 호출해도 리소스를 변경하지 않는다는 것입니다.</p>
  <p>2. 멱등이라는 속성이 있습니다. 몇 번을 요청해도 같은 결과가 나온다는 것을 의미합니다. 주요 메서드 중 POST를 제외하고는 이 속성을 가집니다. POST의 경우 같은 내용으로 요청시 반복해서 INSERT 되므로 멱등적이지 않습니다.</p>
  <p>3. 캐시 가능 속성은 응답 결과를 캐시에서 사용할 수 있는지를 의미합니다. 실제로 GET, HEAD 메서드에서 주로 사용합니다.</p>
</details>

<details>
  <summary>HTTP 상태코드에 대해 간단히 설명해주세요.</summary>
  <br>
  <p>200 번대는 클라이언트의 요청을 성공적으로 처리했을 때 보내주는 코드입니다.</p>
  <p>300 번대는 요청에 대한 처리 성공 후 리다이렉션이 필요할 때 보내주는 코드이고,</p>
  <p>400, 500 번대는 각각 클라이언트, 서버 측에 오류이 원인이 있을 때 보내주는 코드입니다.</p>
</details>

<details>
  <summary>쿠키와 세션에 차이점에 대해서 설명해주세요.</summary>
  <br>
  <p>쿠키는 클라이언트에서 저장하고 서버에 요청시마다 보내주는 data입니다.</p>
  <p>세션은 서버에서 저장하고 서버에서 관리하기 때문에 클라이언트 측보다 보안적인 측면에서 훨씬 유리합니다.</p>
</details>

<details>
  <summary>캐시에 대해서 설명해주세요.</summary>
  <br>
  <p>자주 사용하는 데이터를 미리 복사해 놓는 임시 장소를 가리킵니다.</p>
  <p>캐시 가능 시간 동안에는 네트워크를 사용하지 않아도 돼서 비용 절감을 할 수 있습니다.</p>
  <p>브라우저 로딩 속도가 빨라 사용자 경험(UX)을 좋게 합니다.</p>
  <p>캐시 만료시에도 data에 변동이 없다면 검증 헤더를 통해 클라이언트와 서버의 data가 동일하다는 것을 확인 후 data를 네트워크를 통해 전송하지 않도록 할 수 있습니다.</p>
</details>

<details>
  <summary>CORS에 대해서 설명해주세요.</summary>
  <br>
  <p>CORS는 스프링 시큐리티를 사용하며 자주 만난 이슈입니다.</p>
  <p>특히 외부 API를 사용시 발생했으며, 서로 다른 도메인간에 자원을 공유할 때 발생했습니다.</p>
  <p>security config에서 cors 관련 설정을 추가로 해줘서 해결하거나 filter를 따로 만들어 header 정보를 수정해서 해결했습니다.</p>
</details>

### Spring
<details>
  <summary>DI와 IoC에 대해 설명해주세요.</summary>
  <br>
  <p>IoC 제어 역전을 뜻하며, 인스턴스 생성부터 소멸까지의 생명주기 관리를 개발자가 아닌 컨테이너가 대신 해주는 것입니다.</p>
  <p>DI는 의존성 주입을 뜻하며, 하나의 객체가 다른 객체의 의존성을 제공하는 것, 외부에서 의존 관계를 주입하는 것입니다.</p>
</details>

<details>
  <summary>Spring Bean이란 무엇인지 설명해주세요.</summary>
  <br>
  <p>Spring IoC 컨테이너가 관리하는 자바 객체를 말합니다. @Configuration을 붙인 객체에서 @Bean을 통해 빈등록이 가능하고 또는 스프링에서는 컴포넌트 스캔을 통해 @Component가 있는 클래스를 빈으로 등록합니다.</p>
</details>

<details>
  <summary>SOLID가 무엇인지 설명해주세요.</summary>
  <br>
  <p>좋은 객체 지향 설계의 5가지 원칙을 의미합니다.</p>
  <p>1. SRP, 단일 책임 원칙</p>
  <p>하나의 클래스는 하나의 책임만 가져야한다는 것을 뜻합니다.</p>
  <p>2. OCP, 개방-폐쇄 원칙</p>
  <p>소프트웨어 요소는 확장에는 열려있으나 변경에는 닫혀 있어야합니다. 즉, 인터페이스를 만들어 역할과 구현을 구분하는 것을 뜻합니다.</p>
  <p>3. LSP, 리스코프 치환 원칙</p>
  <p>프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야한다는 것입니다. 다형성에서 하위 클래스는 인터페이스 규약을 다 지켜야한다는 것을 뜻합니다. 역할에 대한 구현의 내용이 설계 의도에 맞게 해야하는 것을 의미합니다.</p>
  <p>4. ISP, 인터페이스 분리 원칙</p>
  <p>특정 클라이언트를 위해 인터페이스를 여러 개로 분리하는 것이 범용 인터페이스 하나보다 낫다는 것입니다. 인터페이스도 역할의 크기가 작을수록 더 명확해지고 대체 가능성이 높아지기 때문입니다.</p>
  <p>5. DIP, 의존관계 역전 원칙</p>
  <p>객체 지향에서는 추상화에 의존해야지 구체화에 의존하면 안된다는 것입니다. 의존성 주입을 통해 인터페이스에 의존해야 수정이 있어도 변경해야 하는 부분이 적어집니다. 확장에는 열려있되 변경에는 닫혀 있어야 하는 원칙인 OCP와 연관되어 있습니다.</p>
</details>

<details>
  <summary>DI의 방법에 무엇이 있고 어떤 것을 주로 쓰는지 설명해주세요.</summary>
  <br>
  <p>생성자 주입, setter를 이용한 수정자 주입, 필드 주입이 있습니다.</p>
  <p>생성자 주입을 주로 쓰며 호출 시점에 딱 한 번만 호출되므로 불변할 때 사용합니다. 보통 의존관계는 불변하기 때문에 생성자 주입을 자주 쓰는 이유가 됩니다.</p>
  <p>수정자 주입은 스프링 빈을 선택적으로 주입할 수 있습니다.</p>
  <p>필드 주입은 @Autowired를 통해서 주입할 수 있는데 외부에서 변경이 불가능해 테스트시 힘들다는 단점이 있습니다. 따라서 애플리케이션 실행과 관련없는 테스트코드에서 사용합니다.</p>
</details>

<details>
  <summary>작업 시에 보통 의존성 주입을 어떻게 했는지 알려주세요.</summary>
  <br>
  <p>예전에는 필드 주입을 사용했으나, 테스트에 변경이 불가능해서 유연하지 못하다는 단점을 알고 나서는 생성자 주입을 사용했습니다.</p>
  <p>롬복에서 제공하는 애노테이션인 @RequiredArgsConstructor와 final 키워드를 이용해서 생성자 주입을 했고 추상화에 의존할 수 있게 했습니다.</p>
</details>

<details>
  <summary>스프링에서 @Autowired를 통한 의존성 주입은 어떻게 일어날까요?</summary>
  <br>
  <p>스프링 컨테이너에 이미 빈으로 등록돼있는 객체를 타입(인터페이스 or 오브젝트)으로 검색해서 주입합니다.</p>
</details>

<details>
  <summary>스프링에서의 싱글톤에 대해서 설명해주세요.</summary>
  <br>
  <p>스프링 빈으로 등록한 객체는 호출 시에 하나의 같은 인스턴스를 여러 클라이언트가 공유하는 것을 말합니다. 원리는 간단하게 설명하자면, 객체의 생성자를 private로 만들어 외부에서 new 키워드 대신 static 메서드로만 접근할 수 있게 하는 것입니다. 이런 방법을 통해 객체 인스턴스를 계속 새로 생성하는 것을 방지해 메모리 낭비를 줄일 수 있습니다. 같은 인스턴스를 공유하기 때문에 객체는 특정 클라이언트에 의존적인 필드를 가지면 안됩니다.</p>
</details>

<details>
  <summary>만약 하나의 인터페이스를 구현한 여러개의 구현체를 bean으로 등록하여 사용하려면 어떻게 해야할까요?</summary>
  <br>
  <p>여러개의 구현체를 bean으로 등록하고 추상화에 의존하려하면 유니크하지 않다는 에러가 발생합니다.</p>
  <p>정말로 의도가 여러개의 빈들 중 골라쓰고 싶다면 List의 형태로 여러개의 빈을 주입해주고 꺼내서 사용해야하고 그렇지 않다면 빈으로 등록할 객체에 @Primary을 붙여 우선권을 가지게 하면 됩니다.</p>
</details>

<details>
  <summary>프론트 컨트롤러 패턴이란 무엇인가요?</summary>
  <br>
  <p>클라이언트의 요청마다 서블릿을 새로 만들어 사용한다면 효율적이지 않기 때문에 이를 해결하기 위해 사용하는 패턴입니다. 모든 요청에 대해 보안, 검증, 국제화 등의 기능들을 한 곳에서 캡슐화할 수 있습니다. 스프링에서는 클라이언트 요청이 들어왔을때 Controller 관련 애노테이션을 확인하고 적절한 Handler Method에 위임해줍니다.</p>
</details>

<details>
  <summary>스프링 MVC 패턴의 동작 원리에 대해서 간단히 설명해주세요.</summary>
  <br>
  <p>클라이언트로부터 HTTP 요청이 들어오면 *Dispatcher Servlet(프론트 컨트롤러) 가 이를 받습니다.</p>
  <p>1. 그 다음 핸들러 매핑을 통해 요청 URL에 매핑된 핸들러(컨트롤러) 조회를 합니다.</p>
  <p>2. 핸들러를 조회했으면 이 핸들러를 처리할 수 있는 핸들러 어댑터를 조회합니다.</p>
  <p>3. 조회한 핸들러 어댑터를 통해 핸들러 즉, 컨트롤러를 호출하고 ModelAndView를 반환합니다.</p>
  <p>4. 반환한 ModelAndView를 가지고 Dispatcher Servlet이 viewResolver를 호출해 view를 찾고 반환시킵니다.</p>
  <p>5. render를 호출하여 view를 랜더링해서 HTML로 응답을 해줍니다.</p>
  <br>
  <p>*스프링 부트는 DispatcherServlet을 서블릿으로 자동으로 등록하면서 모든 경로에 대해서 매핑</p>
</details>

<details>
  <summary>filter와 interceptor의 차이점은 무엇인가요?</summary>
  <br>
  <p>filter는 servlet에 요청이 전달되기 전/ 후의 처리를 담당하고 interceptor는 Spring에서 Handler(컨트롤러)를 실행하기 전, 후 처리를 담당합니다.</p>
  <p>+ filter는 init(필터 초기화), doFilter(처리), destroy(필터 제거) 메서드 / interceptor(handlerInterceptor)는 preHandle(호출 전), postHandle(호출 후), afterCompletion(완료 후 항상) 메서드를 가지고 @configuration 붙은 클래스에 각각 @Bean 등록 / addInterceptors 메서드 override 를 통해 등록</p>
</details>

<details>
  <summary>POJO란 무엇인가요?</summary>
  <br>
  <p>Plain Old Java Object, 오래된 방식의 간단한 자바 오브젝트</p>
  <p>특정 기술에 종속되어 동작하는 것이 아닌 순수한 자바 객체를 뜻합니다. (ex. getter, setter 메서드로만 이뤄진 객체)</p>
  <p>POJO를 지향해야 하는 이유는 객체가 어떤 특정 기술에 종속돼버리면 확장성이 떨어지는 등 객체 지향 설계의 장점을 잃게 되기 때문입니다. 또한 비즈니스 로직에 충실한 개발이 가능하도록 하기 때문입니다.</p>
</details>


### JPA

<details>
  <summary>영속성 컨텍스트란 무엇인지와 사용하는 이유도 설명해주세요.</summary>
  <br>
  <p>영속성 컨텍스트는 엔티티를 영구 저장하는 환경을 의미합니다. 애플리케이션과 데이터베이스 사이에서 객체를 보관하는 가상의 데이터베이스 같은 역할을 합니다.</p>
  <p>1차 캐시를 통해 조회가 가능하며 1차 캐시에 없으면 DB에서 조회해서 1차 캐시에 올립니다.</p>
  <p>동일성을 보장하여 동일성 비교가 가능합니다.</p>
  <p>transaction을 지원하는 쓰기를 지연해서 커밋 시점에 SQL을 한 번에 처리하도록 합니다.</p>
  <p>변경 감지(dirty checking), 1차 캐시에 data가 들어올 때 스냅샷을 찍고 커밋 시점에 엔티티와 비교하여 update SQL을 생성합니다.</p>
  <p>지연로딩 사용이 가능합니다. 실제 객체를 사용하는 시점에 DB에 SQL을 보내 data를 조회합니다.</p>
</details>

<details>
  <summary>MyBatis를 사용하다가 JPA를 사용하는 이유는 무엇인가요?</summary>
  <br>
  <p>MyBatis는 SQL문을 작성할 줄 안다면 접하기 쉽고 특히 동적쿼리를 작성하기 쉬워 사용했지만, 엔티티가 변경될 때마다 일일이 쿼리를 수정해야 되기 때문에 유지보수에는 용이하지 않다는 것을 깨달았습니다. 또한 JPA의 경우 객체지향 프레임워크이기 때문에 관계형 데이터베이스에 의존하지 않고 자바 코드를 통해 작성할 수 있기 때문에 JPA에 익숙해지면 질수록 생산성이 높아진다고 생각했습니다.</p>
</details>

<details>
  <summary>N + 1 문제가 발생하는 이유와 해결하는 방법을 설명해주세요.</summary>
  <br>
  <p>연관 관계에서 발생하는 이슈로 연관 관계가 설정된 엔티티를 조회할 경우에 조회된 data row만큼 연관관계의 조회 쿼리가 추가로 발생하여 N개가 더 실행되는 문제를 말합니다. </p>
  <p>해결하기 위해서는 연관관계가 맺어진 엔티티를 한번에 가져오는 방법을 사용해야 합니다. 주로  fetch join를 사용한다고 알고 있습니다. 조회시 바로 가져오고 싶은 엔티티는 JPQL문에서 join fetch 를 이용해서 join을 하면 됩니다. 또다른 방법으로는 @EntityGraph가 있습니다.</p>
</details>

<details>
  <summary>단방향, 양방향 연관 관계의 차이점은 무엇인가요?</summary>
  <br>
  <p>연관 관계에 있는 두 객체 중 하나의 객체만 참조용 필드를 가지고 참조하고 있으면 단방향 관계, 두 객체 모두 각각 참조용 필드를 갖고 참조하면 양방향 관계입니다.</p>
  <p>기본적으로 단방향 관계로 작성하고 역으로 객체를 탐색할 수 있어야한다면 양방향 관계를 맺어주는 게 불필요한 연관관계 매핑을 피할 수 있습니다.</p>
  <p>연관 관계의 주인은 데이터 제어의 권한을 가지는 쪽 즉, FK를 가지는 쪽이 돼야합니다.</p>
</details>

<details>
  <summary>LAZY(지연로딩)이 무엇인지 설명해주세요.</summary>
  <br>
  <p>객체를 사용하는 시점에 연관된 데이터를 불러오는 것을 말합니다. 반대로 EAGER(즉시로딩)은 데이터를 조회할 때 연관된 데이터까지 한번에 조회하는 것을 말합니다.</p>
</details>

<details>
  <summary>실무에서 fetchType을 LAZY로 해야하는 이유는 무엇일까요?</summary>
  <br>
  <p>즉시로딩을 통해서 연관된 테이블까지 한 번에 조회하는 경우에는 해당 엔티티가 참조하는 모든 엔티티까지 한 번에 조회하기 때문에 쿼리문의 길이가 길어져 해석하기가 어려워지고 불필요한 테이블까지 전부 join되기 때문에 유지 보수를 힘들게 합니다. 사용 시점에 연관된 엔티티를 조회하는 쿼리문을 날리는 것, 즉 지연로딩을 이용하면 이런 단점들은 사라집니다.</p>
  <p>※주의: 지연로딩을 쓴다고해서 N+1 문제를 완전히 해결할 수 있는 것은 아니다. 단지 시점을 늦추는 것일 뿐이다. fetch join등을 통해 한방 쿼리로 만들어줘야 N+1 문제를 해결할 수 있다.</p>
</details>

### 자료구조

<details>
  <summary>배열과 ArrayList를 비교해서 설명해주세요.</summary>
  <br>
  <p>배열은 생성시 크기가 고정되고 인덱스가 부여됩니다. 인덱스를 통해 데이터에 효율적으로 접근할 수 있습니다. 그러나 데이터를 추가하고 삭제하는 방법이 비효율적입니다.</p>
  <p>ArrayList는 크기가 가변적이고 데이터를 추가, 삭제하는 방법이 쉽습니다. 하지만 배열보다 속도가 느립니다.</p>
</details>

<details>
  <summary>스택(Stack)에 대해 설명해주세요.</summary>
  <br>
  <p>순서가 보존되는 선형 데이터 구조 유형입니다. 가장 마지막 요소부터 처리하는 메커니즘을 가지고 있어 추가시에도 맨 위에 쌓이고 가져갈 때도 맨 위에서 가져갑니다.</p>
  <p>장점은 동적인 메모리 크기를 가지고 있다는 것과 데이터를 받는 순서대로 정렬하는 것 그리고 런타임이 빠른 점입니다.</p>
  <p>단점은 가장 최신 요소만 가져올 수 있고 한 번에 하나의 데이터만 처리 가능하다는 점입니다.</p>
</details>

<details>
  <summary>큐(Queue)에 대해 설명해주세요.</summary>
  <br>
  <p>가장 먼저 입력된 요소를 처리하는 매커니즘을 가집니다. 추가시 맨 뒤에 쌓이고 가져갈 때 맨 앞부터 가져갑니다.(선입선출)</p>
  <p>장점은 스택과 동일합니다.</p>
  <p>단점은 가장 오래된 요소만 가져올 수 있고 한 번에 하나의 데이터만 처리 가능하다는 점입니다.</p>
</details>

<details>
  <summary>Linked List에 대해 설명해주세요.</summary>
  <br>
  <p>물리적으로 연결되지 않고 각 요소가 노드에 저장되고 다음 노드 연결에 대한 포인터 또는 주소가 포함된 또 다른 노드에 저장됩니다.</p>
  <p>장점은 새로운 요소들의 추가 및 삭제가 효율적이고, 메모리가 연속적으로 위치하지 않아 구조의 재구성이 필요없다는 점입니다.</p>
  <p>단점은 검색 시에 처음 노드부터 끝까지 순회하기 때문에 검색에 비효율적이라는 점입니다.</p>
</details>

<details>
  <summary>Hash Map / Hash Tables에 대해 설명해주세요.</summary>
  <br>
  <p>data를 key, value 형식으로 저장하는데, key를 저장할 때 메모리 공간을 덜 사용할 수 있도록 키를 해시 함수를 통해 해시라는 특정 숫자값으로 변환합니다.</p>
  <p>장점은 data의 추가, 삭제가 효율적이고, 검색 또한 key로 가져올 수 있어 효율적이라는 점입니다.</p>
  <p>단점은 입력된 key의 해시값이 이미 저장된 메모리 주소를 가리킬 수 있어 충돌이 일어날 수 있다는 점입니다.</p>
</details>

<details>
  <summary>Tree에 대해 설명해주세요.</summary>
  <br>
  <p>노드로 구성된 계층적 자료구조입니다. 최상위 노드를 만들고 그 노드의 자식 노드를 계속 추가하는 방식으로 구현됩니다.</p>
</details>

<details>
  <summary>자바의 Collection 자료구조 대해 설명해주세요.</summary>
  <br>
  <p>컬렉션 프레임워크의 주요 클래스는 List, Set, Map(독립적인 인터페이스 구현) 인터페이스를 상속받고 있습니다.</p>
  <ul>List : 중복허용, 순서가 있습니다.
    <li>ArrayList : 배열에 비해 요소의 추가, 삭제에 용이합니다. 정렬은 안됩니다.</li>
    <li>LinkedList : 배열에 비해 요소의 추가, 삭제에 용이합니다. 정렬은 안됩니다. 검색에는 비효율적입니다. </li>
  </ul>
  <ul>Set : 중복을 허용하지 않습니다.
    <li>HashSet : 순서를 보장하지 않습니다.</li>
    <li>TreeSet : 순서를 보장하고 정렬 방법을 지정할 수 있습니다.</li>
  </ul>
  <ul>Map : key, value 쌍으로 이루어진 자료구조입니다. key의 중복을 허용하지 않습니다.
    <li>HashMap : 순서를 보장하지 않습니다.</li>
    <li>TreeMap : 순서를 보장하고 key값으로 정렬할 수 있습니다.</li>
  </ul>
</details>

<details>
  <summary>ArrayList와 LinkedList의 차이</summary>
  <br>
  <p>ArrayList는 index가 있고 LinkedList는 각 원소마다 앞, 뒤 원소의 위치값을 가지고 있습니다.</p>
  <p>ArrayList는 추가, 삭제가 많다면 계속 요소의 위치를 이동시켜야 하기 때문에(구조 재구성) 비효율적입니다. 데이터를 가져오는 데는 index로 바로 조회하기 때문에 빠릅니다.</p>
  <p>LinkedList는 추가, 삭제시 노드가 가리키고 있는 주소값만 변경해주면 되기 때문에 효율적이지만, 검색 시에는 불리합니다.</p>
  <p>정리하자면 정적인 데이터를 활용하며 조회가 빈번하다면 ArrayList 사용, 동적인 추가/ 삭제가 많다면 LinkedList를 사용하는 것이 좋습니다.</p>
</details>

<details>
  <summary>! 시간복잡도</summary>
  <br>
  <p></p>
</details>

### I/O

### Java
<details>
  <summary>Java 언어에 대해 생각나는대로 간단히 설명해주세요.</summary>
  <br>
  <p>객체 지향 언어이고 컴파일 언어입니다. 메모리를 자동으로 관리합니다. 오픈소스 라이브러리가 방대합니다.</p>
  <p>자바를 실행하는 방식은 자바 컴파일러가 자바 소스코드를 읽어 자바 바이트코드로 변환시키고, Class Loader를 통해 class 파일들을 JVM으로 로딩합니다. 로딩된 파일들은 Execution engine을 통해 해석되고 해석된 바이트 코드는 Runtime Data Areas에 배치되어 수행이 됩니다.</p>
</details>

<details>
  <summary>Garbage Collection을 설명해주세요.</summary>
  <br>
  <p>힙 영역에서 사용하지 않는 객체들을 제거하는 작업을 말합니다. JVM의 GC가 이 불필요한 메모리를 알아서 정리해줍니다.</p>
  <p>동작 방식은 Stop The World, Mark and Sweep 으로 이뤄집니다.</p>
  <p>Stop The World는 GC를 실행하기 위해 JVM이 애플리케이션의 실행을 멈추는 작업입니다.</p>
  <p>Mark and Sweep은 사용되지 않는 메모리를 식별하고 이 식별된 메모리를 해체하는 작업을 뜻합니다.</p>
</details>

<details>
  <summary>컬렉션 프레임워크에 대해 설명해주세요.</summary>
  <br>
  <p>주로 쓰는 자료구조를 바탕으로 객체, 데이터들을 효율적으로 관리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 말합니다.</p>
</details>

<details>
  <summary>제네릭에 대해 설명해주세요.</summary>
  <br>
  <p>제네릭은 타입을 클래스 내부에서 지정하는 것이 아니라 외부에서 사용자에 의해 지정할 수 있게끔한 것을 말합니다. 컴파일 과정에서 타입체크를 해주므로 객체 타입의 안정성을 높이고 형변환의 번거로움을 줄여줍니다. 또한 코드의 재사용성이 높아집니다. <br>
    ex. ArrayList<타입> = new ArrayList<타입>(); </p>
</details>
    
<details>
  <summary>애노테이션이란 무엇일까요?</summary>
  <br>
  <p>인터페이스를 기반으로 한 문법으로 소스 코드에 추가하여 사용할 수 있는 메타데이터의 일종입니다. 컴파일러 시점에서 문법 에러를 체크하도록, 특정 기능을 실행할 수 있도록 해주는 역할을 합니다.</p>
</details>
    
<details>
  <summary>오버라이딩과 오버로딩의 차이점에 대해 알려주세요.</summary>
  <br>
  <p>오버라이딩은 상위클래스의 메서드를 재정의 하는 것을 의미합니다.</p>
  <p>오버로딩은 같은 클래스 내에서 메서드의 이름은 같지만 매개변수의 타입, 개수를 다르게 구현하는 것을 말합니다.</p>
</details>
    
<details>
  <summary>인터페이스와 추상클래스의 차이점에 대해 알려주세요.</summary>
  <br>
  <p>둘 다 추상 메서드를 가지고 있는 것입니다. 인터페이스는 모든 메서드가 추상메서드인 것이고 추상 클래스는 1개 이상의 추상 메서드를 가지고 있는 것입니다. (인터페이스:기획서, 추상클래스:미완성 설계도, 클래스:완성 설계도)</p>
  <p>인터페이스는 구현 객체끼리 같은 동작을 한다는 것을 보장하기 위해 사용합니다. 메서드의 선언부만 있어 상속 받는 클래스에서 메서드의 구현을 강제할 수 있습니다.</p>
  <p>추상클래스는 객체의 추상적인 상위 개념으로 공통된 개념을 표현할 때 사용합니다. 기능을 이용하고 확장시키는데 목적이 있습니다.</p>
</details>
    
<details>
  <summary>클래스와 객체에 대해 설명해주세요.</summary>
  <br>
  <p>객체는 물리적으로 존재하거나 추상적으로 생각할 수 있는 것으로 식별 가능한 행위나 속성의 대상을 뜻합니다. 클래스는 이 객체를 정의하는 틀의 의미입니다.</p>
</details>
    
<details>
  <summary>static의 의미에 대해 설명해주세요.</summary>
  <br>
  <p>GC의 관리 영역 밖 static 영역을 의미하며 프로그램 종료시까지 메모리가 할당된 채로 존재하여 어디서든지 참조할 수 있고 공유하게 되는 것을 뜻합니다.</p>
</details>
    
<details>
  <summary>자바의 원시타입들에 대해서 알려주세요.</summary>
  <br>
  <p>boolean(1 byte): 논리형 데이터 타입이고 true=1, false=0 의 값을 가집니다.</p>
  <p>char (unsigned 2): 문자형</p>
  <p>byte (1): 정수형</p>
  <p>short (2): 정수형</p>
  <p>int (4): 정수형</p>
  <p>long (8): 정수형</p>
  <p>float (4): 실수형</p>
  <p>double (8): 실수형</p>
</details>
    
<details>
  <summary>접근 제어자에 대해서 설명해주세요.</summary>
  <br>
  <p>private, default, protected, public</p>
  <p>private: 해당 클래스 내에서 접근 가능</p>
  <p>default: 해당 패키지</p>
  <p>protected: 상속한 클래스</p>
  <p>public: 전체 영역에서 접근 가능합니다.</p>
</details>
    
<details>
  <summary>객체 지향에 대해서 설명해주세요.</summary>
  <br>
  <p>프로그래밍에서 필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 그 객체들 간의 상호작용을 통해 로직을 구성하는 것을 지향하는 것입니다.</p>
</details>
    
<details>
  <summary>원시타입과 참조타입의 차이에 대해 설명해주세요.</summary>
  <br>
  <p>원시 타입은 항상 값이 존재해야되고(null이 될 수 없습니다.) 참조 타입은 null을 가질 수 있습니다.</p>
</details>
    
<details>
  <summary>NPE를 방지하기 위한 방법을 설명해주세요.</summary>
  <br>
  <p>null 체크를 일일이 해줄 수도 있지만, Optional을 이용해 리턴 타입에서 null을 반환하지 않도록 할 수 있습니다.</p>
</details>

### 기타
<details>
  <summary>테스트, TDD, 작성법</summary>
  <br>
  <p></p>
</details>
