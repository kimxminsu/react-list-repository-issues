# Capture
![스크린샷 2023-08-30 오후 7 41 58](https://github.com/kimxminsu/kimxminsu.github.io/assets/35947676/66df8295-e1f3-464b-8d4d-7297883d1822)

# Loading

`components/issues`
loading 초기값 true일 동안 로딩화면이다가, 응답을 받으면 dataLoadSuccess화면을 보여줌

```
  getGithubIssues = repoName => {
    this.setState({ loading: true })
    return this.fetchIssues(repoName)
      .then(response => {
        if (response) {
          this.setState({
            issues: response.data,
            dataLoadSuccess: response.status && response.status === 200,
            loading: false,
            headerRepoName: repoName
          })
        }
      })
  }
```

```
{loading
            ?
            <div className='loading-screen'>
              <h1>로딩중</h1>
            </div>
            :
            !dataLoadSuccess
```

# 기능 구현 여부
1. 이슈 목록 화면  
- [x] 이슈 목록 가져오기 API 활용  
- [ ] open 상태의 이슈 중 코멘트가 많은 순으로 정렬  
- [x] 각 행에는 ‘이슈번호, 이슈제목, 작성자, 작성일, 코멘트수’를 표시  
- [ ] 다섯번째 셀마다 광고 이미지 출력  
- [ ] 화면을 아래로 스크롤 할 시 이슈 목록 추가 로딩(인피니티 스크롤)

2. 이슈 상세 화면  
- [ ] 이슈의 상세 내용 표시  
- [ ] ‘이슈번호, 이슈제목, 작성자, 작성일, 코멘트 수, 작성자 프로필 이미지, 본문' 표시

3. 공통 헤더  
- [ ] 두 페이지는 공통 헤더를 공유합니다.  
- [x] 헤더에는 Organization Name / Repository Name이 표시됩니다.  
