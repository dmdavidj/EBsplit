# Yonsei Cancer Center - PDF EB Split  (포터블 EXE 만들기)

PDF를 원하는 배율로 확대해 A4/A3 여러 장으로 나누고, 이어붙임 점선 가이드와
좌측 최상단 라벨을 넣은 새 PDF를 만듭니다. **이 PDF를 100%(실제 크기)로 인쇄**하면
배율이 그대로 적용됩니다.

이 폴더는 병원 PC에서 **한 번만** 빌드하면 되는 "포터블 EXE 제작 꾸러미"입니다.
인터넷이 막혀 있어도 되도록 필요한 설치파일(`wheels` 폴더)을 함께 넣었습니다.

## 들어있는 것
- `pdf_split_scale.py` : 프로그램 본체
- `build_exe.bat`      : 더블클릭용 빌드 스크립트 (오프라인 우선)
- `wheels\`            : 오프라인 설치용 패키지(휠) — 지우지 마세요
- `README.md`          : 이 안내문

## 만드는 순서 (3단계)
1. **파이썬 설치** (최초 1회): 64비트 Windows에 파이썬 3.10~3.13.
   - <https://www.python.org/downloads/> 설치 시 **"Add python.exe to PATH" 체크**
   - 또는 Microsoft Store에서 "Python 3.12" 설치
2. 이 폴더 전체를 PC에 복사한 뒤, **`build_exe.bat` 더블클릭** (수 분 소요)
3. 끝나면 `dist\YonseiEBSplit.exe` 생성
   → **이 EXE 하나만** 복사하면 어느 PC에서든 파이썬 없이 실행됩니다.

## 사용법
- **더블클릭** → 파일 선택 GUI (PDF 선택 → 배율 입력 → 용지 선택 → 실행)
- **명령줄**
  ```
  YonseiEBSplit.exe 입력.pdf --scale 1.75 --paper A4
  옵션: --paper A3 / --orientation auto|portrait|landscape / --overlap 10 / --margin 5
  ```

## 인쇄 & 조립
1. 만들어진 PDF를 **"실제 크기 / 100%"** 로 인쇄 ("페이지에 맞춤" 금지).
2. 각 장 좌측 상단 라벨 `[P페이지 R행/전체 C열/전체]` 순서로 배치.
3. 이웃한 두 장을 **각각 빨간 점선을 따라 자른 뒤**, 잘린 면끼리 **맞대어(겹치지 말고)** 붙입니다.
   두 장의 점선은 겹침 구간의 정중앙 = 완전히 같은 위치라, 잘라 맞대면 소실/중복 없이 딱 맞습니다.
   (점선을 남기고 겹쳐 붙이면 겹침 폭만큼 그림이 사라지니, 반드시 "잘라서 맞대기"로 하세요.)

## 참고
- 32비트 Windows이거나 파이썬이 3.10~3.13이 아니면 `wheels` 오프라인 설치가 맞지 않을 수 있습니다.
  그때는 인터넷 연결 후 `build_exe.bat` 를 실행하면 자동으로 온라인 설치로 넘어갑니다.
- 콘솔창 없이 GUI만 뜨게 하려면 `build_exe.bat` 의 PyInstaller 줄 끝에 `--noconsole` 추가 후 재빌드.
