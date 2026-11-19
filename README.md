# Compose

在Compose中如何思考？
什么是Compose？
Compose带来了哪些工具？
Compose技巧
MAD Skills 是 Google Android Developers 官方推出的一套现代 Android 开发技术视频和文章教程系列。Modern Android Development 的缩写。

声明式UI框架
与传统的view的区别，如何转变思路

不使用xml，充分利用kotlin各种结构

来看看一个问答app
 <!-- survey_answer . xml

<LinearLayout android:orientation="horizontal" >

<ImageView
android:id="@+id/answer_image"

<TextView
android:id="@+id/answer_text" ... />

<RadioButton
android : id="@+id/answer_radio_button"

</LinearLayout>

findbyid得到引用，在使用各种set方法设置UI
当状态发生变化时，我们需要手动更新依赖

在kotlin中是这样的
@Composable
fun SurveyAnswer (answer : Answer) {
Row {
Image (answer. image)
Text(answer.text)
RadioButton(false, onClick = { /* ... */ })
}

UI是函数而不是对象
当状态发生变化重新生成用户界面这个过程，我们叫重组

State control UI
Events control State
 

@Composable
fun SurveyAnswer(answer: Answer) {/* ... */}

@Composable
fun SingleChoiceQuestion(answers: List<Answer>) {
Column {
answers. forEach { answer ->
SurveyAnswer (answer = answer)

}

基本知识
开始使用
Hello Word Codelab
如何使用 Android Studio 创建 Android 应用
如何在 Android Studio 中使用预览工具运行应用
如何使用 Kotlin 更新文本
如何使用 Jetpack Compose 更新界面
如何在 Jetpack Compose 中使用预览功能预览应用

Project 标签页/视图
Android 视图

onCreate() 函数是此 Android 应用的入口点，并会调用其他函数来构建界面。

setContent() 函数用于通过可组合函数定义布局。任何标有 @Composable 注解的函数都可通过 setContent() 函数或其他可组合函数进行调用。

modifier: Modifier = Modifier这里传递空的Modifier而不是null

@Composable 函数无法返回任何内容。

@Preview 注解会告知 Android Studio 此可组合函数应显示在此文件的设计视图中。

@Preview 注解可以接收名为 showBackground 的参数。如果 showBackground 设置为 true，则会向可组合函数预览添加背景。

带有非默认参数的 Composable 函数，不能直接被 @Preview 预览，除非你用 @PreviewParameter 标注参数。

使用 Surface 将文本包围起来，请突出显示该行文本，按下 Alt+Enter选择 Surround with widget。

打开设置，选择系统，查看Windows系统信息

Android 虚拟设备 (AVD)

将使用设备管理器来创建 Android 虚拟设备 (AVD)。AVD 是移动设备的软件版本（也称为模拟器），可在计算机上运行，以及模拟特定类型 Android 设备的配置。它可以是任何手机、平板电脑、电视、手表或 Android Auto 设备。我们将使用 AVD 来运行 Greeting Card 应用。

Tools > Device Manager。

了解如何编写可组合函数，例如 Text、Column 和 Row 可组合函数。
如何在布局中显示应用里的文本。
如何设置文本格式，例如更改文本大小。

可缩放像素 (SP) 是字体大小的度量单位。Android 应用中的界面元素使用两种不同的度量单位：一种是您稍后将为布局使用的密度无关像素 (DP)，另一种就是可缩放像素 (SP)。

界面层次结构基于包含机制，意即一个组件可以包含一个或多个组件

Compose 中的 3 个基本标准布局元素是 Column、Row 和 Box 可组合项。
lambda 和尾随 lambda 语法
当最后一个形参是函数时，Kotlin 提供了一种特殊语法来将函数作为形参传递给函数。
可以将函数放在圆括号外部的大括号中，而不是放在圆括号内。这是 Compose 中的一种常见且推荐的做法，因此您需要熟悉代码的格式。

 View > Tool Windows > Resource Manager，或点击 Project 窗口旁边的 Resource Manager 标签页。

将为应用添加一个 Image 可组合项，并将其图片设为您下载的图片，然后调整图片的位置和大小，使其填满整个屏幕。
