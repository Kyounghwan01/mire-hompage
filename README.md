# mire-homepage

## inline-block을 넣어야 padding이 들어감

## 배너 영역의 좌우 패딩만 넣는 div class 필요

## float을 쓰면 상위 컨테이너 구조가 깨져서 height가 0이 됨 (즉, 안보임) - overflow: hidden을 쓰던지 clearfix를 만든다

## 미디어 쿼리

- 사이즈 줄어듬에 따라 padding 위아래값을 줄이는 방향으로 코딩

## before, after 를 이용한 가상 요소만들기

```html
<a class="ham"><span></span></a>
```

```css
/* 터치영역 */
.ham {
  display: block;
  width: 25px;
  height: 10px;
  background: rgba(0, 0, 0, 0);
  padding: 15px 10px 10px 10px;
}

/* 아이콘 영역 */
.ham span {
  position: relative;
  display: block;
  width: 25px;
  height: 4px;
  background: #39106a;
}
.ham span:before {
  content: "";
  width: 25px;
  height: 4px;
  background: #39106a;
  position: absolute;
  left: 0;
  bottom: -7px;
}
.ham span:after {
  content: "";
  width: 25px;
  height: 4px;
  background: #39106a;
  position: absolute;
  left: 0;
  top: -7px;
}
```
