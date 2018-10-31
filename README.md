<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans-4.2.xsd">
        
        
     <!-- 注册spring bean -->
     <!-- dao 的 bean -->
     <bean id="userDao" class="com.bwf.dao.impl.UserDaoPhoneImpl" >
     	<!-- 从外部给bean 注入成员属性的值  -->
     	<property name="age" value="18"></property>
     </bean>
     
     <!-- <bean id="userDao2" class="com.bwf.dao.impl.UserDaoAccountImpl"></bean> -->
        
     <bean id="userService" class="com.bwf.service.UserService">
     	<property name="userDao" ref="userDao"></property>
     </bean>  
     
     
     <!-- 注意：所有的参考的ref都是参考 注册过的 bean id -->
     <bean id="test" class="com.bwf.service.TestService" >
     	<!-- 通过 setter 注入 -->
     	<property name="userDao" ref="userDao" ></property>
     </bean>
     
     <bean id="test1" class="com.bwf.service.Test1Service" >
     	<!-- 通过 构造器 注入 -->
     	<constructor-arg name="userDao" ref="userDao"></constructor-arg>
     </bean>
     
     
     <bean id="user" class="com.bwf.entity.User">
     	<property name="username" value="赵六"></property>
     	<property name="password" value="123"></property>
     </bean>
     
     <bean id="dog1" class="com.bwf.entity.Dog">
     	<property name="type" value="哈士奇"></property>
     </bean>
    <!--  <bean id="testScope" class="com.bwf.test.TestScope" scope=""></bean>-->
     
     <bean id="dog3" class="com.bwf.entity.Dog">
     	<constructor-arg value="哈巴狗"></constructor-arg>
     </bean >
     
     
     
     
        
</beans>
