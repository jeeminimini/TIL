### GPU 설치 성공

파이참에 gpu 까는 것 성공함.
터미널에서 인터넷에 나와있는 코드 3개를 치면 안되고, NVIDA를 깔아서 cuda 설치해줘야함.
https://mallangworld.tistory.com/entry/torchcudaisavailable-False%EC%97%90%EC%84%9C-True%EB%A1%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0
이 사이트에서 알려주는데로 그대로 따라했지만 안됨.
그래서 더 서칭해본 결과 https://www.notion.so/1-18-torch-cuda-is_available-5a246148a872466999227cdc2467276f
이 사이트를 참고했을 때 터미널에 nvidia-smi 이걸쳐서 내 컴퓨터의 cuda 지원 버전을 알아냄.
내가 설치한것은 10.1인데 내 컴퓨터는 10.2를 지원해서
pytorch를 다 지우고 10.2로 다시 깐 결과 true로 나왔다!

### tensor cpu로 바꿔줄 때 오류

그런데 gpu를 돌렸을 때 마지막에 cpu로 바꿔주었음에도 can't convert cuda:0 device type tensor to numpy. Use Tensor.cpu() to copy the tensor to host memory first.
라는 오류가 떴다. 
이는 내가 for문 돌릴때도 model에 cuda를 붙여줘서 인듯함.
없애니까 작동했음.
