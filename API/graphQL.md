## REST_API FLAW

* Main Reason
    * 會不斷成長的 Endpoint 數量
        * graphql 可以有一個end point
    * client with customized requst -> middle man handle it -> grab data from different sources
        * solves problem like over fetching and under fetching

* others
    * 參數、回傳值型別不固定
      * graphql 有固定型別
      * 必須通過graphql validation
    * 多版本時，前後端常不匹配
      * graphql 前後端共用schema
    * 會拿多餘的欄位
      * graphql 清楚條列要拿的欄位
    * 不容易處理巢狀資源
      * details
        * put user into post
        * graphql
          * 指定巢狀資料


* [why graphQL](https://medium.com/free-code-camp/so-whats-this-graphql-thing-i-keep-hearing-about-baf4d36c20cf)
