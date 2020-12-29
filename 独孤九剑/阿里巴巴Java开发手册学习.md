# 阿里巴巴Java开发手册学习

所有的POJO类属性必须使用包装数据类型。

定义DO/DTO/VO等POJO类时，不要设定任何属性默认值。

构造方法里面禁止加入任何业务逻辑，如果有初始化逻辑，请放在init方法中。

高并发时，同步调用应该去考量锁的性能损耗。能用无锁数据结构，就不要用锁；能锁区块，就不要锁整个方法体；能用对象锁，就不要用类锁。

如果是JDK8的应用，可以使用Instant代替Date，LocalDateTime代替Calendar，DateTimeFormatter代替SimpleDateFormat，官方给出的解释：simple beautiful strong immutable thread-safe。

对于需要使用超大整数的场景，服务端一律使用String字符串类型返回，禁止使用Long类型。