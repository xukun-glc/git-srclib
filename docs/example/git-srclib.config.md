# 关于 git-srclib.config 文件的说明

    通常，这个配置文件放在“目的地” Git 仓库的根文件夹里；但是，根据需要，也可以放在具体的项目文件夹里。
    而对于“源”仓库，这个文件必须放在根文件夹里面。

# import.*
    在“目的地”仓库中，需要配置“import.*” 属性。

### import.{name}.src
    这个是“源”仓库的 URL 。

### import.{name}.name
    这是“源”仓库中，export.{name} 中的 “name”。

### import.{name}.version (默认=main)
    这个表示源码库的版本，它可以是 Git 仓库的某个分支的名称，
    也可以是具体的某个commit或者tag的 SHA-1 ID。
    如果配置为具体的版本ID，目标文件夹里的源码版本将被“锁定”在这个版本上，无法通过“git srclib pull”命令更新。

### import.{name}.path （默认=./.srclib/${lib_name}）
    这个路径指向代码的“目标”文件夹。

### import.{name}.readonly （默认=1）
    如果=1, 表示签出的源代码是只读的；
    如果=0，表示签出的源代码可以被改写。

### import.{name}.gitignore （默认=0）
    如果=1，运行该命令将自动添加忽略项到“目标”文件夹旁边的“.gitignore”文件里面；
    如果=0，不会进行相关操作。

# export.*
    在“源”仓库中，需要配置“import.*” 属性。

### export.{name}.path
    这个路径指向代码的“来源”文件夹。
