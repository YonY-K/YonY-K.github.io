---
title: "Github Action과 aws의 ec2, rds 사용해서 Spring boot 프로젝트 배포하기-Github Action 설정"
tag: study_theories
---

## Github Action 설정

### Github Secrets 사용해서 민감정보 관리하기

**application.yml, application.properties** 같은 설정 파일에서는 유출되어서는 안되는 **민감한 정보**가 올라가기 마련이다.<br>
이런 **민감 정보는 되도록 깃에 올리지 않는 것이 좋은데** 그러면 깃을 pull 받을 때 필요한 정보를 다른 곳에 저장해뒀다가 그때그때 추가해줘야하는 **불편함이 발생**한다.<br>
이를 해결하기 위한 방법으로 나는 크게 두가지 방법을 사용하는데 하나는 **서브모듈**을 사용하는 것이고 하나는 **Github Secrets** 을 이용하는 것이다. <br>
오늘은 후자의 방법을 사용해서 배포할 때 깃에 올라가 있지 않은 **yml 파일이 자동적으로 배포파일에 추가되어 build** 되게 해볼것이다.<br>
보통은 yml 파일 자체를 올리지는 않고 **yml 파일에 사용되는 일부 민감정보의 값만**을 올린다.<br>
우리 프로젝트는 yml 파일을 깃에 전혀 올리지 않기 때문에 yml 파일 자체를 올려서 사용해보겠다.<br>

- 프로젝트 **리포지터리 메인 화면**에서 **Settings 탭**을 클릭한다. 

[![01 settings 클릭](https://github.com/yony-k/yony-k.github.io/assets/109204976/ced5288b-8bd3-45ae-b162-f5121e14386c)](https://github.com/yony-k/yony-k.github.io/assets/109204976/ced5288b-8bd3-45ae-b162-f5121e14386c)

- **Security -> Secrets and variables -> Actios** 경로로 들어가 Repository secrets 에서 **new repository secrets** 을 클릭해준다.

[![02 secrets and variables 클릭 new 클릭](https://github.com/yony-k/yony-k.github.io/assets/109204976/0eaa7135-d737-4104-87dd-37e2bad7950d)](https://github.com/yony-k/yony-k.github.io/assets/109204976/0eaa7135-d737-4104-87dd-37e2bad7950d)

- **Name**에 값을 빼내올 때 사용할 **키의 이름**, **Scret**에 저장해야할 **값**을 넣고 **Add secret** 하면 된다.

[![03 입력 방법](https://github.com/yony-k/yony-k.github.io/assets/109204976/0696a49b-110c-43b1-8a9f-87b308765a42)](https://github.com/yony-k/yony-k.github.io/assets/109204976/0696a49b-110c-43b1-8a9f-87b308765a42)

- **aws 지역**, **IAM 사용자 액세스 키**, **application.yml** 을 등록해놨다.

[![04 설정한 키들](https://github.com/yony-k/yony-k.github.io/assets/109204976/081507e1-9497-46d7-816e-8bd50188e75e)](https://github.com/yony-k/yony-k.github.io/assets/109204976/081507e1-9497-46d7-816e-8bd50188e75e)

- application.yml 의 경우 전체 내용을 **Base64로 인코딩** 한후 넣어줬는데 [이 사이트](https://www.convertstring.com/ko/EncodeDecode/Base64Encode)를 이용하면 편리하다.

### worlflows 생성

깃허브 액션을 사용하려면 **worlflows** 를 생성해줘야한다.<br>
worlflows 란 깃허브에 **특정 이벤트가 발생했을 때 자동적으로 실행되는 작업 흐름**을 의미한다.<br>

- 프로젝트 **리포지터리 메인화면**에서 **Actions 탭** 클릭

[![13 action 클릭](https://github.com/yony-k/yony-k.github.io/assets/109204976/9fe4a3a5-3eab-4a41-8a21-443c4709285a)](https://github.com/yony-k/yony-k.github.io/assets/109204976/9fe4a3a5-3eab-4a41-8a21-443c4709285a)

- 우리 프로젝트는 메이븐으로 만들어졌으므로 **Java with Maven 의 Configure** 클릭

[![06 Actions 클릭했을 때](https://github.com/yony-k/yony-k.github.io/assets/109204976/767f627e-5cc2-4917-b73a-eece21450f9b)](https://github.com/yony-k/yony-k.github.io/assets/109204976/767f627e-5cc2-4917-b73a-eece21450f9b)

- 자동적으로 빌드와 관련된 작업흐름이 적힌 파일이 생성된다. <br>
현재 우리는 ci/cd 작업을 하기 위해서 Java with Maven 을 선택했지만 해야할 작업에 따라 **자율적으로 작성**하면 된다.<br>
**파일 이름**을 원하는데로 수정하고 아래 내용을 붙여넣기 한다.

[![07 build with maven 선택했을 때](https://github.com/yony-k/yony-k.github.io/assets/109204976/7791aa39-a39b-4ba3-b72b-a60404fe3d77)](https://github.com/yony-k/yony-k.github.io/assets/109204976/7791aa39-a39b-4ba3-b72b-a60404fe3d77)

```yml
name: Deploy to Amazon EC2

env:
  PROJECT_NAME: "vitabucket_public"
  BUCKET_NAME: "vita-s3"
  CODE_DEPLOY_APP: "vita-codedeploy-app"
  CODE_DEPLOY_DEPLOYMENT_GROUP: "vita-codedeploy-app-deployment-group"

on:
  push:
    branches: [ "main" ]
    
jobs:

  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    
    # ubuntu 서버에 JDK 17 설치
    - name: Set up JDK 17
      uses: actions/setup-java@v3
      with:
        java-version: '17'
        distribution: 'corretto'
        cache: maven
    
    # 디펜던시를 캐싱하는 부분으로 빌드 작업시간 단축
    - name: Cache Maven packages
      uses: actions/cache@v2
      with:
        path: ~/.m2
        key: ${{ runner.os }}-m2-${{ hashFiles('**/pom.xml') }}
        restore-keys: ${{ runner.os }}-m2

    # 시크릿에 올려놓은 yml 파일을 가져온다.
    - name: make yml
      run: |
        cd $PROJECT_NAME
        echo "${{ secrets.APPLICATION_YML }}" | base64 --decode > src/main/resources/application.yml
      shell: bash
    
    # 빌드
    - name: Build with Maven
      run: mvn clean package --file $PROJECT_NAME/pom.xml
    
    # 빌드된 war 파일을 ROOT.war 로 이름을 바꾸고 최상위 경로로 옮긴다.
    - name: rename and move ROOT
      run: |
        mv $PROJECT_NAME/target/*.war $PROJECT_NAME/target/ROOT.war
        mv ./$PROJECT_NAME/target/ROOT.war ./
      shell: bash
    
    # ROOT.war 파일과 appspec.yml 파일, scripts 파일을 zip 으로 압축 
    - name: Make zip file
      run: zip -R $PROJECT_NAME.zip ./appspec.yml ./ROOT.war ./scripts/*
      shell: bash

    # AWS 인증
    - name: Configure AWS credentials
      uses: aws-actions/configure-aws-credentials@v1
      with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: ${{ secrets.AWS_REGION }}

    # s3 버킷에 zip 파일 업로드
    - name: Upload to AWS S3
      run: aws s3 cp --region ap-northeast-2 ./$PROJECT_NAME.zip s3://$BUCKET_NAME/$GITHUB_SHA.zip
    
    # codedeploy 어플리케이션에 배포 명령
    - name: Deploy to AWS EC2 from S3
      run: |
        aws deploy create-deployment \
          --application-name ${{ env.CODE_DEPLOY_APP }} \
          --deployment-config-name CodeDeployDefault.AllAtOnce \
          --deployment-group-name ${{ env.CODE_DEPLOY_DEPLOYMENT_GROUP }} \
          --s3-location bucket=$BUCKET_NAME,key=$GITHUB_SHA.zip,bundleType=zip
```

- s3 버킷의 이름과 codedeploy의 이름은 해당 서비스를 가면 확인할 수 있다.

[![10 s3 이름](https://github.com/yony-k/yony-k.github.io/assets/109204976/02f53f79-93a1-47d0-8b42-b8fb29f426c7)](https://github.com/yony-k/yony-k.github.io/assets/109204976/02f53f79-93a1-47d0-8b42-b8fb29f426c7)

[![11 codedeploy 이름](https://github.com/yony-k/yony-k.github.io/assets/109204976/b0c20e5f-8da9-404e-bd28-85a689349ee1)](https://github.com/yony-k/yony-k.github.io/assets/109204976/b0c20e5f-8da9-404e-bd28-85a689349ee1)

### appspec.yml 생성

- codedeploy가 수행할 명령을 작성한 **appspec.yml** 을 생성한다.

```yml
version: 0.0
os: linux

files:
  - source:  /
    destination: /home/ec2-user/spring-github-action
    overwrite: yes

permissions:
  - object: /
    pattern: "**"
    owner: ec2-user
    group: tomcat
    mode: 775

hooks:
  BeforeInstall:
    - location: scripts/stop.sh
      timeout: 60
      runas: ec2-user
  AfterInstall:
    - location: scripts/deploy.sh
      timeout: 60
      runas: ec2-user
  ApplicationStart:
    - location: scripts/start.sh
      timeout: 60
      runas: ec2-user
```

- 이 파일은 **리포지터리의 최상단**에 위치시킨다.

[![08 파일들 경로](https://github.com/yony-k/yony-k.github.io/assets/109204976/32e6e1b9-8a00-44eb-b016-809848166d0d)](https://github.com/yony-k/yony-k.github.io/assets/109204976/32e6e1b9-8a00-44eb-b016-809848166d0d)

### 배포 스크립트 생성

appspec.yml 에서 총 **세개의 sh 파일**을 실행하도록 되어있다.<br>
이 세개의 sh 파일을 만들어서 **scripts 폴더**에 넣어줘야한다.<br>

- **stop.sh**

```sh
cd /home/tomcat/apache-tomcat-10.1.20/bin
sh ./shutdown.sh
rm -rf /home/tomcat/apache-tomcat-10.1.20/work/Catalina/localhost/ROOT
rm -rf /home/tomcat/apache-tomcat-10.1.20/webapps/ROOT
rm -rf /home/tomcat/apache-tomcat-10.1.20/webapps/ROOT.war
```

- **deploy.sh**

```sh
mv '/home/ec2-user/spring-github-action/ROOT.war' '/home/tomcat/apache-tomcat-10.1.20/webapps'
```

- **start.sh**

```sh
cd /home/tomcat/apache-tomcat-10.1.20/bin
sh ./startup.sh
sudo chmod -R 770 /home/tomcat/
```

- 위 파일들을 scripts 폴더에 같이 넣어놓고 마찬가지로 **리포지터리의 최상단**에 위치시킨다.

[![09 scripts 경로](https://github.com/yony-k/yony-k.github.io/assets/109204976/6793502b-da7c-4745-846d-5b330a6368c4)](https://github.com/yony-k/yony-k.github.io/assets/109204976/6793502b-da7c-4745-846d-5b330a6368c4)

[![08 파일들 경로](https://github.com/yony-k/yony-k.github.io/assets/109204976/de223c3c-7421-4582-9c43-7a5b607d36ff)](https://github.com/yony-k/yony-k.github.io/assets/109204976/de223c3c-7421-4582-9c43-7a5b607d36ff)

### 실행

이제 깃허브에 **push** 하면 설정한 **workflows** 가 실행된다.<br>
**실행결과는 Actions 탭**에서 확인할 수 있다.<br>

[![12 실행화면](https://github.com/yony-k/yony-k.github.io/assets/109204976/8157b68d-f055-47ba-9456-cfd4874a4f8a)](https://github.com/yony-k/yony-k.github.io/assets/109204976/8157b68d-f055-47ba-9456-cfd4874a4f8a)

---

### 참고블로그

[Git secrets yml 파일 올리기](https://velog.io/@balparang/Github-Secret-%EC%9C%BC%EB%A1%9C-yml-%ED%8C%8C%EC%9D%BC-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0)

[Github Action으로 민감정보 관리하기](https://velog.io/@sun1203/Github-Action-Spring-Application.properties-%EB%AF%BC%EA%B0%90%EC%A0%95%EB%B3%B4-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0)

[Git secrets으로 민감정보 관리하기 1](https://keeeeeepgoing.tistory.com/170)

[Git secrets으로 민감정보 관리하기 2](https://velog.io/@marigold1/Github-action-%ED%99%98%EA%B2%BD%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-%ED%95%B4%EA%B2%B0)