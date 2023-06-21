# React Native ToDoApp (ver. expo)

<br />

### 레이아웃

> - view 는 무조건 flex 를 가지고 방향은 column
> - 부모에 flex:1 을 부여하고 자식들에게 각 1 을 부여하면 각 비율에 따라 화면에 자리잡음. 그러나 부모에 사이즈를 부여해주지 않으면 반영 안됨. 만약 부모의 형제가 없다면 값을 어느 것을 준다고 해도 동일함. 계산할 비율이 없기 때문에

<br />

### 스타일

> - 좌우 스크롤 컴포넌트는 명시된 props 들을 더 써봐야 할 듯
> - 각 디바이스의 크기를 알고 싶다면 Dimensions.get("window") api 사용해서 객체로 width, height 꺼내오기
> - 어느 정도 중복되는 스타일은 전개연산자를 사용하여 ...styles.wrap, 이렇게 풀어주고 사용하기

<br />

### 유용한 컴포넌트

> - ActivityIndicator : 로딩
> - TouchableOpacity : 누르면 투명도가 변하는 애니메이션 있음
> - TouchableHighlight : 누르면 배경색이 변경, underlayColor 를 설정해야 변경됨
> - TouchableWithoutFeedback : 뭔가 사용자에게 효과를 보여주고 싶을 때는 TouchableOpacity, 그 외는 TouchableWithoutFeedback. 누르는 이벤트를 리스닝 중
> - Pressable : 위의 것과 비슷하지만 누르는 시간과 효과 설정 가능. 그리고 hipslop 으로 누르는 범위를 설정 가능
> - TextInput : input 태그와 동일. onFocus 는 화면을 터치하면 쓸 준비가 된 상태. onChangeText 는 onChange 함수. keyboardType 은 이메일이나 비밀번호 등에 따른 키보드 타입 지정(number-pad, email-address). returnKeyType 은 키보드의 enter 또는 완료 버튼의 모양을 변경. secureTextEntry 는 비밀번호 입력할 때 가려주는 것. muliline 은 한줄 이상 입력하는 경우 사용. onChangeText 에서 함수의 파람스로 event 를 받아올 수 있는데 이건 input 의 value 를 가져옴 실제로 이벤트나 타겟의 역할은 없음. autoCorrect 는 자동완성 기능. autoCapitalize 는 대문자로 만들고 싶은 것을 지정 가능. enter 버튼을 누르면 onSubmitEditing 이 발생

<br />

### 라이브러리 및 api

> - AsyncStorage : RN 에서 지원해주는 기본 기능 없어짐. expo 라이브러리 사용. setItem(키, 밸류). local storage 처럼 string 만 가능. 하지만 await 사용! 객체의 경우 json stringify 쓸 것
> - Alert : alert 는 Alert.alert() 로 사용. prompt 는 ios 만. confirm 처럼 사용하길 원하면 3번째 인자에 {text: 'cancel'}, 네번째 인자에 {text: 'I'm Sure'} 이런 식으로 입력 후 각각 누른 후 어떤 로직을 처리해주고 싶다면 객체 내에 onPress: () => {// 로직 입력} 이런 식으로 작성. ios 은 style: 'destructive' 를 입력하면 버튼 글씨가 변함

<br />

### 그 외

> - 리프레시가 잘 작동하지 않는다면 터미널에 가서 r 을 누르면 됨.
> - d 는 개발자 도구를 볼 수 있음
> - 데이터 set 하는 state 생성 시 초기값을 배열로 많이 설정하는데 객체가 좋음 hashmap. assign 으로 새로운 todo, 이전 todo 합쳐주기
> - expo install 을 해줄 경우 expo 버전과 라이브러리 버전을 같은 버전의 모듈로 설치해줌
