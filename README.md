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

