# koGPT2-based-korean-novel-generator  

웹에서 한국 소설로 KoGPT-2(https://github.com/SKT-AI/KoGPT2)를 학습시킨 후, 학습 데이터의 저자와 생성할 문장의 처음 부분을 입력으로 주었을 때 정해진 글자 수 만큼 글자를 생성한다.  

## 개요  
순정 KoGPT-2모델과 토크나이저를 사용하였습니다.  
학습 과정에서 문장 앞에 저자의 정보를 같이 입력하여 조건부 확률이 가능하도록 하였습니다.  
flask를 활용하여 웹에서 실시간으로 동작합니다.  
  
## 사용방법  
순정 KoGPT-2에서 학습된 모델 가중치 파일이 필요합니다.  
모델의 config는 kogpt2_file에 있습니다.  
% authors_v2.pkl파일은 실험에 사용했던 저자들의 목록입니다.  
  
web.py가 메인 파일이며 flask 템플릿은 templates에서 작업하면 됩니다.  
app.secret_key는 비밀번호 설정하는 키  
device는 GPU가속 시 여러개의 GPU가 있는 환경이면 설정이 필요합니다.  
authors는 저자의 조건부 확률로 학습에 사용한 저자와 저자에 해당하는 숫자가 매칭되는 dict형태의 pkl파일입니다.  
  
login_form, login, kogpt, kogpt_generate는 flask에서 동작하며 템플릿을 이용하여 동작합니다.  
build_model함수에서 모델 config의 경로 및 가중치 경로를 설정해주면 됩니다.  
  
웹페이지는 localhost의 8889포트가 기본으로 동작합니다.  
