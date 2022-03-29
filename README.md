* [obsidian\-yaml\-bulk\-edit 批量编辑yaml](#obsidian-yaml-bulk-edit-批量编辑yaml)
* [安装](#安装)
* [使用方法](#使用方法)
  * [面板批量更改YAML：具体操作](#面板批量更改yaml具体操作)
  * [表格编辑YAML：具体操作](#表格编辑yaml具体操作)
    * [代码示例](#代码示例)
  * [筛选条件说明](#筛选条件说明)
* [版本更新日志](#版本更新日志)

# obsidian-yaml-bulk-edit 批量编辑yaml

**此插件涉及到批量修改文档内容，所以使用前请进行数据备份！！使用此插件导致的任何数据丢失本人概不负责。**

## 请在使用前备份数据！！

## 请在使用前备份数据！！

## 请在使用前备份数据！！

这个插件是用来批量编辑obsidian中文档的yaml的。

插件的Github链接：https://github.com/1657744680/obsidian-yaml-bulk-edit
新版本（包括表格编辑YAML功能）功能演示视频：[obsidian批量修改文档yaml属性插件新版本演示（表格编辑YAML！！）](https://www.bilibili.com/video/BV1yu411v7Ej/)
最初版本的视频演示：[obsidian批量修改文档yaml属性插件演示](https://www.bilibili.com/video/BV1pq4y1Y7as/)

支持：

1. `添加新属性`
2. `修改属性名`
3. `修改属性值`
4. `删除属性`
5. `删除整个YAML`

# 安装

手动从release页面下载安装，或使用Brat进行安装

# 使用方法

您有两种方式操作yaml

1. 面板**批量**更改YAML
   （包括增删改属性名、改属性值、删除YAML、清理空值一系列批量操作）
   1. 输入条件筛选文档
   2. 确认筛选的文档和自己想要修改的目标文档一致
   3. 选择操作
   4. 输入参数
   5. 修改完成

2. 表格编辑YAML
   （编辑**某个文档的某个属性值**）
   1. 输入条件（可选择显示的属性及顺序）筛选文档
   2. 直接操作表格来改变某个文档的某个属性值


## 面板批量更改YAML：具体操作

面板①②③长度过长时均可以上下滑动

1. Ctrl+P调出命令面板，选择命令`YAML属性批量管理: 打开操作面板`
2. 点击命令后进入**面板①**，在这里输入条件以筛选文档，可以添加新的条件（注意：各个条件之间为与关系），输入完成后确定。目前支持以下几种条件：
   1. `yaml`——`包含/不包含`——`属性名`
   2. `yaml属性`——`属性名`——`属性值`
   3. `标签`——`包含/不包含`——`标签名`
   4. `文件名称`——`符合/不符合`——`正则表达式`
   5. `文件路径`——`符合/不符合`——`正则表达式`
   ![image](https://user-images.githubusercontent.com/39726621/160273310-6ac1ec25-ee74-430e-bc2d-901ca57b047d.png)
3. 点击确定后进入到**面板②**，这里会展示筛选的文档，当您确认文档符合要求后可选择具体操作进行下一步（如果发现显示的文档并不符合您的预期要求，那么您可以进一步选择或者关闭当前面板回到面板①重新设置条件）。可选择的操作有：
   1. `添加新属性`
   2. `修改属性名`
   3. `修改属性值`
   4. `删除属性`
   5. `删除整个YAML`
   ![image](https://user-images.githubusercontent.com/39726621/160343219-2af7c4eb-143b-4d08-bbc1-cc2c636437e7.png)
4. 点击具体操作后进入到**面板③**，在这里输入值来进行最后一步的操作。请谨慎操作！！确认输入无误后点击确定即可提交。
![image](https://user-images.githubusercontent.com/39726621/160273284-614702eb-bc59-4dfc-937a-3f55a799c1e0.png)
5. 到这里就完成批量修改操作了。
6. 对于十分重要的yaml属性值，为了避免对这些重要的属性值造成误删、误改，可以将他们添加到设置页面的`禁止删除和修改的属性名称`中，多个属性值之间以英文半角冒号`:`隔开。例如`ctime,mtime`
7. 对于想要忽略的文件夹，在设置项`需要忽略的文件夹`中输入文件夹路径，文件夹路径开头不要加`/`，多个文件夹路径仍以英文半角冒号`:`隔开。![image](https://user-images.githubusercontent.com/39726621/160343794-f8439cff-f3ed-4040-abc0-dd57ba0fe753.png)

## 表格编辑YAML：具体操作

新版本（包括表格编辑YAML功能）功能演示视频：[obsidian批量修改文档yaml属性插件新版本演示（表格编辑YAML！！）](https://www.bilibili.com/video/BV1yu411v7Ej/)

> 我不太会CSS，表格样式的代码是QQ群的`Cuman`老哥按我的要求帮忙提供的，感谢！！

1. 创建代码块`yamledit`
2. **（可选）输入要显示的属性**
   1. 以`prop:`开头；
   2. 后面每个属性之间以英文半角逗号`,`隔开；
   3. 表格显示的属性顺序和您输入的属性顺序是一致的。
3. **输入筛选条件**，参数与参数之间使用英文半角冒号`:`间隔开来。
   1. 不输入筛选条件的话就是默认筛选全部文档
   2. 多个筛选条件换行即可（多个条件之间均为与关系）
4. 操作表格编辑属性
   1. 当您操作表格的某个单元格且输入改变值时，若该单元格所对应的文档没有该单元格所对应的属性，那么插件会自动为该文档创建该属性
5. 设置项：`表格中隐藏的属性名称`，在这里输入您想要默认隐藏的属性。（如果您输入的要显示的属性中包含表格中隐藏的属性，那么该属性仍会被显示）多个要隐藏的属性以英文半角冒号`:`隔开。

### 代码示例

#### 1、没有筛选条件

1. 默认显示全部文档
2. 显示除默认隐藏属性外的所有属性

````text
```yamledit
```
````

#### 2、一个筛选条件

1. 显示除默认隐藏属性外的所有属性

````text
```yamledit
yaml:包含:导演
```
````

#### 3、两个筛选条件

1. 显示除默认隐藏属性外的所有属性

````text
```yamledit
文件路径:符合:电影/
yaml:包含:导演
```
````

#### 4、选择显示的属性和两个筛选条件

1. 按顺序显示prop属性且选中文档里存在的属性

````text
```yamledit
prop:国家,演员
文件路径:符合:电影/
yaml:包含:导演
```
````

## 筛选条件说明

每个条件之间是与关系。

| 参数1    | 参数2            | 参数3               | 说明                                         |
| -------- | ---------------- | ------------------- | -------------------------------------------- |
| yaml     | 包含<br />不包含 | 属性名              | `yaml`中`包含/不包含` `属性名`的文档         |
| yaml属性 | 属性名           | 属性值              | `yaml属性`中`属性名`值为`属性值`的文档       |
| 标签     | 包含<br />不包含 | 标签名（不带`#`号） | `包含/不包含` `标签名`的文档                 |
| 文件名称 | 符合<br />不符合 | 正则表达式          | `文件名称` `符合/不符合` `正则表达式` 的文档 |
| 文件路径 | 符合<br />不符合 | 正则表达式          | `文件路径` `符合/不符合` `正则表达式` 的文档 |



# 版本更新日志

## 0.1.0

### 增强

- [x] 支持代码块渲染为列表来编辑YAML
- [x] 设置项中添加选项：表格中隐藏的属性名称
- [x] 面板②增加操作：清理空值属性

## 0.0.3

### 增强

- [x] 支持筛选文档后进一步选择目标文档
- [x] 设置项中添加选项：忽略文件夹

## 0.0.2

### 修复
- [x] 修复`yaml属性`选择属性后搜索选框不显示全部已存在的属性值的问题
- [x] 修复未选择添加功能时自动添加`---`的问题
### 增强
- [x] 为面板③修改删除、修改属性操作的第一个输入框增加候选项
- [x] 面板②增加操作：删除整个yaml
