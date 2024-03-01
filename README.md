# 사다리타기 게임 v1

## 수정할 때 참고사항

### index.html

- getDiv에서 새로운 div요소를 만들어줌
- 크기를 반응형으로 바꾸기위해 nMaxWidth, nHeight를 this.window.innerWidth와 this.window.innerHeight를 가지고 넣어줌
- 사다리 자체의 위치를 바꾸기 위해서는 init()함수에서 변경해야함

  ` this.arrTopDiv[i].style.top = "40px";`

  `this.arrGoDiv[i].style.top = "70px";`

  `this.arrBotDiv[i].style.top = this.nHeight + 200 + "px";`

- allStart()함수는 버튼 하나만 눌려도 모두 출발시키기 위해 만든 함수
- nSpeed를 올리면 사다리가 내려가는 속도가 빨라짐
- getRndTop() 함수는 랜덤으로 가로 사다리를 만드는데, minDistance를 올릴 수록 사다리끼리 붙어있는게 줄어듬(대신 사다리 자체가 나올 확률이 낮아질 수 있음)
  - 될때까지 무한루프를 돌리면 스택오버플로우가 되버려서 제한해뒀음. 제한 값은 YL.MaxRetry의 수를 조절하면 됨
- btnAndResultDiv라는 id값을 가진 div요소안에 GO버튼들의 값과 아래 결과들의 값이 들어있음(가장 아래 div)
  - inp*top*으로 시작되는 input의 value를 바꾸면 GO버튼에 들어가는 글자를 변경할 수 있음
  - int*bot*으로 시작되는 input의 value를 바꾸면 아래 결과에 들어가는 글자를 변경할 수 있음

### styles.css

- 위에 GO 버튼은 .go_btn에 스타일이 들어있음
- 아래에 당첨결과는 .result 스타일에 들어있음
- 가장 위에 사다리게임 글자는 #title 스타일에 들어있
