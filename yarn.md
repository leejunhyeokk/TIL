# yarn

- 의존성 관리를 위한 JS 패키지 매니저 (프로젝트에서 외부의 어떤 라이브러리를 사용하느 있는지를 별도로 관리)

  -> 이는 어떤 라이브러리를 사용하는지 남들이 알게 하기 위해서 사용한다. (협업에서 중요)

- java의 gradle, php의 composer와 같은 역할을 한다. (빌드 도구)



## NPM과의 차이점

FACEBOOK(yarn을 만들었다.)은 NPM과의 차이를 아래와 같이 소개했다.



- Ultra Fast(고속)
  \-다운로드한 모든 패키지를 캐시하므로 다시 다운로드할 필요가 없습니다. 또한 운영을 병렬화하여 리소스 활용률을 극대화하므로 설치 시간이 그 어느 때보다 단축됩니다.

  

- Mega Secure(보안)

  \- 체크섬을 사용하여 코드가 실행되기 전에 설치된 모든 패키지의 무결성을 확인합니다.

  

- Super Reliable(신뢰성)
  \- 상세하고 간결하며 잠금 파일 형식과 설치용 결정 알고리즘을 사용하여 한 시스템에서 작동하는 설치가 다른 시스템에서 정확히 동일한 방식으로 작동하도록 보장할 수 있습니다.

  

- Offline Mode(오프라인모드)
  \- 이전에 패키지를 설치한 경우 인터넷 연결 없이 패키지를 다시 설치할 수 있습니다.

  

- Deterministic(결정적)
  \- 설치 순서와 관계없이 모든 시스템에 동일한 종속성이 동일한 방식으로 설치됩니다.

  

- Network Performance(네트워크 성능)
  \- 네트워크 활용도를 극대화하기 위해 요청을 효율적으로 대기열에 올리고 요청 폭포를 방지합니다.

  

- Same Packages(동일 패키지)
  \- npm의 패키지를 설치하고 패키지 workflow를 동일하게 유지합니다.

  

- Network Resilience(네트워크 복구)
  \- 요청 실패 한 번으로 인해 설치에 실패하지 않습니다. 실패 시 요청이 재시도됩니다.

  

- Flat Mode(플랫 모드)
  \- 중복 항목을 생성하지 않으려면 일치하지 않는 버전의 종속성을 단일 버전으로 해결합니다.





### yarn 설치하기

```javascript
//yarn 설치
$ sudo apt-get update && sudo apt-get install yarn

//만약 설치가 안된다면 npm을 통해 설치
$ npm install -g yarn

// path설정
$ echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bashrc

//설치 버전 확인
$ yarn --version
1.13.0

// self update 
$ yarn self-update
```



### yarn 삭제하기

```javascript
//package.json, yarn.lock 에서 패키지를 제거합니다.
$ yarn remove request
```



### 프로젝트 실행하기

```javascript
$ yarn start
```

