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

## 한줄로 쓰다가 밑으로 내릴때

```html
<h2>캡틴 마블 <em>Captin Marvel</em></h2>
```

```css
.h2 em {
  display: block;
}
```

## after, before

- 가상요소를 추가 (앞 또는 뒤에 css로 뭔가 추가할떄)

## img 표현방법

1. img - 이미지 불러올때

```html
<img src="" alt="" />
```

2. figure - 이미지 표현할때
3. figcation - 이미지 설명할때

```html
<figure>
  <img src="" alt="" />
  <figcation>이미지 설명</figcation>
</figure>
```

4. picture - 이미지를 화면크기에 따라 사용 (반응형)

```html
<picture>
  <source media="(max-width:1000px)" srcset="img1" />
  <source media="(min-width:800px)" srcset="img2" />
  <img src="img3" alt="" />
</picture>
```

## border에 의해 라인이 겹치면

`margin-left: -1 or margin-right: -1`

## 이미지 일부가져오기

`background-position: -87px -125px;`

## padding을 width 값 안에 포함되게

width, height = margin + padding + border
width: 50px + 20px + 10px + 1 => width: 112px

`box-sizing: border-box`라 설정시
width: 50px margin: 20px padding: 10px border: 1px
-> width: 90px(50+20+20)됨 --> padding, border가 width에 포함되지 않음

## window width값 줄어들때 요소의 width값도 줄어들도록

`width: auto`

## 포지션 absolute 값을 초기화 할때

`position: static;`

## tab css

```css
.movie_title ul {
  position: relative;
  padding-bottom: 10px;
}
.movie_title ul:before {
  content: "";
  position: absolute;
  z-index: 1;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 2px;
  background: #e1e1e1;
}
.movie_title li {
  width: auto;
  border: 0;
}
.movie_title li a {
  position: relative;
  font-size: 18px;
  color: #666;
  font-weight: 400;
  padding: 0;
  margin-right: 35px;
}
.movie_title li.active a:before {
  content: "";
  position: absolute;
  z-index: 2;
  left: 0;
  bottom: -10px;
  width: 100%;
  height: 2px;
  background: #666;
}
.movie_title li.active a {
  background: none;
  color: #666;
}
```

## zindex를 사용하는데 반영안되는경우

- position: relative를 활용

## img 넣었는데 여백이 생기는 경우

img는 인라인 구조이기 때문에 폰트사이즈가 영향을 받는다
img의 display를 block로 바꾸거나 폰트사이즈를 0으로 바꾼다.
