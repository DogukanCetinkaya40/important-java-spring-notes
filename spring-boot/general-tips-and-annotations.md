# I choose to learn Spring as the first and probably main route for my backend projects. It is said thay Spring is the most popular framework for java because it is a huge and practical ecosystem with high stability. It is also said it has a great community support and modern tools. Here, I will note my tips, thoughts and progress through my first project coding adventure.

##( 05/08/2026)

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
