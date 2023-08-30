# Capture
https://github.com/kimxminsu/kimxminsu.github.io/assets/35947676/66df8295-e1f3-464b-8d4d-7297883d1822

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
