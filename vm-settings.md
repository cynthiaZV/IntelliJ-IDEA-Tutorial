
## 编译阶段

- 路径: `Settings | Build, Execution, Deployment | Compiler > Build Process`
- 以下两个类型选一个:
- Shared build process: 该配置存储到 .idea 的 compiler.xml 文件中，该文件可以提交到 git 方便团队成员公用项目配置(团队成员电脑都不错的情况下可以公用)
  - Shared heap size >> 2000 Mbytes
  - Shared VM options >> -Xmx3g
- User-local build process: 该配置存储到 .idea 的 workspace.xml 文件中，一般不提交到 git，属于个人配置
  - User-local heap size >>  2000 Mbytes
  - User-local VM options >> -Xmx3g


## Maven 配置

- 路径: `Settings | Build, Execution, Deployment | Build Tools | Maven`
  - Thread count 填写你 CPU 中 performance core 的数量
  - macOS 查看核心命令: 
```
system_profiler SPHardwareDataType | grep -i "core"
结果如下，我是 8 个性能核心，所以这里建议填写 8
Total Number of Cores: 12 (8 performance and 4 efficiency)
```

- 路径: `Settings | Build, Execution, Deployment | Build Tools | Maven | Importing`
  - `VM options for importer：` 填写 `-Xmx1500m`
- 路径: `Settings | Build, Execution, Deployment | Build Tools | Maven | Runner`
  - `VM options: ` 填写 `-Xmx1500m`


## Spring Boot 项目运行

- 点击右上角运行类的下拉框: `Edit Configurations`
- 在 Run/Debug Configurations 弹出框, 点击 `modify options` 在出现的选项列表中选择: `Add VM Options`
- 这时候 Run/Debug Configurations 界面就多了一个 VM Options 输入框: `Xmx2000m`
