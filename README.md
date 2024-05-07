
# Integrating $cos\theta$ (instead of $sin \theta$) using 0th order<br>0차 적분을 이용한 ($sin \theta$ 대신) $cos \theta$ 적분

## Description<br>설명

* Using numerical integration of 0th order, please calculate definite integral of $cos \theta$ (instead of $sin \theta$ in the video).<br>0차 수치 적분을 사용하여 (비디오에서는 $sin \theta$ 였지만) $cos \theta$의 정적분을 계산하시오.

## Implementation<br>구현

* Implement following functions in `main.py` file.<br>다음 함수를 `main.py` 파일에 구현하시오.

| function<br>함수 | description<br>설명 |
|:----------------:|:------------------:|
| `int_cos_0()` | calculate definite integral of $cos \theta$ using numerical integration of 0th order<br>0차 수치 적분을 사용하여 $cos \theta$의 정적분을 계산 |
| `compare_int_cos()` | compare the numerical integration and the exact integration of $cos \theta`<br>$cos \theta$의 수치 적분과 정적분을 비교 |

* Please see `sample.py` file for an example.<br>사용 예에 대해서는 `sample.py` 파일을 참고하시오.
* In `main.py` file, every python code line must belong to one of functions.<br>`main.py` 파일에서 모든 파이썬 코드 라인은 반드시 함수 중 하나에 속해야 함.

### 0th order integration<br>0차 적분
* Function `int_cos_0()` has three argument : `theta_rad_begin`, `theta_rad_end`, and `n`.<br>함수 `int_cos_0()` 의 매개변수는 `theta_begin`, `theta_end`, 그리고 `n` 이다.

| argument<br>매개변수 | type<br>형 | unit<br>단위 | description<br>설명 |
|:-----------------:|:----------:|:----------:|:------------------:|
| `theta_rad_begin` | `float` | rad | lower bound of the integral<br>적분구간의 하한 |
| `theta_rad_end` | `float` | rad | upper bound of the integral<br>적분구간의 상한 |
| `n` | `int` | - | number of equally spaced rectangles between the bounds<br>적분 구간을 등간격으로 나눈 직사각형 갯수 |

* Please return a `dict` containing `numpy` array of the area of each rectangle of 0th order integration and the sum of all rectangles as the numerical integration in `float`.<br>`dict`를 반환하시오. value 로 0차 적분의 각 직사각형의 넓이를 담은 배열과 해당 직사각형의 넓이의 합을 `float`로 담으시오.

| key (str)<br>키 (문자열) | type of value<br>value 의 형 | unit<br>단위 | description<br>설명 |
|:-----------------:|:----------:|:----------:|:------------------:|
| `'a_array_0'` | `numpy` array | - | the `n` areas of rectangles of 0th order integration<br>0차 적분의 `n`개의 직사각형의 넓이 |
| `'area_0'` | `float` | - | the numerical integration<br>해당 수치 적분 값 |

### Compare<br>비교
* Function `compare_int_cos()` has three argument : `theta_rad_begin`, `theta_rad_end`, `n`, and `epsilon`.<br>함수 `compare_int_cos()` 의 매개변수는 `theta_rad_begin`, `theta_rad_end`, `n`, 그리고 `epsilon` 이다.

| argument<br>매개변수 | type<br>형 | unit<br>단위 | description<br>설명 |
|:-----------------:|:----------:|:----------:|:------------------:|
| `theta_rad_begin` | `float` | rad | lower bound of the integral<br>적분구간의 하한 |
| `theta_rad_end` | `float` | rad | upper bound of the integral<br>적분구간의 상한 |
| `n` | `int` | - | number of equally spaced rectangles between the bounds<br>적분 구간을 등간격으로 나눈 직사각형 갯수 |
| `epsilon` | `float` | - | tolerance for comparing the numerical integration and the exact integration<br>수치 적분과 정적분을 비교하기 위한 허용오차 |

* Please return a `dict` containing the numerical integration, the exact integration, the absolute value difference between the two integrations in `float`, and whether the absolute value is smaller than `epsilon`.<br>`dict`를 반환하시오. value 로 수치 적분, 정적분, 두 적분의 차이의 절대값, 그리고 절대값이 `epsilon` 보다 작은지 여부를 담으시오.

| key (str)<br>키 (문자열) | type of value<br>value 의 형 | unit<br>단위 | description<br>설명 |
|:-----------------:|:----------:|:----------:|:------------------:|
| `'area_0'` | `float` | - | the numerical integration<br>해당 수치 적분 값 |
| `'area_exact'` | `float` | - | the exact integration<br>해당 정적분 값 |
| `'diff_0'` | `float` | - | the absolute value of the difference between the two integrations<br>두 적분의 차이의 절대값 |
| `'is_close_0'` | `bool` | - | whether the absolute value is smaller than `epsilon`<br>절대값이 `epsilon` 보다 작은지 여부


## Example<br>예

```python
theta_rad_begin = 0.0
theta_rad_end = np.pi / 2
n = 100

print(int_cos_0(theta_rad_begin, theta_rad_end, n))

epsilon = 1e-6
print(compare_int_cos(theta_rad_begin, theta_rad_end, n, epsilon))
```
