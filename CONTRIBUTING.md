# <a name="contributing-to-the-project-rome-documentation"></a>프로젝트 로마 설명서에 기여

설명서에 관심을 가져 주셔서 감사 합니다. 편집, 추가 및 도움말 문서를 개선 하는 사용자 의견에 감사 드립니다. 이 페이지는 기본 단계 및 참여에 대 한 지침을 다룹니다.

## <a name="sign-a-cla"></a>CLA 서명

두 개 이상의 줄 참여 하려는 경우 Microsoft 직원이 아닌 경우 해야 [는 Microsoft 라이선스 계약 (CLA)을 로그인](https://cla.microsoft.com/)합니다. 

## <a name="propose-a-minor-change"></a>사소한 변경 내용 제안

문서에 간단한 변경 내용을 제안, 하려면 다음이 단계를 수행 합니다.

1. Docs.microsoft.com 페이지를 보는 경우 클릭 합니다 **편집** 페이지의 오른쪽 위에 있는 단추입니다.  해당 Markdown 소스 파일로 리디렉션됩니다 합니다 [GitHub 리포지토리](https://github.com/MicrosoftDocs/project-rome)합니다. GitHub 리포지토리에서 이미 있다면 이동할 수 있습니다만 변경 하고자 하는 소스 파일입니다.
2. 아직 GitHub 계정이 없는, 클릭 **등록** 위에 있는 오른쪽 새 계정을 만듭니다.
3. 변경 하려는 GitHub 페이지에서 연필 아이콘을 클릭 합니다. 
4. 파일을 수정 하 고 제대로 변경 내용을 확인 하려면 미리 보기 탭을 사용 합니다.
5. 완료 되 면 변경 내용을 커밋하고 끌어오기 요청을 여세요.

끌어오기 요청을 만든 후 Windows 10 docs 팀의 멤버 검토 됩니다. 요청을 수락 하는 경우 업데이트를 게시할 [ https://docs.microsoft.com/windows/project-rome/ ](https://docs.microsoft.com/windows/project-rome/)합니다.

## <a name="make-more-substantial-changes"></a>더 크게 변경

### <a name="fork-the-github-repo"></a>GitHub 리포지토리 포크

기존 문서를 대폭 변경, 추가 또는 이미지를 변경 하거나 새 문서를 참여를 권장 GitHub 계정에 리포지토리를 분기 (의 오른쪽 위 모서리에서 "분기" 단추를 클릭 합니다 [GitHub 리포지토리에서](https://github.com/MicrosoftDocs/project-rome), 차례로 로컬 클론을 만드는 (녹색 클릭 **복제 또는 다운로드** 단추를 다음 명령줄을 클립보드에 복사 입력 `git clone <paste your repo clone link>`).

자세한 내용은 참조 하세요. [리포지토리를 포크](https://help.github.com/articles/fork-a-repo/)합니다.

Git를 사용 하 여 잘 모르는 경우 참조를 [Lynda.com Git Essentials 교육](https://www.lynda.com/Git-tutorials/Git-Essential-Training/100222-2.html)합니다.

### <a name="author-your-contribution"></a>작성 글

분기를 로컬 컴퓨터에 리포지토리 복제를 후 원하는 텍스트 편집기를 사용 하 여 작성을 시작할 수 있습니다. 것이 좋습니다 [Visual Studio Code](https://code.visualstudio.com/), Microsoft에서 무료 경량 오픈 소스 편집기입니다.

### <a name="submit-your-contribution-by-issuing-a-pull-request-pr"></a>(PR) 끌어오기 요청을 실행 하 여 참여를 제출 합니다.

로컬 git 리포지토리에 변경 내용을 저장 하면, 커밋 및 로컬 분기 된 리포지토리에 푸시 하려면 명령줄에서 다음 명령을 입력 합니다.
- `git status`: 이 명령은 해당 변경 내용을 확인 하려는 확인할 수 있도록 변경한 경우 파일에 표시 됩니다. 
- `git add -A`: 이 명령은 변경 인덱스에 모든 변경 내용을 추가합니다. 원하는 경우 특정 파일에 대 한 변경 내용을 추가 하는 경우 명령을 입력 합니다. `git add <yourfile.md>`합니다.
- `git commit -m "your commit message"`: 이 명령은 만든 변경 내용을 설명 하는 간단한 메시지와 함께 이전 단계에서 추가한 변경 내용을 커밋하기 위해 git을 알려 줍니다.
- `git push origin <yourbranchname>`: 이 명령은 지정 된 분기에서 ("원점"), github 분기는 원격 리포지토리 변경 내용을 푸시합니다.

원격 리포지토리에 작성 글을 푸시를 받게 됩니다에서 전자 메일 *개방형 게시 빌드 서비스* 글 성공적으로 빌드 하는지 여부를 알리는 및 오류나 리포지토리에서 경고에 대 한 링크를 제공 합니다. 끊어진된 링크 예: 합니다. 사이트에 준비 된 콘텐츠를 보려면 보고서의 링크를 클릭 합니다. 오류 및 경고의 변경 내용을 취소 하는 경우 있습니다 제출할 준비가 확인 하세요입니다.
- 프로젝트 로마 리포지토리의 포크로 이동 합니다. https://github.com/  **\<github 사용자 별칭\>**/project-rome 합니다.
- 클릭 합니다 **새 끌어오기 요청** 단추입니다. "기본 분기:" "MicrosoftDocs/project-로마"로 나열 됩니다 및 "분기 헤드:" 리포지토리 및 분기 변경 내용을 변경한의 포크를 표시 해야 합니다. 변경 내용을 여기도 검토할 수 있습니다. 
- 클릭 합니다 **끌어오기 요청 만들기** 단추입니다. 그런 다음 제목과 설명을 PR을 제공 해야 합니다. 마지막으로 클릭 합니다 **끌어오기 요청 만들기** 단추 한 번 더 합니다.

PR 제출 되 면 Windows 10 docs 팀의 멤버 검토 됩니다. 변경 내용을 볼 수 해야 수락 되 면 합니다 [준비 사이트](https://review.docs.microsoft.com/windows/project-rome/)합니다. 이러한 업데이트 결국 게시할 라이브로 [ https://docs.microsoft.com/windows/project-rome/ ](https://docs.microsoft.com/windows/project-rome/)합니다.

## <a name="using-issues-to-provide-feedback-on-project-rome-documentation"></a>문제를 사용 하 여 프로젝트 로마 설명서에 대 한 의견을

피드백을 보내도록 직접 설명서 페이지를 수정 하는 대신 [문제 만들기](https://github.com/MicrosoftDocs/project-rome/issues)합니다.

항목 제목 및 해당 페이지의 URL을 포함 해야 합니다.

## <a name="additional-resources"></a>추가 자료
- [GitHub의 서식 지정 및 작성 시작](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/)

## <a name="additional-resources-for-microsoft-employees"></a>Microsoft 직원에 대 한 추가 리소스
- [GitHub 계정 및 MS 별칭 연결](https://review.docs.microsoft.com/windows-authoring-guide/github-account#2-connect-your-github-account-and-ms-alias-on-the-microsoft-open-source-portal)
- [Markdown을 작성 하기 위한 리소스](https://review.docs.microsoft.com/windows-authoring-guide/writing-guidance/writing-markdown)