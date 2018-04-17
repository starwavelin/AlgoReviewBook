# Fork Command

### Forking Workflow
![alt text](./pics/forking.jpg "Forking Workflow")

#### 把老师项目Fork到我的账户下，并保证master branch同步
1. Click the Fork button from the teacher's repo -> A project with the same name as Teacher's project should appear in my account
2. ```$ git clone https://github.com/MY_ACCOUNT_NAME/PROJECT_NAME.git```
3. Starting from Step 4, I am tring to 保证master branch同步
4. 跟上游仓库同步代码之前，必须配置过 remote，指向上游仓库。 Here 上游仓库 = Teacher's Repo  
```$ git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git```  
在第4步完成后，我们用 ```$ git remote -v``` 就可以看到remote端多了两组upstream(fetch & push):  
```
$ git remove -v
origin https://github.com/MY_ACCOUNT_NAME/PROJECT_NAME.git (fetch)
origin https://github.com/MY_ACCOUNT_NAME/PROJECT_NAME.git (push)
upstream https://github.com/TEACHER_ACCT_NAME/PROJECT_NAME.git (fetch)
upstream https://github.com/TEACHER_ACCT_NAME/PROJECT_NAME.git (push)
```

5. 从上游仓库获取到分支，及相关的提交信息，它们将被保存在本地的 ```upstream/master``` 分支  
```$ git fetch upstream```
6. Switch my local repo's master branch  
```$ git checkout master```
7. Merge upstream's master into my local repo's master  
```$ git merge upstream/master```
8. If needed, I can push my local master branch to my remote repository  
```$ git push```

#### 我的项目的starwavelin分支要和老师项目的starwavelin分支保持一致
1. 在我项目的local repository建立一个branch叫starwavelin  
```$ git checkout -b starwavelin```
2. 在这个项目中做一些修改，并提交，push到我的远程repo
3. 由于我有老师项目的权限，在老师项目的远程Repo中创建一个分支叫starwavelin  
4. 在GitHub上，我的账户下(此时也包括老师的账户下)的项目中，都会出现 Compare & pull request 按钮。点击这个按钮
5. 在开启的Open a pull request页面中,  
base fork: 老师账户/项目名字  
base: starwavelin  
head fork: 我的账户/项目名字  
compare: starwavelin
6. 确定Branches对应关系正确后，点击 Create pull request 按钮。  
7. 确定我项目的Branch starwavelin 和 base branch: ```TEACHER_ACCT:starwavelin```无conflicts后，点击 Merge pull request按钮。
8. 点击 Confirm Merge 按钮      
reference: https://www.zhihu.com/question/21682976/answer/79489643

#### Understand the Pull Request button
GitHub中，Pull Request means 上图中的第6步，是希望别人（Joe）来拉我的修改。这不一定能实现，要看别人是否同意；他同意了也就实现了。

