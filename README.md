## U-Net

논문 링크: [U-Net](https://arxiv.org/pdf/1505.04597.pdf)

U-Net은 이미지를 픽셀 단위로 끊어 분류하는 문제인 image segmentation에 특화된 모델이다. U-Net은 정보를 압축하는 encoder 부분과 압축된 정보를 복원하는 decoder로 이루어져 있는데, 이를 그림으로 나타내면 아래와 같이 U자 모양을 나타내기 때문에 U-Net이라고 불린다.

<img src="https://github.com/mathdoyun/U-Net/assets/135238974/77b2a875-5b00-4a45-9a0a-992c52ac75c3" width="75%" height="75%"/>

U-Net을 이용하면 사진이 입력되었을때 배경과 물체를 구분하는 경계를 찾아낼 수 있는데, 직접 코드를 작성하며 실습해보았다.

> 출처: 텐초의 파이토치 딥러닝 특강

---

P.S. 교재 링크에 있는 데이터셋과 코드를 그대로 따라하면 오류가 발생하는데, 몇몇 파일들이 32bit(4채널), 8bit(1채널) jpg라 차원이 맞지 않기 때문에 문제가 생기는 것이다. 다음의 파일들을 제거하면 코드가 잘 실행된다.

- Abyssinian_5, 34
- Egyptian_Mau_14, 129, 139, 145, 167, 177, 186, 191
- staffordshire_bull_terrier_2, 22

또한 모델 평가 맨 마지막 부분에서 코드를 다음과 같이 바꿔줘야 한다.

```python
pred = model(torch.unsqueeze(data.to(device), dim=0)).cpu()>0.5
```
