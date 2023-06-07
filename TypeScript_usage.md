## TypeScript开发环境搭建

- #### 下载并安装node.js

  - 官网下载msi文件

- #### npm全局安装typescript

  - *typescript就是ts代码的解析器*

  - ```shell
    npm i -g typescript
    ```

- #### 编写一个ts文件
- #### 配置编译器
  * 默认就算有语法错误，编译器也可以生成js文件。ts可以转换为任意版本的js。这些都可以通过配置编译器来设置

- #### 使用tsc对ts文件进行编译

  - <u>要先进入ts所在目录终端</u>

  - ```shell
    tsc xxx.ts
    ```

  - 同目录下生成了一个同名的js文件
  - 编译好的js文件依然是无类型限制，只是在ts中降低出错

- #### 在html文件中引入编译好的js文件

<font color="#890" size=10 face="宋体">阿斯弗</font>
