# Git Flow


## 1. master
所有的协作者和操作都直接在master分支上进行
#### 1.1. 冲突，如果操作公共模块/同一份代码，pull操作可能需要频繁的解决冲突
#### 1.2. 并行，多个需求同时进行的时候，只能把代码整个copy一份了
#### 1.3. 测试，如果出现bug，问题和责任追踪会变得困难
#### 1.4. 发布，master混入了太多特性，要么容易出bug，要么会出现发布时的等待
#### 1.5. 撤销，撤销可能会影响bugfix或者feature

![](https://github.com/cf95a728f034df41e0d664c2290dd21a/git_flow/blob/master/1.git_master.png)


## 2. master-feature
#### 2.1. 测试，没有明确的测试分支
#### 2.2. 版本，虽然没有明确的版本概念，但可以通过wiki记录commit id
每个协作者都有自己的feature分支，完成之后发pull-request申请merge到master

![](https://github.com/cf95a728f034df41e0d664c2290dd21a/git_flow/blob/master/2.git_master_feature.png)


## 3. master-test-feature
#### 3.1. 粒度
#### 3.2. 版本，虽然没有明确的版本概念，但可以通过wiki记录commit id
每个协作者都有自己的feature分支，feature上开发完成之后merge到test分支
test分支定期和master同步（清除废弃的特性）
测试通过之后，feature发pull-request申请merge到master

![](https://github.com/cf95a728f034df41e0d664c2290dd21a/git_flow/blob/master/3.git_master_test_feature.png)


## 4. master-dev/test-feature
#### 4.1. 权限，直接修改/合并master，缺少review，风险很大
1. 直接修改master分支上的代码
2. 将分支merge到master，由开发者自己进行，而不是发pull-request

#### 4.2. 粒度，test/release角色混在一起
3. dev分支同时扮演test和release角色
4. 对分支的应用比较少

## 5. master-develop-release-feature-hotfix
### 5.1. main
主分支通常来讲伴随着代码的整个生命周期
#### 5.1.1. master
#### 5.1.2. develop
### 5.2. support
辅助分支通常来讲生命周期有限
#### 5.2.1. feature
#### 5.2.2. release
#### 5.2.3. hotfix

![](https://github.com/cf95a728f034df41e0d664c2290dd21a/git_flow/blob/master/4.git_flow.png)

![](http://images.cnitblog.com/blog/564490/201309/05090350-fe547d6e4eee4a59b606483a4cb8908c.png)
![](http://images.cnitblog.com/blog/564490/201309/05090438-7c7ea7047cff4d559e47a62308bcb47e.png)
![](http://images.cnitblog.com/blog/564490/201309/05132525-b921c42450674a50b2c03b414557c800.png)


## 6. references
#### 6.1. [nvie](http://nvie.com/posts/a-successful-git-branching-model/) (原文)
#### 6.2. [cnblogs](http://www.cnblogs.com/baiyw/p/3303125.html) (译文)
