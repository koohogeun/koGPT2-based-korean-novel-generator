# koGPT2-based-korean-novel-generator

한국 소설로 KoGPT-2(https://github.com/SKT-AI/KoGPT2)를 학습시킨 후, 학습 데이터의 저자와 생성할 문장의 처음 부분을 입력으로 주었을 때 정해진 글자 수 만큼 글자를 생성.
한다.

flask를 활용하여 웹에서 실시간으로 동작한다.

% weight 파일 없음

------------
# 학습 조건
순정 KoGPT-2를 사용하였으며, DDP를 사용해 4장의 GPU사용
입력 문장들 앞에 저자를 추가하여 조건부 확률로 학습
