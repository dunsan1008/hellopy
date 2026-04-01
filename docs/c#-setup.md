# C# 개발 환경 설정 및 프로젝트 구성 가이드

이 문서는 C# 개발을 처음 시작하는 기여자를 위해  
.NET 설치 방법, 프로젝트 구성 방식, 기본 디렉토리 구조,  CLI 옵션 처리 라이브러리 등을 안내합니다.

---

# 1) .NET SDK 설치

# 🔹 Windows
- https://dotnet.microsoft.com/download 에서 최신 SDK 다운로드
- 설치 후 PowerShell에서 확인

# 2) .csproj 기본 구조

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net8.0</TargetFramework>
  </PropertyGroup>

</Project>

# 3) CLI 추천 라이브러리
 - System.CommandLine-> 간단한 CLI 옵션 처리에 적합
 - Spectre.Console.CLI0> 복잡한 CLI 옵션 처리에 적합, 컬러 출력, 레이블, 프롬포트 등 제공
