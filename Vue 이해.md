# 배운점

## Nodejs 사용 이유

- npm을 통해 웹개발 라이브러리 설치를 쉽게 하도록 함

## App.vue는 메인 화면

- `.vue` 파일을 바로 브라우저로 읽지 못한다

  - **`index.html`로 `App.vue`파일을 HTML로 컴파일해서 넣는다**

  - 이 작업을 `main.js` 파일에서 하고있다

    ```js
    import { createApp } from 'vue'
    import App from './App.vue'
    
    createApp(App).mount('#app')
    ```



## 폴더 구성

- `node-modules` : 프로젝트에 쓰는 라이브러리들
- `src` : 소스ㅗ드 다 담는 곳
- `public` : html파일, 기타파일 보관
- `package.json` : 라이브러리 버전, 프로젝트 설정 기록



## 데이터 바인딩

### Vue에서 변수 관리

```vue
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4>XX 원룸</h4>
    <p>{{price1}} 만원</p>		// {{ }} 안에 데이터 바인딩 한다
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>{{price2}} 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      price1 : 60,
      price2 : 70,
    }
  },
  components: {
  }
}
</script>
```

- `{{ }}`안에 변수값을 넣을 수 있다 (데이터 바인딩)

  ### 쓰는 이유

  1. html을 하드코딩하는 것을 막기 위해 사용

  2. 실시간 자동 렌더링을 위해 사용한다
     - 데이터 변경이 되면 자동으로 렌더링 된다 (웹 앱을 만들 수 있다)

- 변경될 일이 없는 데이터는 하드코딩해도 된다 (ex. 페이지 이름)

- html 속성도 데이터바인딩 가능

  - `:속성="데이터이름"` 형식으로 사용

  ```vue
  <h4 :style="h4style">XX 원룸</h4>
  
  <script>
  export defualt{
      name: 'App',
      data(){
          return{
              h4style : "color : blue"
          }
      }
  }
  </script>
  ```

  

## HTML 반복문

- vue를 통해 반복적인 html을 사용 가능

- `v-for` 사용

  ```vue
  <a v-for="num in 3" :key="num">Home</a>
  // "변수 in 횟수" 형식을 가진다
  
  <a v-for="menu in menues" :key="menu">{{menu}}</a>
  data(){
      return {
        menues : ['Home', 'Shop', 'About'],
      }
    },
  ```

  - 반복을 위해서는 유니크한 `key`값을 넣어야 된다

    - 용도 : 태그를 구분하기 위한 속성

    ```vue
    <a v-for="(menu, i) in menues" :key="i">{{menu}}</a>
    (변수명, 인덱스) //0부터 시작하는 인덱스 i
    ```

    