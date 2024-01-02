## U-Net

[논문 링크](https://arxiv.org/abs/1505.04597)

U-Net은 이미지를 픽셀 단위로 끊어 분류하는 문제인 image segmentation에 특화된 모델이다. U-Net은 정보를 압축하는 encoder 부분과 압축된 정보를 복원하는 decoder로 이루어져 있는데, 이를 그림으로 나타내면 아래와 같이 U자 모양을 나타내기 때문에 U-Net이라고 불린다.

![Fig. 1. U-net architecture.](https://prod-files-secure.s3.us-west-2.amazonaws.com/c6e574d8-a5aa-45b1-bc17-9acd88dc7262/39a52feb-19ac-43c9-b95e-e22be904b36f/Untitled.png)

U-Net을 이용하면 사진이 입력되었을때 배경과 물체를 구분하는 경계를 찾아낼 수 있는데, 직접 코드를 작성하며 실습해보았다.

> 출처: 텐초의 파이토치 딥러닝 특강
