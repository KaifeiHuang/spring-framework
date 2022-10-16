
- spring里说的bean依赖是什么？
一个bean持有其他bean的引用

- 依赖注入体现
    - 构造方法注入(spring推荐，可以防止非空)
      - 可能造成循环依赖(action: 编辑源代码,将构造方法注入改为setter注入)
    - 属性注入(可以重新注入依赖)
    - 循环依赖问题
- 几个关键
  - beanDefination
    - 配置bean依赖

## FAQ
- Spring如何解决Spring创建的容器单例BeanA依赖多例的BeanB？
  实现ApplicationContextAware,通过它的getBean("B")来获取
