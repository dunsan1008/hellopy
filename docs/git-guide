PR과 이슈 자동 연동
GitHub에서는 Pull Request(PR) 본문에 특정 키워드를 사용하면
해당 PR이 기본 브랜치(main 등)에 머지될 때 연관된 이슈가 자동으로 닫히게 됩니다.

1. 사용 가능한 키워드
- Closes #123
- Fixes #42
- Resolves #7
이 키워드를 PR 본문에 포함하면, 해당 번호의 이슈가 자동으로 닫힙니다.

2. 자동 close 동작
- PR이 **기본 브랜치(main 등)**에 머지되면 연동된 이슈가 자동으로 closed 처리됩니다.
- Draft PR이나 기본 브랜치가 아닌 브랜치로 머지되는 경우에는 자동 close가 동작하지 않습니다.
- 다른 저장소의 이슈를 연동할 수도 있습니다.
예: Closes owner/repo#99

3. 예외 케이스
- Draft PR → 머지 전까지 자동 close 동작하지 않음
- 기본 브랜치가 아닌 브랜치 → 머지 시 자동 close 동작하지 않음
- Cross-repo 이슈 연동 → Closes otheruser/otherrepo#123 형식으로 가능

4. 권장 사항
- PR 템플릿에 Closes # 항목을 포함시켜 기여자가 습관적으로 이슈를 연동하도록 합니다.
예시 PR 템플릿: # 관련 이슈 Closes #
