# Study Notes - MkDocs 예제

현재 Git 저장소(`study`)의 최상위 폴더에 예제 파일을 복사하세요.
기존 파일을 덮어쓸 경우 먼저 내용을 확인하세요.

Windows Git Bash 기준:

```bash
# study 폴더에서 가상환경을 처음 만드는 경우에만 실행
python -m venv venv
source venv/Scripts/activate

python -m pip install -r requirements.txt
python -m mkdocs serve
```

브라우저에서 http://127.0.0.1:8000/ 접속.
`venv/`는 `.gitignore`로 제외되며, Git에 올리지 않습니다.

파일 구성을 바꾸려면 `mkdocs.yml`의 `nav`와 `docs/`의 실제 경로를 함께 수정하세요.
