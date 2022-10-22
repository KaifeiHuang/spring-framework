## Spring源码里的命名习惯

### XXXAware
代表XXX装配中心, DI提供XXX类。实现者可通过该类获取XXX。是spring提供的一个扩展点。   

缺点： 使得code与spring API耦合了, 未遵循spring IOC风格

- ApplicationContextAware提供ApplicationContext
```java
public interface ApplicationContextAware extends Aware {
    void setApplicationContext(ApplicationContext applicationContext) throws BeansException;
}
```

- BeanFactoryAware提供BeanFactory
```java
public interface BeanFactoryAware extends Aware {
	void setBeanFactory(BeanFactory beanFactory) throws BeansException;
}
```
- ApplicationEventPublisherAware提供ApplicationEventPublisher
```java 

public interface ApplicationEventPublisherAware extends Aware {

	/**
	 * Set the ApplicationEventPublisher that this object runs in.
	 * <p>Invoked after population of normal bean properties but before an init
	 * callback like InitializingBean's afterPropertiesSet or a custom init-method.
	 * Invoked before ApplicationContextAware's setApplicationContext.
	 * @param applicationEventPublisher event publisher to be used by this object
	 */
	void setApplicationEventPublisher(ApplicationEventPublisher applicationEventPublisher);

}
```

FactoryBean与BeanFactory