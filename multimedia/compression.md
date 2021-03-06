# 무손실 압축과 손실 압축

## 데이터 압축이란?

데이터를 **더 적은 저장 공간**에 효율적으로 저장하기 위한 기술이다.

- 인코딩 : 데이터를 더 작은 크기로 변환
- 디코딩 : 저장된 데이터를 다시 불러와 원래 데이터 형태로 복원

인코딩하기 전의 데이터 크기와 인코딩하고 나서으이 데이터 크기 비율을 **압축률**이라고 한다.

## 무손실 압축이란?

기존의 정보를 100% 보존하는 압축 방식이다.
대표적인 압축 방법으로 반복 길이 부호화가 있다.

예) zip, 7z, gif, png 등

### 반복 길이 부호화

데이터에서 같은 값이 연속해서 나타나는 것을 그 개수와 반복되는 값만으로 표현하는 방법이다.
이 방법은 아이콘 등의 간단한 이미지와 같이 연속된 값이 많이 있는 데이터에 효과적이다.
만화나 애니메이션과 같이 배경의 변화가 적은 영상에 적합하다.
또한 이 방식은 3번 이상 반복되는 문자들에 대해 이용되기 때문에 영어 문장에서는 잘 수행되기 어렵다.

### 허프만

데이터를 구성하는 단위 정보들의 빈도 수를 기반으로 각 단위 정보를 표현하는 비트 수를 효율적으로 할당하는 기법이다.
빈도 수가 높은 단위 정보에는 비트 수를 적게 사용하고, 낮은 빈도수의 단위 정ㅂ오에는 비트 수를 많이 할당

## 손실 압축이란?

사진, 음악, 동영상 등 주로 멀티미디어 데이터에서 인간이 지각하기 힘든 범위의 데이터를 버리고 압축하는 방법이다.
화질, 음질 등에서 좀 손해를 보더라도 용량만 줄이면 된다는 생각으로 만들어진 포맷이다.

예) wmv, jpeg, bpg 등

### 변환

변환 함수 등을 통해 데이터의 영역을 바꾸는 기법이다.

- FFT(Fast Fourier Transform) : 시간 영역 -> 주파수 영역
- DCT(Discrete Cosine Transform) : 공간 영역 -> 주파수 영역

### 예측

정보의 흐름에 있어서 다음에 나타날 정보는 바로 직전에 나타난 정보와 크게 다르지 않다는 가정을 두고 만든 기법이다.
이전 정보와 차이 정보를 가지고 다음 정보를 생성한다.

- DPCM(Differential PCM)
- ADPCM(Adaptive DPCM)
- DM(Delta Modulation)
- ADM(Adaptive DM)


### References

- [위키백과 - 데이터 압축](https://ko.wikipedia.org/wiki/데이터_압축)