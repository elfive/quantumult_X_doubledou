# quantumult_X_doubledou

1. 因为网站在特定时间会对中国大陆进行屏蔽，所以建议将网站加入proxy规则中：

    ```
    [filter_local]
    host-suffix, aaaa.gay, proxy
    ```

2. MITM

    ```
    [mitm]
    hostname= *.aaaa.gay
    ```

3. 获取Cookies

    ```
    [rewrite_local]
    # 获取Cookies
    ^https:\/\/aaaa\.gay\/user\/panel url script-request-header https://raw.githubusercontent.com/elfive/quantumult_X_doubledou/main/v2e.fun.cookie.js
    
    # 如果是把脚本下载到 iCloud云盘/Quantumult X/Scripts 文件夹中本地运行则使用以下设置
    ^https:\/\/aaaa\.gay\/user\/panel url script-request-header v2e.fun.cookie.js
    ```

4. 增加task自动签到任务

    ```
    [task_local]
    30 8 * * * https://raw.githubusercontent.com/elfive/quantumult_X_doubledou/main/v2e.fun.js, tag=v2e签到, enable=true
    
    # 如果是把脚本下载到 iCloud云盘/Quantumult X/Scripts 文件夹中本地运行则使用以下设置
    30 8 * * * v2e.fun.js, tag=v2e签到, enable=true
    ```

