
## Spring Boot Annotations 

#### Core Spring Framework Annotations

[@Required](): nó được áp dụng cho phương thức setter method. Nó chỉ ra rằng Bean được chú thích phải điền vào thời điểm cấu hình, nếu không thì nó sẽ ném ra ngoại lên 'BeanInitilizationException'

[@Autowired](): nó được sử dụng để tiêm(inject) đối tượng vào các phương thức 'setter', 'instance variable' và 'constructor'. @Autowired, bộ chứa lò xo sẽ tự động kết nối bean bằng cách khớp loại dữ liệu.

[@Configuration](): Nó là một chú thích cấp bậc.Lớp được chú thích '@Configuration' sử dụng làm nguồn định nghĩa 'Bean'

[@ComponentScan](): là annotation khai báo ở cấp độ class, giống như cái tên của nó, annotation @ComponentScan dùng để scan toàn bộ bean trong ứng dụng, mặc định nó sẽ scan tất cả bean trong package ở vị trí đặt class chưa hàm main, ngoài ra chúng ta cũng có thể tùy chỉnh package cần scan. thường thì annotation @ComponentScan sẽ đi chung vớ @ComponentScan.

Các param trong `@ComponentScan`:
- `basePackages`: dùng để chỉ ra những package cần scan, bạn có thể truyền vào một hoặc nhiều package name
- `basePackageClasses`: chỉ ra những class cần scan
- `excludeFilters`: dùng để filter loại trừ những bean or package không cần scan
- `includeFilters`: Dùng dể filter những bean or package cần scan.
- `lazyInit`: dùng để lazy load bean, default = false
- `resourcePattern`: chỉ ra các pattern file để Spring có thể scan, default pattern "**/*.class"

[@Bean](): nó là một annotation cho method. Nó là sự thay thể của thẻ XML <bean>. Nó cho biết method tạo ra một bean được Spring Container quản lý.

## Các mẫu Spring Boot Annotations:

[@Component]() :  là một annotation của class. Nó dùng để đánh dấu class Java là một bean. Một class Java được đánh dấu @Component được tìm thấy trong classpath. Spring Framework chọn nó và cấu hình trong ngữ cảnh ứng dụng như một Spring Bean.

[@Controller](): là một annotation ở class. Là một chuyên môn hóa của @Component. Nó đánh dấu class là một class để xử lý request web. Nó thường được sử dụng để phục vụ các request từ UI. Mặc định thì nó trả về một chuỗi cho biết route nào cần redirect. Nó chủ yếu được sử dụng với annotation @RequestMapping.

[@Service]() : nố thường được sử dụng ở class. Nó cho biết Spring biết rằng class này chứa business login.

[@Repository](): nó thường được dụng ở class. Repository là một DAOs (Data Access Object) cái mà sẽ truy cập trực tiếp vào database. Repository thực hiện tất cả các hoạt động liên quan đến database.


## Spring Boot Annotations:

[@EnableAutoConfiguration]() : Nó tự động cấu hình bean có trong classpath và cấu hình nó để chạy các phương thức. Việc sử dụng chú thích này bị giảm trong bản phát hành Spring Boot 1.2.0 vì các nhà phát triển đã cung cấp một giải pháp thay thế cho chú thích, tức là `@SpringBootApplication.`

[@SpringBootApplication]() : Nó là sự kết hợp của 3 chú thích: `@EnableAutoConfiguration`, `@ComponentScan`, `@Configuration.`


## Spring MVC and REST Annotations:

[@RequestMapping]() :  nó được sử dụng để map các request. Nó có nhiều phần tử tùy chọn như `consumes`, `header`, `method`, `name`, `params`, `path`, `produces`, và `value`. Chúng tôi sử dụng nó với lớp cũng như phương thức

[@GetMapping]() : nó map HTTP GET request trên method cụ thể. Nó dùng để tạo một điểm cuối trong web service, và nó được sử dụng thay cho `@RequestMapping(method = RequestMethod.GET)`.

[@PostMapping](): sử dụng khi gửi data tới server để tạo ra tài nguyên mới. Thay cho `@RequestMapping(method = RequestMethod.POST)`.

[@PutMapping](): sử dụng để thay đổi thông tin của một tài nguyên đã tồn tại trong hệ thống bằng cách sử dụng nội dung trong body của request. Nó được sử dụng thay vì sử dụng: `@RequestMapping (method = RequestMethod.PUT)`.

[@DeleteMapping](): sử dụng để xóa một resource chỉ định. Nó được sử dụng thay vì sử dụng: @RequestMapping (method = RequestMethod.DELETE).


## TỔNG HỢP TÀI LIỆU LẬP TRÌNH

[@PatchMapping](): Sử dụng để áp dụng sửa đổi 1 phần cho resource. Nó được sử dụng thay vì sử dụng: `@RequestMapping (method = RequestMethod.PATCH)`

[@RequestBody](): Nó được sử dụng để liên kết yêu cầu HTTP với một đối tượng trong một tham số phương thức. Bên trong nó sử dụng `HTTP MessageConverters` để chuyển đổi phần thân của yêu cầu. Khi chúng tôi chú thích một tham số phương thức với `@RequestBody`, Spring sẽ liên kết phần body yêu cầu HTTP đến với tham số đó.

[@RequestHeader](): Nó được sử dụng để lấy thông tin chi tiết về tiêu đề yêu cầu HTTP. Chúng tôi sử dụng chú thích này như một tham số phương thức. Các phần tử tùy chọn của chú thích là `name`, `required`, `value`, `defaultValue`. Đối với mỗi chi tiết trong tiêu đề, chúng ta nên chỉ định các chú thích riêng biệt. Chúng ta có thể sử dụng nó nhiều lần trong một phương pháp.

[@RestController]():  là một composed annotation được kết từ annotation @Controller và @ResponseBody, khi đặt một annotation @RestController trên một class controller thì mọi method controller trong class đó sẽ được thừa hưởng annotation `@ResponseBody` và response data trong controller này sẽ được trả về dưới dạng `message`.

 
## HTTP Status Code

- [200 OK]() : Mã này chỉ ra rằng yêu cầu thành công và nội dung phản hồi được trả lại cho máy khách khi thích hợp.
- [201 OK]() : Mã này chỉ ra rằng yêu cầu thành công và tài nguyên mới được tạo.
- [400 Bad Request]() : Mã này cho biết rằng máy chủ không thể xử lý yêu cầu do cú pháp không đúng định dạng trong yêu cầu. Khách hàng có thể thử lại sau khi sửa yêu cầu.
- [401 Unauthorized]() :  Mã này chỉ ra rằng xác thực là bắt buộc đối với tài nguyên. Khách hàng có thể thử lại với xác thực phù hợp.
- [403 Forbidden]() : Mã này chỉ ra rằng máy chủ đang từ chối trả lời yêu cầu ngay cả khi yêu cầu hợp lệ. Lý do sẽ được liệt kê trong nội dung cơ thể nếu yêu cầu không phải là phương thức HEAD.
- [404 Not Found]() : Mã này chỉ ra rằng tài nguyên được yêu cầu không được tìm thấy tại vị trí được chỉ định trong yêu cầu.
- [500 Internal Server Error]() : Mã này biểu thị thông báo lỗi chung và cho biết đã xảy ra lỗi không mong muốn trên máy chủ và yêu cầu không thể thực hiện được.


## @PatchMapping, @DeleteMapping, @GetMapping, @PutMapping ...

@DeleteMapping có các phần tử tùy chọn sau, các Anotation khác cũng dùng các phần tử tùy chọn này.

1. [`consumes`](): Được sử dụng để chỉ định các định dạng phương thức này có thể xử lý. Nếu yêu cầu DELETE có định dạng không nằm trong danh sách được chỉ định ở consumes, thì phương thức sẽ không được gọi.
2. [`headers`](): Cho phép bạn chỉ định các header của yêu cầu HTTP mà phải tồn tại để phương thức DELETE được gọi.
3. [`name`](): Được sử dụng để đặt tên cho phương thức, điều này có thể hữu ích trong việc tạo các bản đồ ánh xạ URL tùy chỉnh.
4. [`path`](): Chỉ định một đường dẫn URI mà phải khớp với yêu cầu DELETE để phương thức xử lý.
5. [`produces`](): Được sử dụng để chỉ định các định dạng phản hồi mà phương thức này có thể tạo ra. Nếu yêu cầu DELETE không thể chấp nhận một định dạng nằm trong danh sách produces, thì phương thức sẽ không được gọi.
6. [`value`](): Định nghĩa một hoặc nhiều đường dẫn URI mà phương thức này sẽ xử lý.


## Các Anotation phổ biến:

- [@Bean](): Chú thích @Bean được sử dụng để đánh dấu một phương thức trong một lớp cấu hình (thường được đánh dấu bằng @Configuration) để chỉ định rằng phương thức đó sẽ tạo và cấu hình một bean trong container Spring. 

```java
@Configuration
public class AppConfig {
    
    @Bean
    public MyService myService() {
        return new MyServiceImpl();
    }
}
```

- [@Qualifier](): Chú thích @Qualifier được sử dụng để chỉ định một bean cụ thể mà bạn muốn sử dụng khi có nhiều bean cùng kiểu được đăng ký trong container Spring. Điều này giúp Spring hiểu rõ bạn muốn sử dụng bean nào trong trường hợp có nhiều sự lựa chọn.

```java
@Autowired
@Qualifier("myService")
private MyService service;
```

- [@Autowired](): Chú thích @Autowired được sử dụng để tiêm các phụ thuộc (dependencies) vào các bean tự động. Spring sẽ tự động tìm kiếm bean phù hợp kiểu và đặt nó vào biến được đánh dấu bằng @Autowired.

```java
@Component
public class MyComponent {
    
    @Autowired
    private MyService service;
}
```

- [@Configuration](): Chú thích @Configuration được sử dụng để đánh dấu một lớp là một lớp cấu hình Spring. Các phương thức đánh dấu bằng @Bean trong lớp cấu hình này sẽ tạo và cấu hình các bean trong container Spring.

```java
@Configuration
public class AppConfig {
    
    @Bean
    public MyService myService() {
        return new MyServiceImpl();
    }
}
```

- [@PropertySource](): Chú thích @PropertySource được sử dụng để chỉ định các tệp cấu hình nơi Spring sẽ tìm kiếm thuộc tính để cấu hình các bean. Thuộc tính được sử dụng trong @Value hoặc @Autowired để cấu hình các giá trị từ tệp cấu hình.

```java
@Configuration
@PropertySource("classpath:myapp.properties")
public class AppConfig {
    
    // ...
}
```

- [@Import ](): Chú thích @Import được sử dụng để import các cấu hình Spring khác vào cấu hình hiện tại. Điều này cho phép bạn tổ chức cấu hình thành các module riêng biệt và kết hợp chúng lại.

```java
@Configuration
@Import({AppConfig1.class, AppConfig2.class})
public class AppConfig {
    
    // ...
}
```

- [@ImportResource](): Chú thích @ImportResource được sử dụng để import các tệp cấu hình XML vào cấu hình Spring. Điều này hữu ích khi bạn có các tệp cấu hình XML cũ hoặc các tệp cấu hình từ các thư viện khác.

```java
@Configuration
@ImportResource("classpath:beans.xml")
public class AppConfig {
    
    // ...
}
```

- [@Lazy](): Chú thích @Lazy được sử dụng để chỉ định rằng một bean sẽ được tạo chỉ khi nó được yêu cầu lần đầu tiên, không tự động khi ứng dụng khởi động.

```java
@Component
@Lazy
public class MyLazyBean {
    
    // ...
}
```

- [@Primary](): Chú thích @Primary được sử dụng để xác định một bean là ưu tiên (primary) khi có nhiều bean cùng kiểu được đăng ký. Khi có nhiều sự lựa chọn, bean được đánh dấu bằng @Primary sẽ được Spring sử dụng mặc định.

```java
@Component
@Primary
public class MyPrimaryBean {
    
    // ...
}
```

- [@PostConstruct and @PreDestroy]():
  - @PostConstruct được sử dụng để xác định một phương thức sẽ được gọi sau khi bean được khởi tạo.
  - @PreDestroy được sử dụng để xác định một phương thức sẽ được gọi trước khi bean bị hủy.
 
```java
@Component
public class MyComponent {
    
    @PostConstruct
    public void init() {
        // Thực hiện các tác vụ sau khi bean được khởi tạo
    }
    
    @PreDestroy
    public void cleanUp() {
        // Thực hiện các tác vụ trước khi bean bị hủy
    }
}
```

- [@Repository](): Chú thích @Repository được sử dụng để đánh dấu một lớp là một bean có liên quan đến lớp truy cập cơ sở dữ liệu (DAO - Data Access Object).

```java
@Repository
public class UserRepository {
    
    public User getUserById(Long id) {
        // Thực hiện truy vấn cơ sở dữ liệu để lấy người dùng theo ID
    }
}
```

- [@Service](): Chú thích @Service được sử dụng để đánh dấu một lớp là một bean chứa các logic nghiệp vụ (business logic). Nó thông báo cho Spring rằng lớp đó nên được quản lý bởi Spring container và thực hiện các tác vụ liên quan đến xử lý logic của ứng dụng.

```java
@Service
public class UserService {
    
    @Autowired
    private UserRepository userRepository;
    
    public User getUserById(Long id) {
        return userRepository.getUserById(id);
    }
}
```

- [@Controller and @RestController]():
   - @Controller được sử dụng cho việc xử lý các yêu cầu HTTP và trả về các view hoặc template.
   - @RestController kết hợp giữa @Controller và @ResponseBody, chỉ định rằng phương thức trong lớp sẽ trả về dữ liệu dưới dạng phản hồi HTTP (thường là JSON).

```java
@Controller
public class UserController {
    
    @Autowired
    private UserService userService;
    
    @GetMapping("/users/{id}")
    public String getUser(@PathVariable Long id, Model model) {
        User user = userService.getUserById(id);
        model.addAttribute("user", user);
        return "user-details";
    }
}

@RestController
@RequestMapping("/api/users")
public class UserApiController {
    
    @Autowired
    private UserService userService;
    
    @GetMapping("/{id}")
    public ResponseEntity<User> getUser(@PathVariable Long id) {
        User user = userService.getUserById(id);
        return ResponseEntity.ok(user);
    }
}
```

- [@Component, @Controller, @Repository và @Service](): Chú thích @Component, @Controller, @Repository, và @Service đều là các phân loại con của @Component. Chúng được sử dụng để đánh dấu các lớp là các thành phần của ứng dụng và cho phép Spring quản lý và quản lý các bean đó.

```java
@Component
public class MyComponent {
    
    // ...
}
```

- [@Scope](): Chú thích @Scope được sử dụng để chỉ định phạm vi sống (scope) của một bean. Trong trường hợp prototype, mỗi lần bean được yêu cầu, một instance mới của bean sẽ được tạo ra.

```java
@Component
@Scope("singleton")
public class MySingletonBean {
    
    // ...
}
```

- [@PathVariable](): Chú thích @PathVariable được sử dụng trong các phương thức của Controller để ràng buộc một biến trong URL thành một tham số trong phương thức.

```java
@Controller
@RequestMapping("/api")
public class ApiController {
    
    @GetMapping("/users/{id}")
    public ResponseEntity<User> getUser(@PathVariable Long id) {
        User user = userService.getUserById(id);
        return ResponseEntity.ok(user);
    }
}
```

- [@ResponseBody](): Chú thích @ResponseBody được sử dụng để chỉ định rằng một phương thức trong một Controller sẽ trả về dữ liệu dưới dạng phản hồi HTTP, thường là JSON. Nó giúp bạn trả về dữ liệu thay vì các view hoặc template.

```java
@RestController
@RequestMapping("/api/users")
public class UserApiController {
    
    @GetMapping("/{id}")
    public ResponseEntity<User> getUser(@PathVariable Long id) {
        User user = userService.getUserById(id);
        return ResponseEntity.ok(user);
    }
}
```

- [@RequestBody](): Chú thích @RequestBody được sử dụng để ràng buộc dữ liệu từ phần thân của yêu cầu HTTP vào các tham số của phương thức trong Controller. Nó giúp bạn lấy dữ liệu từ phần thân yêu cầu (thường là JSON) và ánh xạ chúng vào các đối tượng Java.

```java
@RestController
@RequestMapping("/api/users")
public class UserController {
    
    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        // Xử lý logic để tạo mới người dùng từ dữ liệu yêu cầu
    }
}
```

- [@ResponseStatus](): Chú thích @ResponseStatus được sử dụng để đặt giá trị mã trạng thái HTTP của phản hồi khi một phương thức trong Controller được gọi. Nó cho phép bạn thiết lập trạng thái phản hồi tùy ý.

```java
@RestController
@RequestMapping("/api/users")
public class UserController {
    
    @PostMapping
    @ResponseStatus(HttpStatus.CREATED)
    public void createUser(@RequestBody User user) {
        // Xử lý logic để tạo mới người dùng từ dữ liệu yêu cầu
    }
}
```

- [@Async](): Chú thích @Async được sử dụng để đánh dấu một phương thức để được thực hiện bất đồng bộ. Khi gọi phương thức này, nó sẽ chạy trên một luồng riêng biệt và không chặn luồng chính.

```java
@Service
public class MyService {
    
    @Async
    public CompletableFuture<String> doSomethingAsync() {
        // Xử lý công việc bất đồng bộ và trả về một Future
    }
}
```

- [@SpringBootTest](): Chú thích @SpringBootTest được sử dụng trong kiểm thử để tạo ra một ứng dụng Spring Boot hoàn chỉnh để kiểm tra toàn bộ hệ thống ứng dụng.

```java
@RunWith(SpringRunner.class)
@SpringBootTest
public class MyApplicationTests {
    
    // Kiểm tra toàn bộ ứng dụng Spring Boot
}
```

- [@SpringBootTest vs @WebMvcTest]():
  - @SpringBootTest được sử dụng để kiểm thử toàn bộ ứng dụng Spring Boot, trong khi
  - @WebMvcTest được sử dụng để kiểm thử một phần của ứng dụng liên quan đến lớp Controller và cấu hình MVC.
 
```java
@RunWith(SpringRunner.class)
@SpringBootTest
public class MyApplicationTests {
    
    // Kiểm tra toàn bộ ứng dụng Spring Boot
}

@RunWith(SpringRunner.class)
@WebMvcTest(UserController.class)
public class UserControllerTests {
    
    // Kiểm tra Controller liên quan đến User
}
```

- [@DataJpaTest](): Chú thích @DataJpaTest được sử dụng để kiểm thử các thành phần liên quan đến JPA (Java Persistence API) trong ứng dụng Spring Boot.

```java
@RunWith(SpringRunner.class)
@DataJpaTest
public class UserRepositoryTests {
    
    // Kiểm tra các phương thức liên quan đến JPA
}
```

- [@GetMapping, @PostMapping, @PutMapping, @DeleteMapping and @PatchMapping](): Chú thích @GetMapping, @PostMapping, @PutMapping, @DeleteMapping, và @PatchMapping được sử dụng để đánh dấu các phương thức trong Controller để xử lý các yêu cầu HTTP tương ứng.


- [@EnableAutoConfiguration](): Chú thích @EnableAutoConfiguration được sử dụng để kích hoạt tính năng tự động cấu hình (auto-configuration) của Spring Boot. Khi bạn sử dụng chú thích này, Spring Boot sẽ tự động cấu hình các bean và các cài đặt dựa trên các thư viện và các phụ thuộc trong classpath của ứng dụng.

```java
@SpringBootApplication
public class MyApplication {
    
    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }
}
```

- [@SpringBootApplication](): Chú thích @SpringBootApplication là một chú thích tổng hợp bao gồm ba chú thích khác: @Configuration, @EnableAutoConfiguration, và @ComponentScan. Nó được sử dụng để đánh dấu một lớp chính của ứng dụng Spring Boot và kích hoạt các cấu hình tự động và quét các thành phần của ứng dụng.

```java
@SpringBootApplication
public class MyApplication {
    
    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }
}
```



