---
typora-root-url: /home/wlt/blog/BruceWant.github.io

---

### Relative path to certain folder

1. write following YAML Front Mater in the beginning of the file.

   ```yaml
   ---
   typora-root-url: /path_to_the_root
   ---
   ```

2. write a relative path in image.
3. For example, write typora-root-url:/User/Abner/Website/typora.io/ in YAML Front Matters, and then ![alt](/blog/img/test.png) will be treated as ![alt](file:///User/Abner/Website/typora.io/blog/img/test.png) in typora.

### 相对路径

1. 在文件开头手动输入如下 YAML 格式的绝对路径

   ```yaml
   ---
   typora-root-url: /path_to_the_root
   ---
   ```
2. 使用相对路径插入一个图片

3. 例如：

   ```
   ---
   typora-root-url:/User/Abner/Website/typora.io/
   ---
   ```

   


![alt](/blog/img/test.png) 等价于  ![alt](file:///User/Abner/Website/typora.io/blog/img/test.png)

Reference: [Relative path to certain folder](https://support.typora.io/Images/#relative-path-to-certain-folder)