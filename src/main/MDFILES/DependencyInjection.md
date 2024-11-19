# Dependency injection
- Refers to injecting data into a class using constructor of another class/interface
- It is preferred to use interfaces to utilize dependency injection
- By using DI we can access `data/methods/variables` we previously couldn't

## Example:

- @Component refers to class being spring component
- @RequiredArgsConstructor is annotation from lombok project which auto generates needed `constructors/getters/setters` at runtime
```java
@Component
@RequiredArgsConstructor
public class BootstrapData implements CommandLineRunner {
    private final BeerRepository beerRepository;
    private final CustomerRepository customerRepository;

    @Override
    public void run(String... args) throws Exception {
        loadBeerData();
        loadCustomerData();
    }
}
```