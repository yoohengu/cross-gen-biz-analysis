### 참고용) Seaborn의 꽃 palette 프리셋 (시각화 시 자주 씀!)
1. 범주형(Categorical) 팔레트 (각 항목이 독립적일 때)
* palette='pastel': 부드럽고 편안한 느낌. (유아복/여성복 분석에 추천)
* palette='Set2': 색상 간 구분이 명확하여 보고서용으로 가장 깔끔함.
* palette='hls': 밝고 화사한 느낌을 주고 싶을 때 사용.


2. 연속형(Sequential) 팔레트 (값의 크기나 순서가 중요할 때)
* palette='viridis': 통계 분석의 정석. 가독성이 매우 뛰어남.
* palette='rocket': 짙은 빨간색 계열로, '매출 폭발'이나 '주의가 필요한 구간' 강조에 적합.
* palette='mako': 심해의 느낌을 주는 청록색 계열로, 차분하고 전문적인 느낌.
* palette='Blues': 전통적인 파란색 그라데이션.

3. 발산형(Diverging) 팔레트 (중앙값을 기준으로 양극단을 강조할 때(예: 평균 대비 매출 증감))
* palette='vlag': 차가운 색과 뜨거운 색의 대비.
* palette='coolwarm': 마이너스와 플러스, 혹은 저가와 고가 대비에 최적.


```python
import seaborn as sns
import matplotlib.pyplot as plt

# 팔레트들을 한 번에 확인하기 위한 샘플 데이터
def show_palette(palette_name):
    sns.palplot(sns.color_palette(palette_name))
    plt.title(f"Palette: {palette_name}")
    plt.show()
print("범주형")
# 1. 범주형 
for p in ['Set2', 'pastel', 'husl']:
    show_palette(p)
print("연속형")
# 2. 연속형 
for p in ['viridis', 'rocket', 'mako']:
    show_palette(p)
print("발산형")
# 3. 발산형
show_palette('coolwarm')
```

    범주형
    


    
![png](palette_files/palette_1_1.png)
    



    
![png](palette_files/palette_1_2.png)
    



    
![png](palette_files/palette_1_3.png)
    


    연속형
    


    
![png](palette_files/palette_1_5.png)
    



    
![png](palette_files/palette_1_6.png)
    



    
![png](palette_files/palette_1_7.png)
    


    발산형
    


    
![png](palette_files/palette_1_9.png)
    



```python
# 기본 변환 명령어
# python -m jupyter nbconvert --to markdown "파일명.ipynb"

# 만약 파이썬 내에서 실행하고 싶다면 (주피터 노트북 셀 안에서)
# !python -m jupyter nbconvert --to markdown "파일명.ipynb"
```

# 1. 설치(터미널)
### pip로 설치
pip install nbconvert
### 또는 pip 안쓰는 우회 설치
python -m pip install nbconvert 
(참고용) python -m pip install pandocfilters
→ 저는 nbconvert만 설치해서 썼는데 이제 ai한테 물어보니까 편의성을 위해 pandocfilters도 설치하라고 하더라구요 요건 조금 더 찾아보고 알려드릴게요!

# 2. 마크다운 변환
### 기본 변환 명령어(터미널)
python -m jupyter nbconvert --to markdown "파일명.ipynb"
### 주피터 노트북 셀 안에서 직접 사용
!python -m jupyter nbconvert --to markdown "파일명.ipynb"
→ 이 경우 모두 run할 시 갑자기 파일이 저장되는... 불상사를 막기 위해 주석 처리해두시거나 터미널 이용하시는 것을 추천드립니다!

# 3. github에 커밋/푸쉬하기
* github를 기록용으로 쓰실 경우 마크다운이 유용하다고 합니다!
* 그냥 md 파일을 올리면 이미지는 같이 올라가지 않습니다!
* 하지만 md 파일 푸쉬할 때 이미지 파일도 같이 푸쉬하시면 github 폴더 내에 이미지 폴더가 생기고, 이미지도 함께 연동되니 시각화 자료가 있다면 꼭 같이 올리시는 것을 추천드려요!

* 혹시나 필요하실까봐 공유드리지만 어디까지나 선택 사항이고 이미 티스토리, 블로그 등에 잘 정리하고 계시다면 굳이일 수 있습니다!!! 본인에게 맞는 방법을 쓰고 계시다면 참고용으로만 봐주세요!
* 프로젝트가 끝난 뒤 git 연동을 개인 레포지토리와 연동할 경우(혹은 지금도 개인git - vscode - 팀git 이렇게 연동하고 계시는 경우)에 유용하게 쓰일 것 같습니다!! 데이터 분석가는 시각화가 중요한 무기니까 기록해두면 좋을 것 같아서... 괜찮으시다면 저희 같이 기록해봐요!!! 


```python
!python -m jupyter nbconvert --to markdown "palette.ipynb"
```
