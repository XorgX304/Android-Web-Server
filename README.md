# Android Web Server (FireFly)
Simple and Small footprint TCP/IP Web Server for Android in Java

This is standalone, multithreaded, almost or No dependancy ! http server in Java with example use in Android.

Features supported
- Support basic GET, POST requests
- Render html files
- Render jpeg,png,gif
- Custom api for dynamic web pages (mvc)
- Support javascript rendring
- Multithreaded, support mulitple client

What it does not do?
- File upload, video rendering


# Getting Started
## How to use it in Android?

1.  Copy TinyWebServer.java class from src dir to your android project package
2.  Call following from android service or process
    

       ```java
       @Override
       protected void onCreate(Bundle savd){
            super.onCreate(savd);
            ...
           //call contructor with local ip, port , public html directory path
           TinyWebServer.startServer("localhost",9000, "/web/public_html");
       }
       
       @Override
       public void onDestroy(){
           super.onDestroy();
            //stop webserver on destroy of service or process
            TinyWebServer.stopServer();
       }
       ```

## How to write custom api? 

1.  Copy AppApis.java from src directory
2.  keep the package name same for AppApis.java like "appapis.queryfiles" 
3.  open AppApis.java and write your own mehtod/function inside AppApis.java 
    for example,

    ```java
    public String myfirstapi(HashMap qparms){
      //todo - write your api logic here
      //qparms is collection of GET and POST parameters
    }
    ```
    
    you can access this api -> http://localhost/myfirstapi
    
    

## How to check demo?
   - Run the code and hit browser with http://localhost:9000/helloworld 
   - here port number is 9000 
   - localhost or your device ip address
   - helloworld is api method inside AppApis.java
   
   ![Demo ScreenShot](https://github.com/sonuauti/Android-Web-Server/blob/master/demo.png)
  
  
    Design, Build, Tested by
    ![twitter](https://help.twitter.com/content/dam/help-twitter/twitter_logo_blue.png)  ![github](https://avatars0.githubusercontent.com/u/9919?s=280&v=4) /@sonuauti
    
