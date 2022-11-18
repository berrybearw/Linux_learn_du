# Linux_learn_du
du ( 查看目錄使用多少大小 )

參考 : 

https://stackoverflow.com/questions/15141588/exclude-all-permission-denied-messages-from-du

https://www.notion.so/du-11b0db1171f5483194cdf1e0925b6cd0#f1a47f2118bb46e7bbc6cf3b0c6ddb17

常用參數
---
- h   : 用易懂格式顯示
- k   : 用 kb 格式顯示大小
- a   : 各別計算大小
- s   : 整個目錄加總 

```
通常是
du -參數 或
du -參數 *
差異在於 * 可以幫助列表區分每個檔案與目錄
```

範例 : 

```bash
du -h
```
![image](https://user-images.githubusercontent.com/96226780/202670880-a65422b4-4035-4194-9dc8-259bc6e1351e.png)

```bash
du -k
```
![image](https://user-images.githubusercontent.com/96226780/202671065-16f34cb4-5ef1-4bca-a4f1-87634e43e118.png)

```bash
du -a
```
![image](https://user-images.githubusercontent.com/96226780/202671254-93f65bc8-e003-4778-8cc9-64b8cbdc9204.png)

```bash
du -s
```
![image](https://user-images.githubusercontent.com/96226780/202671372-aa704367-18bb-47a8-8396-04df8156fe50.png)

```bash
#不顯示當下目錄 總合
du -sh *
#顯示各別檔案 大小與當下目錄總合
du -ah
```
![image](https://user-images.githubusercontent.com/96226780/202671506-e07d0622-06e3-4eb8-9958-f086a79dac60.png)


du 排序
---
- 依照 kb : 

```bash
du -s | sor -rn
```

- 依照易讀懂格式 : 
```
du -sh | sort -h -r
( 此方式需確認 sort 是否有 參數 h )
```

du 不顯示 錯誤訊息在畫面
---
```bash
du -sh 2>&1
```

查看每個目錄檔案數
---
```bash
du -a | cut -d/ -f2 | sort | uniq -c | sort -nr
```

![image](https://user-images.githubusercontent.com/96226780/202669333-21cd13a5-02bc-4542-9068-302dfc2c3da1.png)
