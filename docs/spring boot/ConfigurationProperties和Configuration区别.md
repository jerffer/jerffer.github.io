# ConfigurationProperties和Configuration区别

## ConfigurationProperties

```java
@Component
@ConfigurationProperties(prefix = "order")
public class OrderProperties {
    private Integer payTimeoutSeconds;
    private Integer createFrequencySeconds;

    public Integer getPayTimeoutSeconds() {
        return payTimeoutSeconds;
    }

    public void setPayTimeoutSeconds(Integer payTimeoutSeconds) {
        this.payTimeoutSeconds = payTimeoutSeconds;
    }

    public Integer getCreateFrequencySeconds() {
        return createFrequencySeconds;
    }

    public void setCreateFrequencySeconds(Integer createFrequencySeconds) {
        this.createFrequencySeconds = createFrequencySeconds;
    }
}
```

## Configuration

```java
@Data
@Configuration
public class Order {
    @Value("${order.pay-timeout-seconds}")
    private int payTimeoutSeconds;
    @Value("${order.create-frequency-seconds}")
    private int createFrequencySeconds;

}
```

其中，<code>@Value</code> 注解是 Spring 所提供，<code>@ConfigurationProperties</code> 注解是 Spring Boot 所提供。
