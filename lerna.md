- references
https://juejin.cn/post/6844903985900421127#heading-17


- 初始化
lerna init
Fixed/Locked 模式（默认）
Independent 模式（--independent）  --independent 或 -i

- 安装所有依赖
lerna bootstrap
lerna bootstrap --registry https://registry.npmjs.org/

- 为packages文件夹下的package安装依赖
lerna add <package>[@version] [--dev] [--exact] # 命令签名
lerna add dva-cli --scope=pck-2
lerna add module-1 --scope=module-2 # 将 module-1 安装到 module-2
lerna add module-1 --scope=module-2 --dev # 将 module-1 安装到 module-2 的 devDependencies 下
lerna add module-1 # 将 module-1 安装到除 module-1 以外的所有模块
lerna add babel-core # 将 babel-core 安装到所有模块

- 卸载依赖
lerna exec -- <command> [..args] # 在所有包中运行该命令  
lerna exec --scope=npm-list  yarn remove listr # 将 npm-list 包下的 listr 卸载
lerna exec -- yarn remove listr # 将所有包下的 listr 卸载


- 清理依赖包
lerna clean

- 检测模块是否发生过变更
lerna diff 
lerna updated 

- 创建模块
 lerna create <name>
 erna import <dir>  dir 是本项目外的包含 npm 包的 git 仓库路径（相对于本项目根路径的相对路径）

 - 查看模块列表
lerna list

- 运行 script 脚本
lerna run <script> -- [..args] # 在所有包下运行指定

- 版本迭代
$ lerna version [major | minor | patch | premajor | preminor | prepatch | prerelease]
$ lerna version 1.0.1 # 按照指定版本进行迭代
$ lerna version patch # 根据 semver 迭代版本号最后一位
$ lerna version       # 进入交互流程选择迭代类型 
--conventional-changelog
--changelog-preset

- 发布
lerna publish
lerna publish from-git
