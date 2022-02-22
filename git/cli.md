# git CLI

## 👀 참조 링크

📎 <a href="https://levelup.gitconnected.com/top-30-git-commands-you-should-know-to-master-git-cli-f04e041779bc" target="_blank">git 필수 명령어 관련 블로그</a>  
📎 <a href="https://tapajyoti-bose.medium.com/advanced-git-concepts-you-should-know-f617e79f3edf" target="_blank">알면 좋은 git concepts</a>  
📎 <a href="https://velog.io/@njs04210/Git-reset과-revert-알고-사용하기" target="_blank">revert와 reset의 차이</a>

---

## 1. Repository 초기화

```
git init
```

## 2. working directory에서 staging area로 파일 추가하기

```
git add file.js
git add .
git add *
```

- \*의 경우 .gitignore에 있는 파일들도 staged 된다
- \.의 경우 .gitignore에 있는 파일을 제외하고 staged 된다

## 3. commit하기

```
git commit -m "text"
git commit -am "text"
```

commit을 되돌리는 방법들

- git reset: 커밋 취소
- git revert: 커밋 되돌리기
- git amend: 커밋 덮어쓰기

### 1) 마지막 커밋을 수정하고 싶다면

```
git commit -amend -m "text"
```

### 2) 원하는 커밋을 삭제하고 싶다면

돌아가길 원하는 커밋으로 reset시키기

```
git reset --mixed [hash]
```

- soft 옵션으로 진행하면 변경 이력은 삭제되고 staged된 상태
- mixed 옵션으로 진행하면 변경 이력만 삭제되고 변경 내용은 보존
- hard 옵션으로 진행하면 변경 이력과 내용 모두 삭제

reset 명령어는 협업시, 원격에 push 되었을 때 사용하지 않는 것이 좋음

### 3) 현재 상태를 유지하면서 과거의 특정 커밋만 변경하고 싶을 때

```
git revert [hash]
git revert --no-commit [hash]
```

로컬과 원격에서 히스토리가 차이가 날 때 아래와 같은 명령어를 사용하여
연결할 수 있으나 협업시에는 사용하지 않는 것이 좋음

```
git push --force
```

### 4) reset과 revert의 차이

- reset: 시간을 아예 특정 사건으로 되돌리는 것
- revert: 현재의 상태를 유지하면서 특정 사건만 삭제하는 것

## 4. Repository 상태 확인하기

현재 modified 상태인지, unmodified인지, tracked 되었는지 등을 확인할 수 있다

```
git status
```

## 5. 커밋 히스토리 보기

```
git log
```

## 6. 특정 커밋을 자세히 보기

```
git show [hash]
```

## 7. 커밋하기 전 코드 변경 사항을 확인하기

```
git diff
```

## 8. 파일 및 디렉토리 삭제와 이름 변경

```
git rm dirname/file.js
git mv dirname/file.js
```

## 9. 브랜치에 관한 명령어

```
git branch [branch name]
git checkout -b [branch name]
git branch
git branch -d [branch name]
```

### 1) 브랜치 삭제에 관한 옵션

- -d 옵션으로 브랜치 삭제시 main 브랜치에 병합된 상태가 아니라면 에러가 발생
- -D 옵션으로 브랜치 삭제시 현재 상태와 상관없이 브랜치가 삭제됨

### 2) 원격 저장소에 있는 브랜치를 삭제하고 싶다면

```
git push origin --delete [branch name]
```
