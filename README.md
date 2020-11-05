### vue-login-java

---

### 配置前端跨域配置类：CorsConfig

```java
 @Configuration
 public class CorsConfig {
     private CorsConfiguration buildConfig() {
         CorsConfiguration corsConfiguration = new CorsConfiguration();
         corsConfiguration.addAllowedOrigin("*"); // 1
         corsConfiguration.addAllowedHeader("*"); // 2
         corsConfiguration.addAllowedMethod("*"); // 3
         return corsConfiguration;
     }
 
     @Bean
     public CorsFilter corsFilter() {
         UrlBasedCorsConfigurationSource source = new UrlBasedCorsConfigurationSource();
         source.registerCorsConfiguration("/**", buildConfig()); // 4
         return new CorsFilter(source);
     }
 }
```




### 错误码
> 200, "操作成功"<br>
  500, "操作失败"<br>
  404, "参数检验失败"<br>
  401, "暂未登录或token已经过期"<br>
  403, "没有相关权限"<br>

---


