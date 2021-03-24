

# Spring Core

![image-20210215212706528](image/image-20210215212706528.png)

|       Keyword        |                                                              |
| :------------------: | ------------------------------------------------------------ |
|         IoC          | Inversion of Control (IoC) / Dependency Injection (DI)       |
|   Spring Container   | Core, Bean,Context,SpEl                                      |
|      **@Bean**       | an object that is instantiated, assembled, and managed by a spring IoC container |
|   **@scope("<>")**   | default: singleton,  Prototype                               |
| Dependency Injection | one object supplies the dependencies of another object       |
|  Configuration IoC   | xml file,  java configuration class, java annotations        |
|  **@Configuration**  | used over the Congif class name                              |
|    **@Component**    | over the class, define beans,  bean name is: lowercase with class name |
|  **@ComponentScan**  | over config class;  includes controller, service, repository. <br />@ComponentScan(basePackages = ”name”) |
|    **@Autowired**    | inject beans into components                                 |
|    **@Qualifier**    | used in different implementation of bean                     |
|     **@Primary**     | used in same implementation of bean                          |
|       Bean Id        | a unique name that allows Spring to recognize each bean      |
|      **@Value**      | use value from properties file                               |
|     Environment      | use value form properties file                               |
| **@PropertySource**  | used over config class  *@PropertySource*("classpath:application.properties") |
|     **@Profile**     | allow us to configure an application in a different way for a different environment |

**Spring MVC**

**Spring Data wieh Hibernate**

**Spring Security**

**REST**

**Spring Boot**

Advantage:

​	Inversion of Control container with Dependency injection

​	AOP

​	POJO

![image-20210215150819850](image/image-20210215150819850.png)

---

## Spring Container

![image-20210215150858931](image/image-20210215150858931.png)

---

## Bean

![image-20210215151718727](image/image-20210215151718727.png)

![image-20210215151922764](image/image-20210215151922764.png)

**default bean is singleton**

---

## Inversion of Control / DI (programming principle)

https://en.wikipedia.org/wiki/Inversion_of_control

- Developer is no longer responsible for managing objects life cycle.
- Outsourcing the process of creating and managing bojects to an IOC container.

![image-20210215170605455](image/image-20210215170605455.png)

![image-20210215170722184](image/image-20210215170722184.png)



![](image/image-20210215171139984.png)

![image-20210215192500063](image/image-20210215192500063.png)

![image-20210215192912952](image/image-20210215192912952.png)

```java
@Component
public class MailService {
    ...
}
```

这个`@Component`注解就相当于定义了一个Bean，它有一个可选的名称，默认是`**mailService**`，即小写开头的类名。

![image-20210215192931966](image/image-20210215192931966.png)

![image-20210215193114259](image/image-20210215193114259.png)

![image-20210215195823526](image/image-20210215195823526.png)

![image-20210215202506443](image/image-20210215202506443.png)

![image-20210215204516086](image/image-20210215204516086.png)

![image-20210215204635852](image/image-20210215204635852.png)

Only one profile can be active at the same time, and bean without profile, not everyonewill be created always.

