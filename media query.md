# Media query level 5

알아야 할 새로운 미디어 쿼리



### light-level

애플에 의해 다크모드 같은 기능들이 추가되고 사용자의 시간 때나 밝고 어두움에 따른 많은 미디어쿼리들이 생겨나고 있습니다.

그중에서 'light-level'은 밝기에 대한 것입니다.

쉽게 말해 화면 밝기에 따라 반응하는 미디어 쿼리입니다.

dim, washed, normal 3가지 속성이 있습니다.

```
@media (light-level: dim){
  color:#fff;
  background:#000
}
```

* dim : 디바이스를 어두운 환경에 대한 스타일 설정 값

* washed : 광량이 밝은 곳에서의 디바이스 밝기에 따라 변경될 스타일 설정 값

* normal : 화면에 이상적인 범위의 조명 수준의 환경에서 사용 / 특별한 조정 X



### inverted-colors

다크 모드가 나오기 전에 많은 사람들이 다크모드 느낌을 얻기 위해 색상 반전을 켰습니다. 꽤 깔끔해 보였지만 이미지, 텍스트 그림자 및 글꼴이 렌더링되는 방식도 망가졌습니다.

none, inverted 2가지 속성이 있습니다.

```
@media (inverted-colors: inverted){
   img{
      filter: invert(1);
   }
}
```



### prefers-*

#### prefers-color-scheme

최근 OS, 소프트웨어, 웹 서비스 IT 업계에서 산업군을 넘어 Dark Mode (어두운 테마)가 유행하고 있습니다. macOS, Microsoft Windows 등 웹 서비스 또한 다크모드를 지원하는 추세입니다. ex) Youtube

이렇듯 선택적으로 Dark Mode, Light Mode를 선택할 수 있는 서비스들이 많아지고 있습니다. 사용자가 취향에 맞는 설정을 할 수 있다는 점에서 개인화의 일종이라고 볼 수 있습니다.

dark, light, no-preference 3가지 속성이 있습니다.

ie, firefox에서 일부 지원하지 않습니다.

```
@media (perfers-color-scheme: dark){
  body{
    background:#222;
    color:#fff;
  }
}
```

* dark : 사용자가 다크 모드 선호
* light : 사용자가 라이트 모드 선호

* no-preference : 사용자가 선호하는 테마를 알리지 않았음 / false



#### prefers-reduced-motion

디바이스 및 OS 설정에서 애니메이션을 감소시키는 설정이 켜져있는 경우가 있습니다. 이 경우 웹 브라우저에서도 영향을 주어 CSS 애니메이션이 일부 작동하지 않게 됩니다.

시각적인 부분이 좋지 않은 몇몇 분들에게는 이런 움직임이 신체적으로 아프게 할 수도 있습니다. 그렇기 때문에 현재 대부분의 최신 UI에서 찾을 수 있는 전환을 조정하는 방법을 지원합니다.

reduce, no-reduce 2가지 속성이 있습니다.

```
@media (prefers-reduced-motion: reduce){
   .animated{
      transition-duration: 0.05s;
   }
}
```



#### prefers-reduced-transparency

일부 운영체제는 시스템에서 사용되는 반투명 레이어링 효과의 양을 줄이는 옵션을 제공합니다.

특히 opacity 를 0 에서 1 로 바꿔서 컨텐츠를 표시하는 애니메이션을 구성한 경우, 컨텐츠 자체가 표현되지 않는 문제가 발생 할 수도 있습니다.

reduce, no-reduce 2가지 속성이 있습니다.

```
@media (prefers-reduced-motion: reduce){
   .animated{
      opacity: 1 !important;
   }
}
```



#### prefers-reduced-data

셀룰러 데이터가 부족하거나 해외 여행을 하는 경우 이미지가 많은 사이트에 부딪히게 됩니다.

고해상도 이미지를 건너 뛸 수 있습니다.

reduced, no-preference 2가지 속성이 있습니다.

```
@media (prefers-reduce-data: reduced){
   .img{
      background-image:none;
      background-color:yellow;
   }
}
```





[Can I Use - 지원여부](https://caniuse.com/?search=prefers)

[Chrome - 다크모드](https://developer.chrome.com/devsummit/)

[sally - 다크모드](https://code.d2.co.kr/sallykwak/study/04_media/01.html)

[sally - 모션감소](https://code.d2.co.kr/sallykwak/study/04_media/02.html)

