# I choose to learn Spring as the first and probably main route for my backend projects. It is said thay Spring is the most popular framework for java because it is a huge and practical ecosystem with high stability. It is also said it has a great community support and modern tools. Here, I will note my tips, thoughts and progress through my first project coding adventure.

##(Date of notes between 1-5: 05/08/2026)

### 001: @Autowired is deprecated and Constructor Injection is recommended as the best practice.
### Note: In @Autıwired, dependencies cannot be declared as final. This may cause some changes in dependecies. It is also hard to test it with mock and new. There are also risks for circular and secret dependencies. Using Construcor injection is a far better option.
public class UserController {

    private final UserService userService; 
    
    (Put @RequiredArgsConstructor annotation at top or write the constructor manually.)
}

### 002: @GeneratedValue(strategy = GenerationType.X) is the main strategy for deciding how to produce primary key (id). There are 5 main strategies as I learn:

- IDENTIFY: ID determined with SQL's AUTO_INCREMENT system. Suitable for MySQL and SQL Server.
- AUTO: ID determined by Hibernate/JPA. This method chooses the best strategy by looking at DB.
- SEQUENCE: Allocets and knows the ID before even insertion. Best option for PostgeSQL and Oracle.
- TABLE: Slowes one for the databases that don't support sequence.
- UUID: Most modern and safe choice. Creates a long and secure unique ID.

### 003: Important annotations and their uses as I learn:
### Fundamental annotations:

@SpringBootApplication: Used for marking the main class. Also encapsulates @Configuration, @EnableAutoConfiguration, and @ComponentScan annotations.
@EnableAutoConfiguration: Used with @Configuration on it's top for allow 
@ConditionalOnClass -@ConditionalOnMissingBean - @ConditionalOnBean - @ConditionalOnProperty; Annotations that decides the conditions of AutoConfig.
@EnableAsync and @EnableScheduling: Enabler annotations. Generally used with main class, but sometimes we use them with config classes in specifid needs.
@Async: Allows us to use multi-threading in a more easier way.
@Scheduled: Allows us to set a timer to plan the working time of a method (NOTE: The method annotated with @Scheduled must have a void return type.) (NOTE: Before Java 8, use @Schedules annotation for multi-scheduled methods.).
