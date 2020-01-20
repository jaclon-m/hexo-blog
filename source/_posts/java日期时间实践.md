
---
title: java日期时间实践
categories: javaSE核心技术
tags: java日期时间
archives: 2020-01
---
## 类型汇总

- java.util.Date
- org.joda.time.*
- java.time.*
在java7中使用的是java.util.Date,无论是和数据库交互，还是用于时间的计算，都很不方便，java8以后出了java.time.*包（LocalDateTime、LocalDate、LocalTime等），专门用于日期时间的计算。`Joda-Time`是用于处理日期时间的一个工具包，该包的作者参与了java8日期时间的开发，并且`Joda-Time`在1.7&1.8版本都能用，是一个不错的工具包。它基本包含了jdk1.8中的日期时间功能，还有部分扩展。

## 使用

- java.util.Date与java.time.LocalDateTime互转
```
LocalDateTime startTime = LocalDateTime.ofInstant(reqInfo.getStartTime().toInstant(), ZoneId.systemDefault());
LocalDateTime endTime = LocalDateTime.ofInstant(reqInfo.getEndTime().toInstant(), ZoneId.systemDefault());
```
```
Date.from(start.atZone(ZoneId.systemDefault()).toInstant())
```

- java.util.Date与org.joda.time.LocalDateTime互转
```
LocalDateTime time = new LocalDateTime(date.getTime());
```
```
Date date = localDateTime.toDate();
```

- java.time.LocalDateTime与org.joda.time.LocalDateTime互转
额，这两个还是不要转了吧，类名都是一样的，类里面的方法也一样，`Joda-Time`可以看做是jdk1.8的扩展。

## 参考链接

[JDK8中 Date、LocalDateTime、LocalDate、LocalTime、Joda-Time互转](https://blog.csdn.net/weixin_38294999/article/details/90267049)
[Joda-Time 简介l](https://www.ibm.com/developerworks/cn/java/j-jodatime.html)

