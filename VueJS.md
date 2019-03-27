Vue.js 사용법
======================
# 1. 기본 셋팅
## 1.1. Visual Studio Code 설치
파일공유(Z:)\Utility\VSCode
## 1.2. node.js 설치
https://nodejs.org/en/
### 버전 확인
    1.cmd 실행
    2.node --version
    3.npm --version
    node - v10.15.x / npm - v6.4.x
## 1.3. vue 패키지 설치
    npm install -g @vue/cli
# 2. 페이지 만들기
## 2.1. vue 생성
    vue create jennyyoon
### 생성규칙
    1.Manual 체크
    2.Babel, Router, Vuex는 spacebar로 체크해제
    3.질문이 나오면 default로 no
## 2.2. vue 실행
    1.cd jennyyoon -- 제니윤 폴더로 이동
    2.dir -- 폴더 구성 확인
    3.code . -- visual studio code로 실행
    4.visual studio code에서 새 터미널을 연다(cmd와 동일하게 작동)
    5.npm run serve -- 실행하는 명령어 (실행된 로컬 주소가 뜨면 ctrl 클릭으로 웹 브라우저를 실행한다.)
## ※TIP
    기본 페이지에서 About과 홈으로 이동하면 주소에 #이 보인다
    #이 있는 이유는 페이지 이동을 안했다는 뜻으로
    다른 페이지가 아님을 의미한다.
# 3. datagrid 추가
## devextreme 패키지 설치
    npm install --save devextreme devextreme-vue
    ※npm install 하면 package.json 자동으로 입력됨
## datagrid 요소 추가
https://js.devexpress.com/Demos/WidgetsGallery/Demo/DataGrid/FormEditing/Vue/Light/

    1.페이지에서 App.vue를 Copy한 뒤 views폴더에 DataGrid.vue라는 새 파일을 만들어 Paste하고
    import 쪽에
    import 'devextreme/dist/css/dx.common.css';
    import 'devextreme/dist/css/dx.light.compact.css'; 추가한다.
    2.페이지에서 data.js를 Copy한 뒤 views폴더에 새파일을 동일한 이름으로 만들어 Paste한다.
    3.App.vue 에서는 링크를 구분하기 위한 막대표시와
     | <router-link to="/datagrid">DataGrid</router-link>
    링크를 추가한다.
    4.저장 하면 실행됬던 페이지에 datagrid라는 링크가 보인다.
    5.해당 링크를 클릭하면 datagrid가 표현된다
## ※TIP
    1.저장이 안되면 숫자가 보임
    2.Aplication 당 하나의 Vue파일을 가지게 되고
    Page 당 하나의 export를 가지게 된다.
    import 기능을 간략화 => export 바인딩 => 그리드에 표시됨
    이런 구조이다.
# 4. electron 추가
## electron 패키지 설치
    npm install electron --save-dev
## 빌드
    1.npm run build
    2.vue add electron-builder (dist_electron 생김)
    3.npm run electron:build
## 실행
    npm run electron:serve (앱으로 실행됨)
# 5. firebase 뷰 연동
https://appdividend.com/2018/04/21/vue-firebase-crud-example/

    예제와 같이 새 Vue를 생성하여 12 Step을 모두 마친 다음
    src폴더에 config 폴더를 생성하고 db.js를 만
    import Firebase from 'firebase'
    var config = {
    apiKey: "AIzaSyAHjYwnzB-Q1eornf7G6Si78PwjebbCCKo",
    authDomain: "vuemoim.firebaseapp.com",
    databaseURL: "https://vuemoim.firebaseio.com",
    projectId: "vuemoim",
    storageBucket: "vuemoim.appspot.com",
    messagingSenderId: "856865636452"
    };

    let app = Firebase.initializeApp(config)
    export const db = app.database()
    다음 내용을 입력한다.
