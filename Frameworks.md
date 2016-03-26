Frameworks
========
*tl;dr*

[React (Javascript)](https://facebook.github.io/react/)
- Isomerphic 
- Element
  - `React.DOM.div({attributes},{element1},{elementS})`
- Props `this.props.<props>`
  - Things that being passed to components OR to other components
  - Everything that's not an HTML attribute
  - Can be used with `map`, `forEach` to mapped to perform function or return react element(s)
  - Validating props (making sure if it's there, if it's the correct type, if it's part of an array value):
  - Defaulting props (if turns out to be empty):
  
  ```javascript
  React.createClass({
    propTypes: {
      description: React.PropTypes.string,
      category: React.PropTypes.oneOf(['News','Photos']).isRequired,
      dialog: React.PropTypes.instanceOf(Dialog).isRequired
    },
    getDefaultProps: function() {
        return {
          value: 'default value'
        };
      }
    ...
  });
  ```
  
- Children: get children item
  - `React.Children.map(children, function(child){})`
  - `React.Children.count(children)`
  - `React.Children.only(children)`
- Spread attribute: `<ShoppingTotal {...this.props} />`
  - To pass the props to the other component
  - Works for any JS object
- propTypes: `React.PropTypes.___`
  - Static typing component's props (specifying what comes in)
  - Types: number, string, func, bool, array, object, node, element
  - Member: 
    - `instanceOf(class)`
    - `oneOf([val1,val2])`
    - `arrayOf(propType)`
    - `objectOf(propType)`
  - Example:
  ```javascript
  React.createClass({
    propTypes: {
        items: React.PropTypes.arrayOf(React.PropTypes.object)
    },
    getDefaultProps: function() {
      return {
        foo: 'foo'
      };  
    }
    ...
  });
  ```
- Local State: `this.state`
  - Does not get pass down from above
  - `this.setState({foo: 'bar'})` will trigger re-render
    - Can be using it sparingly by using jquery to manage the state (also Backbone)
  - `getInitialState()`
- React lifecycle methods:
  - `componentWillMount`: before 
  - `componentDidMount`: after
  - `componentWillReceiveProps(newProps)`: when have gotten new props
  - `componentWillUpdate(newProps, newState)`: after get new state, but before renders into DOM
  - `componentDidUpdate(oldProps, oldState)`: right after things goes into DOM
  - `componentWillUnmount`
  - `shouldComponentUpdate(nextProps, nextState)`:
    - Invoked before rendering when new props or state are being received
    - Use this as an opportunity to `return false` when you're certain that the transition to the new props and state will not require a component update.

[Hapi (Javascript)](http://hapijs.com/)
------------------------------------
- Very lightweight javascript server side application framework
- Requirement: Node.js (+ npm)
- Getting started
  1. Create nodejs app: `npm init`
  2. Add Hapi as your app dependencies: `npm install hapi --save`
  3. Create `server.js` file and create `new Hapi.Server();`
  4. Run your app by running `npm start`

Spring (java)
------
- Lightweight alternative to J2EE (achieve capabilities of EJB with simple POCO)
- Initially requires configurations using XML, it has changed ever since:
  - Version 2.5 by using Component based scanning
  - Version 3 by using Annotation
- How to start developing application with Spring:
  1. A project structure, complete with a Maven or Gradle build file including required dependencies. At the very least, you’ll need Spring MVC and the Servlet API expressed as dependencies.
  2. A web.xml file (or a WebApplicationInitializer implementation) that declares Spring’s DispatcherServlet.
  3. A Spring configuration that enables Spring MVC.
  4. A controller class that will respond to HTTP requests with “Hello World”.
  5. A web application server, such as Tomcat, to deploy the application to.

Spring Boot (java/groovy)
----------------
- Suites best with Microservice architecture
- Spring Boot allows developers to start with minimum dependencies to start with Spring Framework
- Capabilities:
  1. Automatic configuration— Spring Boot can automatically provide configuration for application functionality common to many Spring applications. [Spring docs on it](https://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-auto-configuration.html)
  2. Starter dependencies— You tell Spring Boot what kind of functionality you need, and it will ensure that the libraries needed are added to the build. [List of starters](https://github.com/spring-projects/spring-boot/tree/master/spring-boot-starters)
  3. The command-line interface— This optional feature of Spring Boot lets you write complete applications with just application code, but no need for a traditional project build.
  4. The Actuator— Gives you insight into what’s going on inside of a running Spring Boot application.
- What it does not:
  1. Spring Boot is not an application server. It has bare minimum app server (Jetty?)
  2. Spring Boot doesn’t implement any enterprise Java specifications such as JPA or JMS
  3. Spring Boot doesn’t employ any form of code generation to accomplish its magic
- Installing:
  1. Download and extract Spring Boot CLI [v1.3.2](http://repo.spring.io/release/org/springframework/boot/spring-boot-cli/1.3.2.RELEASE/spring-boot-cli-1.3.2.RELEASE-bin.zip)
  2. Set up JAVA_HOME, SPRING_HOME & PATH to include SPRING_HOME\bin
  3. Test with `spring --version`
- Initializing:
  * Option 1: Call `spring init -dweb --build gradle -p war <appname>` `-d: dependencies ... --build: build type ... -p extract as ...`

  * Option 2: Open [Spring Initializer](http://start.spring.io/) site
- Structures:
  - Entry point class: For configuration and bootstrapping
    - The `@SpringBootApplication` enables Spring component-scanning and Spring Boot auto-configuration. In fact, `@SpringBootApplication` combines three other useful annotations:
      1. Spring’s `@Configuration`—Designates a class as a configuration class using Spring’s Java-based configuration. Although we won’t be writing a lot of configuration in this book, we’ll favor Java-based configuration over XML configuration when we do.
      2. Spring’s `@ComponentScan`—Enables component-scanning so that the web controller classes and other components you write will be automatically discovered and registered as beans in the Spring application context. A little later in this chapter, we’ll write a simple Spring MVC controller that will be annotated with `@Controller`so that component-scanning can find it.
      3. Spring Boot’s `@EnableAutoConfiguration`—This humble little annotation might as well be named `@Abracadabra` because it’s the one line of configuration that enables the magic of Spring Boot auto-configuration. This one line keeps you from having to write the pages of configuration that would be required otherwise.

- Running:
  1. From gradle: `gradle bootRun` or `gradle build && java -jar <app>-0.01.SNAPSHOT.jar`

:date: **As of 20 February 2016**

- Create Simple App:
  1.  Define domain (POJO):
    ```
    @Entity
    public class Book {

        @Id
        @GeneratedValue(strategy=GenerationType.AUTO)
        private Long id;
        private String isbn;
        private String title;
        private String author;

        public Long getId() {
          return id;
        }

        public void setId(Long id) {
          this.id = id;
        }

        public String getIsbn() {
          return isbn;

        }

        public void setIsbn(String isbn) {
          this.isbn = isbn;
        }

        public String getTitle() {
          return title;
        }

        public void setTitle(String title) {
          this.title = title;
        }

        public String getAuthor() {
          return author;
        }

        public void setAuthor(String author) {
          this.author = author;
        }
    }
    ```

  2. Define repository:
    ```
      public interface BookRepository extends JpaRepository<Book, Long> {
          List<Book> findByTitle(String title);
      }
    ```

  3. Define controller:
    ```
    @Controller
    @RequestMapping("/")
    public class BookController {

      private BookRepository bookRepository;

      @Autowired
      public BookController(
                 BookRepository bookRepository) {
        this.bookRepository = bookRepository;
      }

      @RequestMapping(value="/{title}", method=RequestMethod.GET)
      public String booksByTitle(
          @PathVariable("title") String title,
          Model model) {

        List<Book> books =
            bookRepository.findByTitle(title);
        if (books != null) {
          model.addAttribute("books", books);
        }
        return "books";
      }

      @RequestMapping(value="/{title}", method=RequestMethod.POST)
      public String addToBooks(@PathVariable("title") String title, Book book) {
        book.setTitle(title);
        bookRepository.save(book);
        return "redirect:/{title}";
      }
    }
    ```
