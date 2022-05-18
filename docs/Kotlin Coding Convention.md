# Kotlin Coding Convention
이 문서에서는 가독성과 협업이 가능한 코드를 위해 코딩 컨벤션을 정의합니다. 기본적으로 구글의 [Kotlin Style Guide](https://developer.android.com/kotlin/style-guide)을 따릅니다.

## Composable
### **매개변수 지정**
```kotlin
Box( 
  modifier = Modifier
    .fillMaxWidth()
    .padding(start = 30.dp),
  color = Color.Black,
  horizontalAlignment = Alignment.Center
) {
  ...
}
```
- 매개변수가 2개 이상이면 괄호를 여는 곳에서 한 줄을 띄운다
- modifier 매개변수를 항상 가장 위에 둔다
- chaining (Modifier.~~.~~...)은 속성마다 한 줄씩 띄운다
- 닫는 괄호 전에 한 줄을 띄운다.

### **화면 컴포저블**
```kotlin
// 컴포저블의 이름은 항상 명사형 => 파스칼 케이스
// Background와 Content 컴포저블을 항상 작성할 것!
@Composable
fun LoginScreen() {
  LoginBackground {
    LoginContent {
      ...
    } 
  }
}

// <화면명>Background: 배경색, Scrollable 등 지정
@Composable
private fun LoginBackground(
  // Content 마진: Scaffold의 하단 내비게이션바 높이 등
  margin: PaddingValues,
  // Trailing Lambda를 통해 내용 컴포저블 받기
  // Row, Column, Box 레이아웃 중 선택 
  content: @Composable <Layout>Scope.() => Unit
) {
  // Layout으로 Column을 사용했으므로 content는 ColumnScope.() => Unit
  Column(
    modifier = Modifier
      .fillMaxSize()
      .padding(margin)
      .background(Color),
    content = content
  )
}

// <화면명>Content: 내용물 공통 패딩 등 지정
@Composable
private fun LoginContent(
  content: @Composable <Layout>Scope.() => Unit
) {
  Column(
    modifier = Modifier
      .fillMaxSize()
      .padding(...),
    content = content
}
```