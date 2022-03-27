# USAGE

템플릿 저장소에 대한 내용과 활용 방안에 대해 설명한다.

## 템플릿

기본적으로 이슈 템플릿과 풀 리퀘스트 템플릿을 제공하지 않고, 라벨 템플릿을 제공한다.

이슈 및 플 리퀘스트 템플릿은 필요에 따라 생성하면 된다. [참고](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates)

라벨 템플릿을 적용하기 위해서는 일부 작업이 필요하다. 적용 방법은 다음과 같다.

1. `github-label-sync` 라이브러리를 설치한다.
```shell
$ sudo npm install -g github-label-sync
```

2. Github 에서 `개인 액세스 토큰` 을 생성한다. [참고](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

3. 적용하고자 할 라벨을 정의한다.
   * 기본적으로 `.github/labels.json` 파일을 제공한다.

4. 라벨을 적용한다.
```shell
$ sudo github-label-sync --access-token [액세스 토큰] --labels .github/labels.json [계정명]/[저장소 이름]
```

<br>

## 프로젝트 릴리즈

`default-repo-template` 저장소에서는 release-drafter 를 활용해 릴리즈 자동화를 제공한다.

버전은 크게 major, minor, patch 로 나뉘며, 라벨 템플릿에서는 이를 구분 및 사용하기 위한 라벨이 정의되어 있다.

사용 방법은 비교적 간단하며 [여기](https://github.com/release-drafter/release-drafter) 에서 상세 내용에 대해 확인할 수 있다.

<br>

## 그 외 기타 파일

.gitignore 파일을 통해 Git 버전관리에서 제외할 파일 및 디렉토리를 지정할 수 있다. 
사전에 정의해둠으로써 중요 파일이나 실제 버전관리가 필요하지 않은 파일에 대해 버전관리를 제외할 수 있다.

LICENSE 파일을 활용해 본인이 진행하고 있는 프로젝트의 라이센스를 지정하고, 저작권 보호를 받을 수 있다.

package.json 파일은 릴리즈 노트를 자동화 생성하기 위해 필요하다.  
