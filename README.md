# Full-Stack-Develop-Notes
## Front-End
  - Web development
      - HTML
      - CSS
      - JavaScript
      - DOM Web API
      - React(FaceBook)
      - Vue
      - Angular(Google)
      - jQuery (out of fashion)
      - Bootstrap (out of fashion)
      - Mobile app (key point)
  - Server
      - Tomcat
      - node.js:可以让JS在服务器运行
        - Koa
        - Express
  - DataBase
      - mongoDB
         - mongoose: connect node.js and mongoDB
      - mysql
      - What are differnece mongoDB and mysql? [Reference](https://www.geeksforgeeks.org/mongodb-vs-mysql/)
      
          | MySQL  | MongoDB                     |
          |--------|-----------------------------|
          | Table  | Collection                  |
          | Row    | Document                    |
          | Column | Field                       |
          | Joins  | Embedded documents, linking |
          
           - A Document in MongoDB
           
                 {
                 name: "Daniel",
                 age:20,
                 contact:{
                 mobile:"413406989*",
                 home-address:"Amherst"
                 }
                 }
           
           - A Record in MySQL

               | name   | age | contact-mobile | home-address |
               |--------|-----|----------------|--------------|
               | Daniel | 20  | 413406989*     | Amherst      |
      
  - Tools
      - webpack
      - git and github
## Micro-Front-End
  - WebComponents
  - 技术栈无关
  - 独立开发、独立部署
  - 独立运行
