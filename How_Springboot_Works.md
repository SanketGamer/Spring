problem 1 : why we always not asign new because we have to create a object and the way is new class()

@SpringBootApplication
public class MyAppApplication {
    public static void main(String[] args) {
        SpringApplication.run(MyAppApplication.class, args);
        `` problem is if i do this it create another object but spring ioc container he creates object for his own ``
        Dev obj=new Dev();
        obj.build();
    }
}

problem 2 : why we need application context
ApplicationContext context;

ApplicationContext is the Spring container.
👉 It is responsible for:
Creating objects (beans)
Managing their lifecycle
Injecting dependencies
Providing configuration & resources

--> what we do is 
ApplicationContext context=SpringApplication.run(MyAppApplication.class, args);  //what it does springapplication returns application context and application context create ioc container

--> What is a Bean?
A bean is an object that is created, managed, and controlled by Spring’s IoC container (ApplicationContext).

--> context always return beans
 Dev obj=context.getBean(Dev.class);

it give still err so we have to use @Componenet
@Component  //it means this this the class i have to manage now spring will create object for u
