# blog
> 2022 7/19
- 打算做一个个人blog 
- swagger版本 导致了很多意想不到的错误，移除了
- 学习一下日志记录
  - [推荐](https://blog.csdn.net/qq_35787138/article/details/81009056)
  -  日志可以输出成html形式，但是时间好像错位了，但是个人感觉比输出成txt好
-  [重定向和转发]( https://www.bilibili.com/video/BV1vt4y1i7Vy?spm_id_from=333.337.search-card.all.click&vd_source=afdbe5eeb7dd29283083f0417f15b5d0)
- 现在在看登录拦截器
  - 拦截器由一个拦截逻辑和拦截哪些网站构成
  - 拦截逻辑经常用getsession，session可以保存信息，也就是你拦截器中getsession(sth)就对应你controller中 session.setattr()
  - 
- 拦截器拦截哪些网站我们在配置类中配置 
  - 配置类就是为了不写xml等配置文件，直接用[类代替](https://blog.csdn.net/qq_43203949/article/details/118762655)
  - 配置类 [参考](https://blog.csdn.net/weixin_45433031/article/details/121846207)
  - [视图解析器了解一下](https://blog.csdn.net/JerryWu666/article/details/116498075)
  - 拦截器的原理是 先看配置文件中拦截哪些请求，在经过拦截逻辑看返回 true还是false; false仍然无法访问请求
  - :angry: 找了好久，使用[support](https://blog.csdn.net/u012862619/article/details/81557779?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165822627116781790739227%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165822627116781790739227&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-81557779-null-null.142^v32^pc_rank_34,185^v2^control&utm_term=%E6%8B%A6%E6%88%AA%E5%99%A8%E6%97%A0%E6%95%88&spm=1018.2226.3001.4187) 拦截器改动后需要重启
  - ```java
    @Configuration
    public class config extends WebMvcConfigurationSupport {
    @Autowired
    private logininterception logininter;

    @Override
    public void addInterceptors(InterceptorRegistry registry) {
    //        registry.addInterceptor(logininter).addPathPatterns("/**");
        super.addInterceptors(registry);
    }

    }

-拦截器还可以做统计，记录在日志里面
- 

































