---
layout: post
title: "JavaFX 라이프사이클"
subtitle: "JavaFX 라이프사이클"
category: Java
date: 2020-03-24
background: '/img/bg-index.jpg'
---

# JavaFX 라이프사이클

JavaFX 애플리케이션은 다음과 같은 순서로 진행됩니다.
<br>

|            Application.launch()             |
| :-----------------------------------------: |
|                 기본 생성자                 |
|                   init()                    |
|                   start()                   |
|                  **사용**                   |
| Platform.exit() 호출 또는 마지막 Stage 닫힘 |
|                   stop()                    |
|                  **종료**                   |

<br>

이때 호출되는 스레드는 `JavaFX-Launcher`와 `JavaFX Application Thread` 두가지입니다. 여기서 `JavaFX-Launcher`는 `init()`을 실행하며, 나머지는 모두  `JavaFX Application Thread` 가 수행합니다. 그 이유는 JavaFX API가 스레드에 안전하지 않아서 <u>멀티 스레드가 동시에 접근할 경우에 문제가 발생</u>하기 때문입니다.

<br>
<br>

이와 같은 과정을 Java에서 직접 확인하는 코드는 아래와 같습니다. 

`javafx.application.Application`을 상속받고, `start()` 메소드를 재정의한 후 `launch()` 메소드를 호출하면 이  `launch()` 메소드는 메인 클래스의 객체를 생성하고, 메인 윈도우를 생성하여 `start()` 메소드를 호출합니다. 이 과정에서 사용되는 스레드를 확인하며 스레드의 작동 순서를 이해할 수 있습니다.

<br>

```java
import javafx.application.Application;
import javafx.stage.Stage;

public class AppMain extends Application {
	public AppMain() {
		System.out.println(Thread.currentThread().getName()+": AppMain() 호출");
	}
	
	@Override
	public void init() throws Exception {
		System.out.println(Thread.currentThread().getName()+": init() 호출");
	}
	
	@Override
	public void start(Stage primaryStage) throws Exception {
		System.out.println(Thread.currentThread().getName()+": start() 호출");
		primaryStage.show();
	}
	
	@Override
	public void stop() throws Exception {
		System.out.println(Thread.currentThread().getName()+": stop() 호출");
	}
	
	public static void main(String[] args) {
		System.out.println(Thread.currentThread().getName()+": main() 호출");
		launch(args);
	}
}
```

실행결과 >>

![image](https://user-images.githubusercontent.com/37536366/77379816-00546980-6dbd-11ea-978c-5218bd986b20.png)


<br>
<br>
