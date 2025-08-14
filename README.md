
# 구글 폼 연동 테스트 사이트 (GitHub Pages 배포 가이드)

아래 순서대로 따라 하면, **GitHub 계정이 처음이어도** 10분 내에 사이트를 배포하고 테스트할 수 있습니다.

---

## 0) 준비물
- GitHub 계정 (https://github.com) — 가입/이메일 인증까지 완료
- 이 저장소에 넣을 파일: `index.html` (이 폴더 안에 있습니다)

> 이 예시는 **정적 사이트**이므로 빌드/서버가 필요 없습니다.

---

## 1) GitHub에서 새 저장소 만들기
1. GitHub 로그인 → 우측 상단 **+** 버튼 → **New repository**
2. Repository name: 예) `google-form-demo`
3. **Public** 선택 (Pages 무료 호스팅에 가장 간단)
4. 다른 옵션은 기본값으로 두고 **Create repository** 클릭

---

## 2) 파일 업로드 (웹에서 바로)
1. 새로 만든 저장소 화면에서 **Add file** → **Upload files**
2. `index.html` 과 `README.md` 파일을 업로드 창에 드래그 앤 드롭
3. 아래쪽 **Commit changes** 버튼 클릭

> 업로드 후 저장소 루트(`/`)에 `index.html` 이 보여야 합니다.

---

## 3) GitHub Pages 켜기
1. 저장소 상단 탭에서 **Settings** → 좌측 사이드바 **Pages**
2. **Build and deployment** 섹션:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`  /  **Folder**: `/ (root)` 선택
3. 아래의 **Save** 또는 선택 즉시 저장되는 UI면 그대로 두기
4. 잠시 후 **Your site is live**와 함께 **사이트 URL**이 표시됩니다.
   - 형식: `https://<계정명>.github.io/<저장소명>/`

> 만약 URL이 바로 표시되지 않으면 페이지를 한 번 새로고침 해보세요.

---

## 4) 사이트 접속 & 테스트
1. 위에서 표시된 **사이트 URL**로 접속
2. 페이지에서 값 입력 → **[제출]** 버튼 클릭
3. Google Form의 **응답 → 스프레드시트 열기**에서 새 행 생성 확인
4. 만약 네트워크 환경상 외부 POST가 제한되어 보이면, **[구글 폼에서 열기(자동 채움)]** 버튼을 눌러 새 탭(구글 도메인)에서 제출하면 100% 동작합니다.

---

## 5) 수정/업데이트 방법
- `index.html` 내용을 바꾼 뒤, 저장소에서 **Add file → Upload files** 또는 **Edit this file** 후 **Commit changes** 하면 자동으로 다시 배포됩니다.
- 페이지가 바뀌지 않으면 브라우저 캐시를 새로고침(Ctrl/Cmd + Shift + R) 해보세요.

---

## 6) 문제 해결(FAQ)
- **404 Not Found**: Settings → Pages에서 Source/Branch/Folder 설정이 올바른지 확인, `index.html`이 루트에 있는지 확인
- **제출해도 시트에 안 쌓임**: 
  - Google Form 설정에서 로그인 제한/도메인 제한/1회 응답 제한 OFF
  - 체크박스 라벨 값이 실제 옵션과 정확히 일치(현재 `"옵션 1"`)
  - 이 예제는 섹션 폼용 숨김 필드(`fvv`, `dlut`, `hud`, `partialResponse`, `pageHistory`, `fbzx`, `submissionTimestamp`)가 포함됨
  - 그래도 안되면 **[구글 폼에서 열기(자동 채움)]** 버튼으로 제출
- **사이트 URL이 안 나옴**: Settings → Pages 설정을 다시 저장, 혹은 저장소를 Public으로 전환해 테스트

---

## 7) 로컬에서 개발하고 푸시(선택 사항)
CLI를 쓰고 싶다면:
```bash
# 로컬에서
git init
git add index.html README.md
git commit -m "initial"
git branch -M main
git remote add origin https://github.com/<계정명>/<저장소명>.git
git push -u origin main
```
그 다음, Settings → Pages에서 위의 설정대로 활성화하세요.

---

### 참고: 이 예제 파일의 주요 설정
- Google Form ID: `1FAIpQLSfbaVaebSlCdOn7eNwGDfryph3brI1cmqPLrjkFc4pWoe4xEg`
- 항목 ID: `entry.2004604856`, `entry.1604015`, `entry.1133356289`, `entry.1849677858`
- 체크박스 라벨: `"옵션 1"`
- fbzx: `5815251098877105380`
- 섹션 폼 대응 hidden 필드 포함 (필요 시 추가 조정 가능)

행운을 빕니다! 🚀
