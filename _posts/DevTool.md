##DevTool

### Mac path설정
1. touch ~/.bash_profile
2. vi ~/.bash_profile
3. alias 명령어 = 'cd 디렉토리의 경로', :wq
4. source ~/.bash_profile



### NODE
#### nvm
[기존 node완전 삭제 ] (https://gist.github.com/tonymtz/d75101d9bdf764c890ef)

nvm 설치
[nvm](https://github.com/creationix/nvm)
[한글설명](http://hmhv.tistory.com/38)

1. curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
2. touch .bash_profile
3. vi .bash_profile
4. enter the .bash_profile
```
export NVM_DIR="/Users/name/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
```
5. nvm install 6.9.2
6. nvm use 6.9.2

#### eslint
1. npm install -g eslint
2. 해당 프로젝트로 이동
3. eslint --init
4. popular, AirBnb, react N, JSON
5. atom eslint package install 



### Test Tool
- mocha
- sinon
- should
- should-sinon


eslint
