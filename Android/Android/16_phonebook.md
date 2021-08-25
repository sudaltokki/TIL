# 과제 - 전화번호부 만들기

1. 원하는 사람 수 만큼 등록하기
2. 그 사람들을 리스트로 만들고 클릿기 상세화면이 나오도록 만들기
3. 상세화면안에는 휴대전화 번호 나오게 하기

```
import android.view.View
import android.widget.TextView

class PhoneBookActivity : AppCompatActivity() {

override fun onCreate(savedInstanceState: Bundle?) {
super.onCreate(savedInstanceState)
setContentView(R.layout.activity_phone_book)

val phoneBook = createFakePhoneBook(30)
createPhoneBookList(phoneBook)
}

fun createFakePhoneBook(fakeNumber: Int = 10, phoneBook: PhoneBook = PhoneBook()) {
for (i in 0 until fakeNumber) {
Person(name = "" + i + "번째 사람", number = "" + i + "번째 사람이 전화 번호")
}
return phoneBook
}

fun createPhoneBookList(phoneBook: PhoneBook) {
val layoutInflater = LayoutInflater.from(this@PhoneBookActivity)
val container = findViewById<LinearLayout>(R.id.phonebook_list_container)
for (i in 0 until phoneBook.personList.size) {
val view = layoutInflater.inflate(R.layout.phonevook_item,)
val personNameView = view.findViewById<TextView>(R.id.person_name)
personNameView.setText(phoneBook.personList.get(i).name)
addSetOnClickListener(phoneBook.personList.get(i), view)
container.addView(view)
}
}
fun addSetOnClickListener(person:Person, view: View){
view.setOnClickListener{
val intent = Intent(this@PhoneBookActivity,
intent.putExtra("name",person.name)
intent.putExtra("number",person.number)
startActivity(intent)
PhoneBookDetailActivity::class.java)
}
}

class PhoneBook(){
//전화번호부
val personList = ArrayList<Person>()

fun addPerson(person : Person){
personList.add(person)
}
}

class Person(val name: String, var number: String)t
```

```
<LinearLayout
android:layout_width="match_parent"
android:layout_height="match_parent"
android: orientation = "vertical"
tools:context=".PhoneBookActivity">

<TextView
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:gravity="center"
android:text="전화번호부"
android:padding="4dp"
android:textSize="40dp"/>

<ScrollView
android:layout_width="match_parent"
android:layout_height="match_parent"
android:fillViewport="true"

<LinearLayout
andorid:id="@+id/phonebook_list_container"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical"/>

 </LinearLayout>

</ScrollView>

```
