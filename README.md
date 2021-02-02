# kaptcha-2.3.2.jar
用于javaweb中生成图片验证码的jar包。

前端页面的使用用法：
<img src="kaptcha.jpg>这里直接导入在配置文件的验证码图片地址，地址是在配置文件中所配置好的。
          
在配置文件web.xml中的用法：
<servlet>
    <servlet-name>Kaptcha</servlet-name>
    <servlet-class>com.google.code.kaptcha.servlet.KaptchaServlet</servlet-class>
</servlet>
 <servlet-mapping>
    <servlet-name>Kaptcha</servlet-name>
    <url-pattern>/kaptcha.jpg</url-pattern>
 </servlet-mapping>    
 
 在web层即servelt中的用法：
 1.获取Session域中的验证码
    String token=(String)request.getSession().getAttribute(KAPTCHA_SESSION_KEY);
 2.防止重复提交表单的方法就是访问到之后，删除验证码，如果再次提交表单就会因为验证码错误，导致无法再次提交表单。
    request.getSession().removeAttribute(KAPTCHA_SESSION_KEY);
 3.验证码判断   
  if(token!=null&&token.equalsIgnoreCase(code){}
      
