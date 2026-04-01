# Octokit.NET 사용 가이드

이 문서는 C# 프로젝트에서 GitHub API를 호출하기 위해  
Octokit.NET 라이브러리를 사용하는 방법을 정리한 가이드입니다.

# 1. Octokit.NET 설치 방법

Octokit.NET은 NuGet 패키지로 제공됩니다.

NuGet UI 설치
Visual Studio / Rider / VSCode C# Dev Kit에서
Octokit 패키지를 검색하여 설치할 수도 있습니다.

# 2 기본 클라이언트 생성
GitHub API를 호출하려면 **Personal Access Token(PAT)**이 필요합니다.
토큰은 GitHub → Settings → Developer settings → Personal access tokens에서 생성할 수 있습니다.

using Octokit;

var client = new GitHubClient(new ProductHeaderValue("RepoScore"))
{
    Credentials = new Credentials("YOUR_GITHUB_TOKEN")
};

#3 저장소 이슈 목록 조회
var issues = await client.Issue.GetAllForRepository("owner", "repo");

foreach (var issue in issues)
{
    Console.WriteLine($"#{issue.Number} - {issue.Title} (State: {issue.State})");
}

# 4. Pull Request 목록 조회 예시
var pullRequests = await client.PullRequest.GetAllForRepository("owner", "repo");

foreach (var pr in pullRequests)
{
    Console.WriteLine($"PR #{pr.Number} - {pr.Title} by {pr.User.Login}");
}
