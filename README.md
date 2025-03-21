# Word Test Generator

## 📌 프로젝트 소개
이 프로젝트는 영어 단어와 한글 뜻이 포함된 엑셀 파일을 기반으로 랜덤 단어 테스트를 생성하는 Python 스크립트입니다. 최근 회차의 단어와 이전 회차에서 랜덤으로 선택된 단어를 포함하여 총 100개의 단어를 선택하고, 이를 랜덤하게 배열하여 테스트 및 정답 시트를 이미지 파일로 저장합니다.
![image](https://github.com/user-attachments/assets/406b6637-5418-42e0-8e4a-b6778af060f9)


## 📂 파일 구조
```
├── wordsheet.xlsx  # 영어 단어 및 한글 뜻 데이터 파일
├── word_test_generator.py  # 메인 스크립트 파일
├── output/  # 생성된 단어 테스트 및 정답 이미지가 저장되는 폴더
```

## 🔧 기능
- 엑셀 파일(`wordsheet.xlsx`)에서 단어 목록을 읽어옴
- 최신 회차 단어 + 이전 회차 단어를 랜덤으로 선택 (총 100개)
- 단어 순서를 무작위로 섞어 출력
- 한글 뜻을 빈칸으로 둔 단어 테스트 시트 생성
- 정답이 포함된 답안 시트 생성
- 두 개의 시트를 이미지(`.png`) 파일로 저장

## 🛠️ 사용법
### 1. 필수 라이브러리 설치
```sh
pip install pandas openpyxl matplotlib
```

### 2. `wordsheet.xlsx` 파일 준비
엑셀 파일에는 다음과 같은 형식으로 데이터가 포함되어야 합니다.
```
chapter | english               | korean
--------|-----------------------|--------------------------------
1       | make the most of      | ~의 이점 등을 최대한도로 활용하다
1       | out of reach          | 손에 닿지 않는
2       | initiate              | 동) ~을 착수하다
3       | solid                 | 형) 탄탄한, 충분한
```

### 3. 스크립트 실행
```sh
python word_test_generator.py
```

### 4. 결과 확인
스크립트 실행 후 같은 디렉터리에 `회차_날짜.png` 형식의 이미지 파일이 생성됩니다.
- `{회차}회차 {날짜}.png` → 단어 테스트 시트 (한글 뜻 빈칸)
- `{회차}회차 answer {날짜}.png` → 정답 시트 (한글 뜻 포함)

## ⚠️ 주의사항
- `wordsheet.xlsx` 파일이 동일한 디렉터리에 있어야 합니다.
- `matplotlib`에서 한글 폰트를 사용하기 위해 Windows의 경우 `C:\Windows\Fonts\batang.ttc` 경로의 폰트를 불러오도록 설정되어 있습니다. 다른 OS를 사용하는 경우 폰트 경로를 적절히 변경해야 합니다.

## 📜 라이선스
MIT License

