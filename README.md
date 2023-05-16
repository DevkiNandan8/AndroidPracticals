# AndroidPracticals
Serial No. 	Practical 
1. 	Create “Hello World” application that will display “Hello World” in the middle of the screen in the emulator. Also display “Hello World” in the middle of the screen in the android phone. 
2 . 	Create an application to display various android activity lifecycle phases. 
3 . 	Create an application with first activity with an editText and send button. On click of send button, make use of explicit intent to send text to second activity and display there in text view. 
4 . 	Create an application with first activity with an editText and send button. On click of send button, make use of implicit intent that uses a SEND ACTION and let user select app from app chooser and navigate to that application. 
5 . 	Create spinner with strings taken from resource folder (res >> value folder) and on changing the spinner value, Image will change. 
6 . 	Create a menu with 5 options and selected option should appear in text box in upper case. 
7. 	Create a radio button group with radio button of all courses in your college and on selecting a particular course, teacher- in- charge of that course should appear at the bottom of the screen. 
8. 	Create a list of all courses in your college and on selecting a particular course parent department and the teacher- in-charge of that department should appear at the bottom of the screen. 
9. 	a)	Create an application with three buttons (with different color names) vertically aligned, on selecting a button color of the screen will change. 
b)	Create an application with three buttons horizontally aligned, on selecting a button color of the screen will 
 	change. 
10. 	Create a Login application (check username and password). On successful login, pop up the message. ("Welcome username") 
11. 	Create a login application as above, on successful login redirect to another activity with logout button. On click of logout button a dialog appears with OK and CANCEL button. On OK button click go to login activity and on CANCEL stay at same activity. 
12. 	Create an application to Create, Insert, update and Delete operation on the database 


Objective 1. Create “Hello World” application that will display “Hello World” in the middle of the screen in the emulator. Also display “Hello World” in the middle of the screen in the android phone. 
 
Code: 
 
MainActivity.xml 
 
<?xml version="1.0" encoding="utf-8"?> 
 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<TextView android:layout_width="wrap_content" android:layout_height="wrap_content" android:rotationX="7" android:text="Hello World!" android:textColor="@color/teal_200" android:textSize="50sp" android:textStyle="bold|italic" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" app:layout_constraintVertical_bias="0.484" /> 
 
</androidx.constraintlayout.widget.ConstraintLayout 
 
> 
 
  
MainActivity.java 
 
 
 
package com.example.myapplication; import androidx.appcompat.app.AppCompatActivity; import android.os.Bundle; public class MainActivity extends 
AppCompatActivity { 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
} 
 
} 
 
Output: 
 
 
  
Objective 2. Create an application to display various android activity lifecycle phases. 
Activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="wrap_content" android:layout_height="wrap_content" tools:context=".MainActivity"> 
<TextView android:id="@+id/Display" android:layout_width="0dp" android:layout_height="wrap_conten 
t" 
android:layout_marginLeft="100dp" android:layout_marginBottom="250d p" android:fontFamily="sans-serif- black" android:text="@string/activity_life_cy cle" 
android:textAppearance="@style/Tex tAppearance.AppCompat.Large" android:textColor="@color/purple_50 
0" android:textColorHighlight="@color/b lack" android:textSize="50sp" android:textStyle="bold|italic" android:typeface="monospace" app:layout_constraintBottom_toBott omOf="parent" app:layout_constraintEnd_toEndOf=" parent" app:layout_constraintLeft_toLeftOf=" parent" app:layout_constraintRight_toRightOf 
="parent" app:layout_constraintTop_toTopOf=" parent" app:layout_constraintVertical_bias="1 
.0" /> 
 
</androidx.constraintlayout.widget.ConstraintLayout> 
 
 
 
 
MainActivity.java                                               
package com.example.lifecycle; import androidx.appcompat.app.AppCompatActivity; import android.os.Bundle; import android.widget.Toast; public class MainActivity extends AppCompatActivity { 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Created", 
Toast.LENGTH_SHORT); 
t.show(); 
 
} 
@Override protected void onResume() { super.onResume(); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Resumed", Toast.LENGTH_SHORT); 
t.show(); 
 
} 
 
@Override protected void onPause() { super.onPause(); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Paused", Toast.LENGTH_SHORT); 
t.show(); 
 
} 
 
@Override protected void onStart() { super.onStart(); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Started", Toast.LENGTH_SHORT); 
t.show(); 
 
} 
 
@Override protected void onStop() { super.onStop(); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Stopped", Toast.LENGTH_SHORT); 
t.show(); 
} 
 
@Override protected void onDestroy() { super.onDestroy(); 
Toast t = Toast.makeText(getApplicationContext(), "Activity Destroyed", Toast.LENGTH_SHORT); 
t.show(); 
 
} 
 
} 
 
Output: 
 
 
 
 
 
  
Objective 3. Create an application with first activity with an editText and send button. On click of send button, make use of explicit intent to send text to second activity and display there in text view. 
activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
 
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" 
 
tools:context=".MainActivity" android:padding="20sp"> 
 
<EditText android:layout_width="match_parent" android:layout_height="wrap_content" android:hint="Type Something" android:id="@+id/edittext" 
/> 
 
<Button android:layout_width="match_parent" android:layout_height="wrap_content" android:text="Submit" android:textSize="20sp" android:layout_below="@+id/edittext" android:id="@+id/button"/> 
</RelativeLayout> 
 
 
 
MainActivity.java 
package com.example.twoactivity; import androidx.appcompat.app.AppCompatActivity; import android.content.Intent; import android.os.Bundle; import android.view.View; import android.widget.Button; import android.widget.EditText; public class MainActivity extends AppCompatActivity { 
Button btn; 
EditText et; 
String st; 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); btn=findViewById(R.id.button); et=findViewById(R.id.edittext); btn.setOnClickListener(new View.OnClickListener(){ 
@Override public void 
onClick(View v){ 
 
Intent i=new Intent(MainActivity.this,SecondActivity.class); st=et.getText().toString(); 
i.putExtra("Value",st); startActivity(i); finish(); 
} 
 
}); 
 
} }  
activity_second.xml 
<?xml version="1.0" encoding="utf-8"?> 
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" 
 
tools:context=".SecondActivity"> 
 
<TextView android:id="@+id/textView" android:layout_width="match_parent" android:layout_height="match_parent" android:gravity="center" android:text="Value" android:textColor="@color/purple_200" android:textSize="50sp" android:textStyle="bold" /> 
</RelativeLayout> 
 
SecondActivity.java 
package com.example.twoactivity; import androidx.appcompat.app.AppCompatActivity; import android.os.Bundle; import android.widget.TextView; public class SecondActivity extends AppCompatActivity { 
TextView tv; 
String st; 
 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_second); tv=findViewById(R.id.textView); st=getIntent().getExtras().getString("Value"); tv.setText(st); 
} 
 
} 
 
Output: 
 
 
 
 
 
 
Objective 4. Create an application with first activity with an editText and send button. On click of send button, make use of implicit intent that uses a SEND ACTION and let user select app from app chooser and navigate to that application. 
activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<Button android:id="@+id/btnShare" android:layout_width="wrap_content" android:layout_height="wrap_content" android:text="Share Text" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent" /> 
</androidx.constraintlayout.widget.ConstraintLayout> 
 
MainActivity.java 
package com.example.implicitintent; import androidx.appcompat.app.AppCompatActivity; import android.content.Intent; import android.os.Bundle; import android.view.View; import android.widget.Button; public class MainActivity extends AppCompatActivity { 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); Button btnShare=findViewById(R.id.btnShare); btnShare.setOnClickListener(new View.OnClickListener() { 
@Override public void 
onClick(View v) { 
 
Intent intent=new Intent(Intent.ACTION_SEND); intent.setType("text/plain"); intent.putExtra(Intent.EXTRA_TEXT,"Hello 
There"); startActivity(intent.createChooser(intent,"Share")); 
} 
 
}); 
 
} 
 
} 
 
Output: 
 
 
 
 
  
 
Q5.Objective of Practical 5: Create spinner with strings taken from resource folder (res >> value folder) and on changing the spinner value, Image will change. 
 
activity_main.xml 
 
<?xml version="1.0" encoding="utf-8"?> 
 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<Spinner android:id="@+id/spinner" android:layout_width="0dp" android:layout_height="wrap_content" android:layout_marginStart="8dp" android:layout_marginLeft="8dp" android:layout_marginTop="16dp" android:layout_marginEnd="8dp" android:layout_marginRight="8dp" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" 
/> 
 
<ImageView android:id="@+id/image" android:layout_width="332dp" android:layout_height="323dp" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="@+id/spinner" app:layout_constraintVertical_bias="0.479" /> 
 
</androidx.constraintlayout.widget.ConstraintLayout> 
 
MainActivity.java 
package com.example.spinner; import androidx.appcompat.app.AppCompatActivity; import android.os.Bundle; import android.view.View; import android.widget.AdapterView; import android.widget.ArrayAdapter; import android.widget.ImageView; import android.widget.Spinner; public class MainActivity extends AppCompatActivity { private Spinner spinner; private ImageView image; 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); spinner=findViewById(R.id.spinner); image=findViewById(R.id.image); 
String [] birds={"Select One","Flamingo","Macaw","Kingfisher","Toucan"}; 
ArrayAdapter<String>adapter=new 
ArrayAdapter<String>(this,android.R.layout.simple_spinner_dropdown_item,birds); spinner.setAdapter(adapter); spinner.setOnItemSelectedListener(new 
AdapterView.OnItemSelectedListener() 
{ 
@Override 
 
public void onItemSelected(AdapterView<?> parent, View view, int position, long id) { switch (position){ case 1: image.setImageResource(R.drawable.flamingo); break; case 2: image.setImageResource(R.drawable.macaw); break; case 3: 
image.setImageResource(R.drawable.kingfisher); break; case 4: 
image.setImageResource(R.drawable.toucan); break; 
} 
 
} 
 
@Override public void onNothingSelected(AdapterView<?> parent) { 
} 
 
}); 
 
} 
 
} 
 
Output: 
 
  
  
 
 
 
Objective 6. Create spinner with strings taken from resource folder (res >> value folder) and on changing the spinner value, Image will change. 
 
activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<RelativeLayout android:layout_width="match_parent" android:layout_height="match_parent" android:layout_margin="80dp" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent"> 
<EditText android:layout_width="match_parent" android:layout_height="wrap_content" android:id="@+id/etMenuItem" android:layout_centerInParent="true" android:hint="Select an Option from the Menu" android:textAlignment="center" android:gravity="center_horizontal" /> 
 
</RelativeLayout> 
 
</androidx.constraintlayout.widget.ConstraintLayout> 
 
MainActivity.java 
package com.example.menuwithoptions; import androidx.appcompat.app.AppCompatActivity; import android.os.Bundle; import android.view.Menu; import android.view.MenuInflater; import android.view.MenuItem; import android.widget.EditText; public class MainActivity extends AppCompatActivity { private EditText etMenuItem; 
@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); etMenuItem=(EditText) findViewById(R.id.etMenuItem); 
} 
 
@Override public boolean onCreateOptionsMenu(Menu menu){ MenuInflater inflater=getMenuInflater(); inflater.inflate(R.menu.main_menu,menu); return true; 
} 
 
@Override public boolean onOptionsItemSelected(MenuItem item){ etMenuItem.setText(item.getTitle().toString().toUpperCa se()); return super.onOptionsItemSelected(item); 
} }  
main_menu.xml 
<?xml version="1.0" encoding="utf-8"?> 
 
<menu xmlns:android="http://schemas.android.com/apk/res/android"> 
 
<item android:id="@+id/miSettings" android:title="@string/settings" /> 
<item android:id="@+id/miBackup" android:title="@string/backup" /> 
<item android:id="@+id/miReset" android:title="@string/reset" /> 
<item android:id="@+id/miAbout" android:title="@string/about" /> 
<item android:id="@+id/miHelp" android:title="@string/help" /> 
</menu> 
Output: 
 
 
  
 
  
 
Objective 7 : Create a radio button group with radio button of all courses in your college and on selecting a particular course, teacher-in- charge of that course should appear at the bottom of the screen. 
 
activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<RelativeLayout android:layout_width="match_parent" android:layout_height="match_parent" android:layout_margin="75dp" 
app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent" > <RadioGroup android:layout_width="match_parent" 
android:layout_height="wrap_content" android:id="@+id/rgCourses" android:layout_centerInParent="true"> 
</RadioGroup> 
</RelativeLayout> 
</androidx.constraintlayout.widget.ConstraintLayout> 
MainActivity.java 
package com.example.courses; import androidx.appcompat.app.AppCompatActivity; 
import android.os.Bundle; import android.provider.MediaStore; import android.widget.RadioGroup; import android.widget.RadioButton; import com.google.android.material.snackbar.Snackbar; 
import java.util.HashMap; 
public class MainActivity extends AppCompatActivity { private RadioGroup rgCourses; 
private HashMap<String, String> coursesMap; 
@Override 
protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
initCourses(); 
} 
private void initCourses(){ rgCourses=(RadioGroup)findViewById(R.id.rgCourses); if 	(coursesMap==null){ 	coursesMap=new 
HashMap<>(); coursesMap.put("BSc(H) Computer Science"," Dr.V.S.Dixit"); 
coursesMap.put("BCom(H)"," Dr.Manika Jain"); coursesMap.put("BA(H) Sociology"," Dr. Apra Sinha"); for 
(String course : coursesMap.keySet()){ 
RadioButton rButton=new RadioButton(MainActivity.this); rButton.setText(course); rgCourses.addView(rButton); 
} 
rgCourses.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() { 
@Override public void onCheckedChanged(RadioGroup group, int checkedId) { int 
checkedRadioButtonId=rgCourses.getCheckedRadioButtonId(); RadioButton rButton=(RadioButton) findViewById(checkedRadioButtonId); 
Snackbar.make(rgCourses,coursesMap.get(rButton.getText()),Snackbar.LENGTH_SHORT) .show(); 
} 
}); 
} 
} 
}  
	Output: 	 
 
  
 
 
 
 
 
   
Q8) Create a list of all courses in your college and on selecting a particular course parent department and the teacher-in-charge of that department should appear at the bottom of the screen. activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<RelativeLayout android:layout_width="match_parent" android:layout_height="match_parent" android:layout_margin="75dp" 
app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent" > <RadioGroup android:layout_width="match_parent" android:layout_height="wrap_content" android:id="@+id/rgCourses" android:layout_centerInParent="true"> 
</RadioGroup> 
</RelativeLayout> 
</androidx.constraintlayout.widget.ConstraintLayout> 
MainActivity.java 
package com.example.incharge; import androidx.appcompat.app.AppCompatActivity; 
import android.os.Bundle; import android.provider.MediaStore; import android.widget.RadioGroup; import android.widget.RadioButton; 
import com.google.android.material.snackbar.Snackbar; import java.util.HashMap; 
public class MainActivity extends AppCompatActivity { private RadioGroup rgCourses; private HashMap<String, String> coursesMap; 
@Override protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); initCourses(); 
} 
private void initCourses(){ rgCourses=(RadioGroup)findViewById(R.id.rgCourses); if 	(coursesMap==null){ 	coursesMap=new 
HashMap<>(); coursesMap.put("BSc(H) Computer Science","Deptt of Computer Sc - Dr.V.S.Dixit"); 
coursesMap.put("BCom(H)","Deptt of Commerce - Dr.Manika Jain"); 
coursesMap.put("BA(H) Sociology"," Deptt of Economics - Dr. Apra Sinha"); for (String course : coursesMap.keySet()){ 
RadioButton rButton=new RadioButton(MainActivity.this); rButton.setText(course); rgCourses.addView(rButton); 
} 
rgCourses.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() { 
@Override public void onCheckedChanged(RadioGroup group, int 
	checkedId) 	{ 	int 
checkedRadioButtonId=rgCourses.getCheckedRadioButtonId(); 
RadioButton rButton=(RadioButton) findViewById(checkedRadioButtonId); 
Snackbar.make(rgCourses,coursesMap.get(rButton.getText()),Snackbar.LENGTH_SHORT) .show(); 
} 
}); 
} 
} 
} 
 
Output: 
 
 
 
  
 
   
 
 
 
Objective of Practical 9(a): 
Create an application with three buttons (with different color names) vertically aligned, on selecting a button color of the screen will change. Code: activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:id="@+id/layoutSuperParent" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<LinearLayout 
android:layout_width="wrap_content" android:layout_height="wrap_content" android:orientation="vertical" 
app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent"> 
<Button 
android:layout_width="150dp" android:layout_height="wrap_content" 
android:id="@+id/btnRed" android:layout_gravity="center" android:backgroundTint="@android:color/holo_red_dark" android:text="RED"/> 
<Button 
android:layout_width="150dp" android:layout_height="wrap_content" 
android:id="@+id/btnBlue" android:layout_gravity="center" android:backgroundTint="@android:color/holo_blue_light" android:text="BLUE"/> 
<Button 
android:layout_width="150dp" android:layout_height="wrap_content" android:id="@+id/btnGreen" android:gravity="center" android:backgroundTint="@android:color/holo_green_dark" android:text="GREEN"/> 
<Button 
android:layout_width="150dp" android:layout_height="wrap_content" android:id="@+id/btnReset" android:gravity="center" android:text="Reset"/> 
</LinearLayout> 
</androidx.constraintlayout.widget.ConstraintLayout> 
MainActivity.java 
package com.example.colorchangevertical; import androidx.appcompat.app.AppCompatActivity; import android.graphics.Color; import android.view.View; import android.widget.Button; import androidx.constraintlayout.widget.ConstraintLayout; import android.os.Bundle; 
public class MainActivity extends AppCompatActivity implements View.OnClickListener { 
private Button btnRed; private Button btnBlue; private Button btnGreen; private Button btnReset; 
private ConstraintLayout layoutSuperParent; 
@Override protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
layoutSuperParent=(ConstraintLayout)findViewById(R.id.layoutSuperParent); 
btnRed=(Button)findViewById(R.id.btnRed); btnBlue=(Button)findViewById(R.id.btnBlue); btnGreen=(Button)findViewById(R.id.btnGreen); btnReset=(Button)findViewById(R.id.btnReset); btnRed.setOnClickListener(this); btnBlue.setOnClickListener(this); btnGreen.setOnClickListener(this); btnReset.setOnClickListener(this); 
} 
@Override 
public void onClick(View v){ switch (v.getId()){ case R.id.btnRed: 
layoutSuperParent.setBackgroundColor(Color.RED); break; case R.id.btnBlue: 
layoutSuperParent.setBackgroundColor(Color.BLUE); break; case R.id.btnGreen: 
layoutSuperParent.setBackgroundColor(Color.GREEN); break; case R.id.btnReset: 
layoutSuperParent.setBackgroundColor(Color.TRANSPARENT); break; default: break; 
} 
} 
} 
Output: 
 
  
 
 
  
 
 
  
Objective 9b)Create an application with three buttons horizontally aligned, on selecting a button color of the screen will change. 
 
 
Objective of Practical 9(b): 
Create an application with three buttons horizontally aligned, on selecting a button color of the screen will change. 
Code: activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:id="@+id/layoutSuperParent" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> 
<LinearLayout android:layout_width="wrap_content" android:layout_height="wrap_content" android:orientation="horizontal" 
app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintLeft_toLeftOf="parent" app:layout_constraintRight_toRightOf="parent" app:layout_constraintTop_toTopOf="parent"> 
<Button 
android:layout_width="100dp" android:layout_height="wrap_content" 
android:id="@+id/btnRed" android:layout_gravity="center" android:backgroundTint="@android:color/holo_red_dark" android:text="RED"/> 
<Button 
android:layout_width="100dp" android:layout_height="wrap_content" 
android:id="@+id/btnBlue" android:layout_gravity="center" android:backgroundTint="@android:color/holo_blue_light" android:text="BLUE"/> 
<Button 
android:layout_width="100dp" android:layout_height="wrap_content" 
android:id="@+id/btnGreen" android:gravity="center" android:backgroundTint="@android:color/holo_green_dark" android:text="GREEN"/> 
<Button 
android:layout_width="100dp" 
android:layout_height="wrap_content" android:id="@+id/btnReset" android:gravity="center" android:text="Reset"/> 
</LinearLayout> 
</androidx.constraintlayout.widget.ConstraintLayout> 
MainActivity.java 
package com.example.colorchangehorizontal; import androidx.appcompat.app.AppCompatActivity; 
import android.graphics.Color; 
import android.view.View; import android.widget.Button; import androidx.constraintlayout.widget.ConstraintLayout; import android.os.Bundle; 
public class MainActivity extends AppCompatActivity implements View.OnClickListener { 
private Button btnRed; private Button btnBlue; private Button btnGreen; private Button btnReset; 
private ConstraintLayout layoutSuperParent; 
@Override protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
layoutSuperParent=(ConstraintLayout)findViewById(R.id.layoutSuperParent); 
btnRed=(Button)findViewById(R.id.btnRed); btnBlue=(Button)findViewById(R.id.btnBlue); btnGreen=(Button)findViewById(R.id.btnGreen); btnReset=(Button)findViewById(R.id.btnReset); btnRed.setOnClickListener(this); btnBlue.setOnClickListener(this); btnGreen.setOnClickListener(this); btnReset.setOnClickListener(this); 
} 
@Override public void onClick(View v){ switch (v.getId()){ case R.id.btnRed: 
layoutSuperParent.setBackgroundColor(Color.RED); break; case R.id.btnBlue: 
layoutSuperParent.setBackgroundColor(Color.BLUE ); break; case R.id.btnGreen: 
layoutSuperParent.setBackgroundColor(Color.GRE EN); break; case R.id.btnReset: 
layoutSuperParent.setBackgroundColor(Color.TRANSPARENT); break; default: break; 
} 
} 
} 
Output: 
 
 
 
  
 
   
Objective 10) Create a Login application (check username and password). On successful login, pop up the message. ("Welcome username") 
Create a Login application (check username and password). On successful login, pop up the message. ("Welcome username") Code: 
app/src/main/res/layout/activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schem as.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" 
android:layout_height="match_parent" tools:context=".MainActivity"> 
<EditText android:id="@+id/etEmail" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="240dp" android:autofillHints="false" android:ems="10" android:hint="@string/e_mail_id" android:inputType="textEmailAddress" 
app:layout_constraintBottom_toTopOf="@id/etPassword" 
app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" /> 
<EditText 
android:id="@+id/etPassword" android:layout_width="wrap_content" 
android:layout_height="wrap_content" 
android:layout_marginTop="10dp" android:autofillHints="false" android:ems="10" android:hint="@string/password" android:inputType="textPassword" 
app:layout_constraintBottom_toTopOf="@id/btnLogin" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/etEmail" /> 
<Button android:id="@+id/btnLogin" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="30dp" android:text="@string/login" app:layout_constraintBottom_toTopOf="@id/btnRegister" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/etPassword" /> 
<Button android:id="@+id/btnRegister" android:layout_width="wrap_content" 
android:layout_height="wrap_content" android:layout_marginBottom="250dp" android:text="@string/register" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/btnLogin" /> </androidx.constraintlayout.widget.ConstraintLayout> app/src/main/res/values/strings.xml 
<resources> 
<string name="app_name">LoginValidation</string> 
<string name="welcome">Welcome</string> 
<string name="log_out">Log Out</string> 
<string name="password">Password</string> 
<string name="e_mail_id">E-mail ID</string> 
<string name="login">Login</string> 
<string name="register">Register</string> 
<string name="cancel">Cancel</string> 
<string name="ok">Ok</string> 
</resources> 
app/src/main/java/com/example/loginvalidation/MainActivity.java package com.example.loginvalidation; 
import android.database.sqlite.SQLiteConstraintException; import android.os.Bundle; import android.util.Log; import android.widget.Button; import android.widget.EditText; import android.widget.Toast; 
import androidx.appcompat.app.AppCompatActivity; 
import com.example.loginvalidation.models.User; import com.example.loginvalidation.services.UserService; public class MainActivity extends AppCompatActivity { private 
EditText etEmail; private EditText etPassword; private Button btnLogin; private Button btnRegister; private 
UserService userService; @Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); userService = 
UserService.getInstance(); 
UserService.initDatabase(this); etEmail = (EditText) findViewById(R.id.etEmail); etPassword = (EditText) findViewById(R.id.etPassword); btnLogin = (Button) findViewById(R.id.btnLogin); btnRegister = (Button) findViewById(R.id.btnRegister); btnLogin.setOnClickListener(v -> { User user = validateCredentials(); if (user != null) { try { 
userService.login(user); 
Toast.makeText(this, "Welcome " + userService.getUser().em ail, Toast.LENGTH_SHORT).show(); 
} catch (IllegalStateException illegalStateException) { 
Toast.makeText(this, "Invalid Email/ 
Password", Toast.LENGTH_SHORT).show(); 
} catch (Exception e) { 
Log.d("TAG", e.getMessage()); 
Toast.makeText(this, "Error", Toast.LENGTH_SHORT).show(); 
} 
} 
}); 
btnRegister.setOnClickListener(v -> { User user = validateCredentials(); if (user != null) { try { userService.register(user); 
Toast.makeText(this, "Registered", Toast.LENGTH_SHORT).show(); 
} catch (SQLiteConstraintException sqLiteConstraintException) 
{ 
Toast.makeText(this, "Email 
Already Used", Toast.LENGTH_SHORT).show(); 
} catch (Exception e) { 
Toast.makeText(this, "Error", Toast.LENGTH_SHORT).show(); 
} 
} 
}); 
} 
private User validateCredentials() { 
String email = etEmail.getText().toString().trim(); String password = etPassword.getText().toString().trim(); if (email.length() == 0) { etEmail.setError("Enter your e-mail address"); return null; 
} 
if (password.length() == 0) { etPassword.setError("Enter 
your password"); return null; 
} 
return new User(email, password); 
} 
} 
app/src/main/java/com/example/loginvalidation/models/User.java package com.example.loginvalidation.models; 
import androidx.annotation.NonNull; import androidx.room.ColumnInfo; import androidx.room.Entity; import androidx.room.PrimaryKey; @Entity public class User { @PrimaryKey 
@NonNull 
@ColumnInfo(name = "email") public String email; 
@NonNull 
@ColumnInfo(name = "password") public String password; public User(@NonNull String email, @NonNull String password) { this.email 
= email; this.password = password; 
} 
} 
app/src/main/java/com/example/loginvalidation/data/UserDao.java package com.example.loginvalidation.data; 
import androidx.room.Dao; import androidx.room.Delete; import androidx.room.Insert; 
import androidx.room.Query; import java.util.List; import com.example.loginvalidation.models.User; 
@Dao 
public interface UserDao { 
@Query("SELECT * FROM user") 
List<User> getAll(); 
@Query("SELECT * FROM user WHERE email LIKE :email LIMIT 1") 
User findByEmail(String email); 
@Insert void insert(User user); @Delete void delete(User user); 
} 
app/src/main/java/com/example/loginvalidation/data/UserDatabase.java 
package com.example.loginvalidation.data; import androidx.room.RoomDatabase; import androidx.room.Database; 
import com.example.loginvalidation.models.User; @Database(entities = {User.class}, version = 1) public abstract class UserDatabase extends RoomDatabase { 
public abstract UserDao userDao(); 
} 
app/src/main/java/com/example/loginvalidation/services/UserService.java 
package com.example.loginvalidation.services; import 	android.content.Context; 	import androidx.room.Room; 
import com.example.loginvalidation.data.UserDatabase; import com.example.loginvalidation.models.User; public class UserService { private User user = null; 
private static UserService instance = null; private static UserDatabase database = null; public void login(User user) throws IllegalStateException { User u = database.userDao().findByEmail(user.email); if (!u.password.equals(user.password)) throw new IllegalStateException("Password Mismatch"); this.user = user; 
} 
public void register(User user) { database.userDao().insert(user); this.user = user; 
} 
public void logout() { this.user = null; 
} 
public User getUser() { return 
user; 
} 
public static UserService getInstance() { if (instance == null) { instance = new UserService(); 
} 
return instance; 
} 
public static void initDatabase(Context ctx) { 
if (database == null) { database = Room 
.databaseBuilder(ctx, UserDatabase.class, "login_module") 
.allowMainThreadQueries() 
.build(); 
} 
} 
} 
Output: 
 
  
 
  
 
Objective 11) Create a login application as above, on successful login redirect to another activity with logout button. On click of logout button a dialog appears with OK and CANCEL button. On OK button click go to login activity and on CANCEL stay at same activity. 
Code: 
app/src/main/AndroidManifest.xml <?xml 
version="1.0" encoding="utf-8"?> 
<manifest xmlns:android="http://schemas.android.com/apk/res/android" package="com.example.loginmodule"> <application android:allowBackup="true" android:icon="@mipmap/ic_launcher" android:label="@string/app_name" android:roundIcon="@mipmap/ic_launcher_round 
" android:supportsRtl="true" android:theme="@style/Theme.LoginModule"> 
<activity android:name=".MemberModule"></activity> 
<activity android:name=".MainActivity"> 
<intent-filter> 
<action android:name="android.intent.action.MAIN" /> 
<category android:name="android.intent.category.LAUNCHER" /> 
</intent-filter> 
</activity> 
</application> </manifest> app/src/main/res/layout/activity_main.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schem as.android.com/apk/res/android" 
xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity"> <EditText android:id="@+id/etEmail" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="240dp" android:autofillHints="false" android:ems="10" android:hint="@string/e_mail_id" android:inputType="textEmailAddress 
" 
app:layout_constraintBottom_toTopOf="@id/etPassword" 
app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" /> 
<EditText android:id="@+id/etPassword" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="10dp" android:autofillHints="false" android:ems="10" android:hint="@string/password" android:inputType="textPassword" app:layout_constraintBottom_toTopOf="@id/btnLogin" 
app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/etEmail" /> 
<Button android:id="@+id/btnLogin" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginTop="30dp" android:text="@string/login" app:layout_constraintBottom_toTopOf="@id/btnRegister" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/etPassword" /> 
<Button android:id="@+id/btnRegister" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginBottom="250dp" android:text="@string/register" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/btnLogin" /> </androidx.constraintlayout.widget.ConstraintLayout> app/src/main/res/layout/activity_member_module.xml 
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schem as.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MemberModule"> 
<TextView android:id="@+id/tvWelcome" android:layout_width="wrap_content" 
android:layout_height="wrap_content" android:text="@string/welcome" 
android:textAppearance="@style/TextAppearance.AppCompat.Display1" 
app:layout_constraintBottom_toTopOf="@id/tvEmail" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" /> <TextView android:id="@+id/tvEmail" android:layout_width="wrap_content" android:layout_height="wrap_content" android:text="" 
app:layout_constraintBottom_toTopOf="@id/btnLogout" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@id/tvWelcome" /> 
<Button 
android:id="@+id/btnLogout" android:layout_width="wrap_content" 
android:layout_height="wrap_content" android:text="@string/log_out" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toBottomOf="@+id/tvEmail" /> </androidx.constraintlayout.widget.ConstraintLayout> app/src/main/res/values/strings.xml 
<resources> 
<string name="app_name">LoginModule</string> 
<string name="welcome">Welcome</string> 
<string name="log_out">Log Out</string> 
<string name="password">Password</string> 
<string name="e_mail_id">E-mail ID</string> 
<string name="login">Login</string> 
<string name="register">Register</string> 
<string name="cancel">Cancel</string> 
<string name="ok">Ok</string> 
</resources> 
 
 
 
app/src/main/java/com/example/loginmodule/MainActivity.java 
 
package com.example.loginmodule; import 
android.content.Intent; 
import android.database.sqlite.SQLiteConstraintException; 
import android.os.Bundle; import android.util.Log; import android.widget.Button; import android.widget.EditText; import android.widget.Toast; import androidx.appcompat.app.AppCompatActivity; import com.example.loginmodule.models.User; import com.example.loginmodule.services.UserService; public class MainActivity extends AppCompatActivity { private EditText etEmail; private EditText etPassword; private 
Button btnLogin; private Button btnRegister; private UserService userService; 
@Override protected void onCreate(Bundle savedInstanceState) { 
super.onCreate(savedInstanceState); 
setContentView(R.layout.activity_main); userService = 
UserService.getInstance(); UserService.initDatabase(this); etEmail = (EditText) findViewById(R.id.etEmail); etPassword = (EditText) findViewById(R.id.etPassword); btnLogin = (Button) findViewById(R.id.btnLogin); btnRegister = (Button) findViewById(R.id.btnRegister); btnLogin.setOnClickListener(v -> { User user = validateCredentials(); if (user != null){ try { 
userService.login(user); 
Toast.makeText(this, "Logged In", Toast.LENGTH_SHORT).show(); startActivity(new Intent(this, MemberModule.class)); 
} catch (IllegalStateException illegalStateException) { Toast.makeText(this, 
"Invalid E- mail/Password", Toast.LENGTH_SHORT).show(); 
} catch (Exception e) { 
Log.d("TAG", e.getMessage()); 
Toast.makeText(this, "Error", Toast.LENGTH_SHORT).show();} 
} 
}); btnRegister.setOnClickListener(v -> { User user = validateCredentials(); if (user != null) { try { 
userService.register(user); 
Toast.makeText(this, "Registered", Toast.LENGTH_SHORT).show(); startActivity(new 	Intent(this, 	MemberModule.class)); 	} 	catch 
(SQLiteConstraintException sqLiteConstraintException) 
{ 
Toast.makeText(this, "E-mail Already Used", 
Toast.LENGTH_SHORT).show(); 
} catch (Exception e) { 
Toast.makeText(this, "Error", Toast.LENGTH_SHORT).show(); 
} 
} 
}); 
} 
private User validateCredentials() { 
String email = etEmail.getText().toString().trim(); String password = etPassword.getText().toString().trim(); if (email.length() == 0) { etEmail.setError("Enter your e-mail address"); return null; 
} 
if (password.length() == 0) { etPassword.setError("Enter 
your password"); return null; 
} 
return new User(email, password); 
} 
} 
app/src/main/java/com/example/loginmodule/MemberModule.java package com.example.loginmodule; 
import android.app.AlertDialog; import android.os.Bundle; import android.widget.TextView; import android.widget.Toast; import androidx.appcompat.app.AppCompatActivity; import com.example.loginmodule.models.User; import com.example.loginmodule.services.UserService; public class MemberModule extends AppCompatActivity { private User user; private UserService userService; private TextView tvEmail; private TextView btnLogout; 
@Override 
protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_member_module); userService = UserService.getInstance(); user = userService.getUser(); tvEmail = (TextView) findViewById(R.id.tvEmail); btnLogout = (TextView) findViewById(R.id.btnLogout); if (user == null) { super.finish(); } else { tvEmail.setText(user.email); 
} 
btnLogout.setOnClickListener(v -> { new AlertDialog.Builder(this) 
.setTitle("Logout") 
.setMessage("Are you sure you want to log out?") .setPositiveButton(android.R.string.ok, (dialog, which) - > logoutUser()) 
.setNegativeButton(android.R.string.cancel, null) 
.setIcon(android.R.drawable.ic_dialog_alert) 
.show(); 
}); 
} 
private void logoutUser() { userService.logout(); 
Toast.makeText(this, "Logged Out", Toast.LENGTH_SHORT).show(); super.finish(); 
} 
} 
app/src/main/java/com/example/loginmodule/models/User.java package com.example.loginmodule.models; 
import androidx.annotation.NonNull; import androidx.room.ColumnInfo; import androidx.room.Entity; import androidx.room.PrimaryKey; @Entity public class User { @PrimaryKey 
@NonNull 
@ColumnInfo(name = "email") public String email; 
@NonNull 
@ColumnInfo(name = "password") public String password; public User(@NonNull String email, @NonNull String password) { 
this.email = email; this.password = password; 
} 
} 
app/src/main/java/com/example/loginmodule/data/UserDao.java package com.example.loginmodule.data; 
import androidx.room.Dao; import androidx.room.Delete; import androidx.room.Insert; 
import androidx.room.Query; import java.util.List; 
import com.example.loginmodule.models.User; 
@Dao 
public interface UserDao { 
@Query("SELECT * FROM user") 
List<User> getAll(); 
@Query("SELECT * FROM user WHERE email LIKE :email LIMIT 1") 
User findByEmail(String email); 
@Insert void insert(User user); @Delete void delete(User user); 
} 
app/src/main/java/com/example/loginmodule/data/UserDatabase.java 
package com.example.loginmodule.data; import androidx.room.RoomDatabase; import androidx.room.Database; import com.example.loginmodule.models.User; @Database(entities = {User.class}, version = 1) public abstract class 
UserDatabase extends RoomDatabase { public abstract 
UserDao userDao(); 
} 
app/src/main/java/com/example/loginmodule/services/UserService.java package com.example.loginmodule.services; import android.content.Context; import androidx.room.Room; 
import com.example.loginmodule.data.UserDatabase; import 
com.example.loginmodule.models.User; 
public class UserService { private User user = null; private static UserService instance = null; private static 
UserDatabase database = null; public void login(User 
user) throws IllegalStateException { User u = database.userDao().findByEmail(user.email); if (!u.password.equals(user.password)) throw new IllegalStateException("Password Mismatch"); this.user = user; 
} 
public void register(User user) { database.userDao().insert(user); this.user = user; 
} 
public void logout() { this.user = null; 
} 
public User getUser() { return 
user; 
} 
public static UserService getInstance() { if (instance == null) { instance = new UserService(); 
} 
return instance; 
} 
public static void initDatabase(Context ctx) { 
if (database == null) { database = Room 
.databaseBuilder(ctx, UserDatabase.class, "login_module") 
.allowMainThreadQueries() 
.build(); 
} 
} 
} 
Output: 
 
 
 
Q12) Create an application to Create, Insert, update and Delete operation on the database. 
 
activity_main.xml 
 
 
 
<?xml version="1.0" encoding="utf-8"?> 
 
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" 	android:padding="10dp" tools:context=".MainActivity"> 
 
 
<TextView 	android:id="@+id/textTitle" android:layout_width="match_parent" android:layout_height="wrap_content" android:text="Enter Your Application Form Details" android:textSize="24sp" android:layout_marginTop="20dp" tools:ignore="HardcodedText" /> 
 
 
<EditText 	android:id="@+id/name" android:layout_width="match_parent" android:layout_height="wrap_content" android:hint="Enter Your Name:" android:textSize="24sp" android:layout_below="@+id/textTitle" android:inputType="textPersonName" android:autofillHints="" /> 
 
 
<EditText android:id="@+id/age" android:layout_width="match_parent" android:layout_height="match_parent" android:layout_below="@+id/name" android:autofillHints="" android:hint="Enter Your Age:" android:inputType="number" android:textSize="24sp" /> 
 
 
<EditText 	android:id="@+id/mobile" android:layout_width="match_parent" android:layout_height="wrap_content" android:padding="10dp" android:hint="Enter Your Mobile Number:" android:textSize="24sp" android:layout_below="@+id/age" android:inputType="number" android:autofillHints="" /> 
 
 
<Button android:id="@+id/buttonInsert" android:layout_width="match_parent" android:layout_height="wrap_content" android:textSize="24sp" android:text="Insert New Data" android:layout_marginTop="24dp" android:layout_below="@id/mobile" /> 
 
 
<Button android:id="@+id/buttonUpdate" android:layout_width="match_parent" android:layout_height="wrap_content" android:textSize="24sp" android:text="Update Your Data" android:layout_marginTop="24sp" android:layout_below="@id/buttonInsert" /> 
<Button android:id="@+id/buttonDelete" android:layout_width="match_parent" android:layout_height="wrap_content" android:textSize="24sp" android:text="Delete Your Record" android:layout_marginTop="24dp" android:layout_below="@id/buttonUpdate"/> <Button android:id="@+id/buttonView" android:layout_width="match_parent" android:layout_height="wrap_content" android:textSize="24sp" android:text="Display Your Record" android:layout_marginTop="24sp" android:layout_below="@id/buttonDelete"/> 
</RelativeLayout> 
 
 
 
MainActivity.java 
 
 
 
package com.example.lokdbapp; 
 
 
 
import androidx.appcompat.app.AlertDialog; import androidx.appcompat.app.AppCompatActivity; 
 
 
import android.database.Cursor; import android.os.Bundle; import android.view.View; import android.widget.Button; import android.widget.EditText; import android.widget.Toast; 
 
 
public class MainActivity extends AppCompatActivity { 
EditText name, age, mobile; 
Button insert, update, delete, view; 
DBhelper db; 
 
 
 
 
protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main); 
 
	name = findViewById(R.id.name); 	age 
 
= findViewById(R.id.age); 	mobile = findViewById(R.id.mobile); 	insert = findViewById(R.id.buttonInsert); 	 update = findViewById(R.id.buttonUpdate); 	   delete = findViewById(R.id.buttonDelete); 	  view = findViewById(R.id.buttonView); 	db = new 
DBhelper(this); 
 
 
insert.setOnClickListener(new View.OnClickListener() { 
	@Override 	public void 
onClick(View view) { 
 
String nameTXT = name.getText().toString(); 
String ageTXT = age.getText().toString(); 
String mobileTXT = mobile.getText().toString(); 
 
Boolean checkinsertdata = db.insertuserdata(nameTXT, ageTXT, mobileTXT); if (checkinsertdata == true) { 
Toast.makeText(MainActivity.this, "New Record Inserted", Toast.LENGTH_SHORT).show(); 
 
} else { 
 
Toast.makeText(MainActivity.this, "New Record Not Inserted", Toast.LENGTH_SHORT).show(); 
 
} 
 
} 
 
}); 
 
 
 
update.setOnClickListener(new View.OnClickListener() { 
@Override 
public void onClick(View view) { 
 
String nameTXT = name.getText().toString(); 
String ageTXT = age.getText().toString(); 
 
String mobileTXT = mobile.getText().toString(); 
 
Boolean checkupdatedata = db.updateuserdata(nameTXT, ageTXT, mobileTXT); 
if (checkupdatedata == true) 
Toast.makeText(MainActivity.this, "Record Updated", Toast.LENGTH_SHORT).show(); else 
Toast.makeText(MainActivity.this, "Record Not Updated", Toast.LENGTH_SHORT).show(); 
 
} 
 
}); 
 
 
 
delete.setOnClickListener(new View.OnClickListener() { 
	@Override 	public void 
onClick(View view) { 
 
String nameTXT = name.getText().toString(); 
 
Boolean checkdeletedata = db.deletedata(nameTXT); 
if (checkdeletedata == true) 
Toast.makeText(MainActivity.this, "Record Deleted", Toast.LENGTH_SHORT).show(); else 
Toast.makeText(MainActivity.this, "Record Not Deleted", Toast.LENGTH_SHORT).show(); 
 
} 
 
}); 
 
 
 
view.setOnClickListener(new View.OnClickListener() { public void onClick(View view) { 	Cursor res = db.getdata(); 
 
if (res.getCount() == 0) { 
Toast.makeText(MainActivity.this, "Record Not Exists", Toast.LENGTH_SHORT).show(); return; 
} 
 
StringBuffer buffer = new StringBuffer(); 
 
	while (res.moveToNext()) { 	 	buffer.append("sid:" + 
res.getString(0) + "\n"); 	buffer.append("name:" + 
res.getString(1) + "\n"); 	buffer.append("age:" + 
res.getString(2) + "\n"); 	buffer.append("mobile:" + 
res.getString(3) + "\n"); 
} 
 
AlertDialog.Builder builder = new 
AlertDialog.Builder(MainActivity.this); 	builder.setCancelable(true); builder.setTitle("Application Entries"); builder.setMessage(buffer.toString()); 	builder.show(); 
} 
 
}); 
 
} 
 
} 
 
 
 
DBhelper.java 
 
 
 
package com.example.lokdbapp; 
 
 
 
import android.content.ContentValues; import android.content.Context; 
import android.database.Cursor; import android.database.sqlite.SQLiteDatabase; import android.database.sqlite.SQLiteOpenHelper; 
 
 
public class DBhelper extends SQLiteOpenHelper { public DBhelper( Context context) { 
  
super(context, "userDB5.db", null, 1); 
 
} 
 
 
 
@Override 	public void onCreate(SQLiteDatabase db) { 
db.execSQL("create Table appform(_sid integer primary key autoincrement, name TEXT, age TEXT, mobile TEXT)"); 
 
} 
 
 
 
	@Override 	public void onUpgrade(SQLiteDatabase 
db, int i, int i1) {db.execSQL("drop Table if exists appform"); 
} 
 
public Boolean insertuserdata(String name, String age, String mobile) { 
SQLiteDatabase db = this.getWritableDatabase(); ContentValues contentValues = new ContentValues(); contentValues.put("name", name); contentValues.put("age", age); contentValues.put("mobile", mobile); 	long result = db.insert("appform", null, contentValues); if (result == -1) 
	{ 	return 
 
false; 
 
} 
 
else 
 
{ 
 return true; 
 
} 
 
} 
 
 
 
public Boolean updateuserdata(String name, String age, String mobile) { 
SQLiteDatabase db = this.getWritableDatabase(); ContentValues contentValues = new ContentValues(); contentValues.put("age", age); 	contentValues.put("mobile", mobile); 
Cursor cursor = db.rawQuery("Select * from appform where name = ?", new String[]{name}); if (cursor.getCount() > 0) { long result = db.update("appform", contentValues, "name = ?", new String[] {name}); 
if (result == -1) 
 
{ 
 return false; 
 
} 
 
else 
 
{ 
 return true; 
 
} 
 
} 
 
else { 
return false; 
} 
 
} 
 
public Boolean deletedata(String name) 
 
{ 
 
SQLiteDatabase db = this.getWritableDatabase(); 
 
Cursor cursor = db.rawQuery("Select * from appform where name = ?", new String[] {name}); if (cursor.getCount() > 0) 
{ 
 
long result = db.delete("appform", "name=?", new String[]{name}); 
if (result == -1) 
{ 
 return false; 
 
} 
 
else 
 
{ 
 return true; 
 
} 
 
} 
 
else 
 
{ 
 return false; 
 
} 
 
} 
 
public Cursor getdata() 
 
{ 
SQLiteDatabase db = this.getWritableDatabase(); Cursor cursor = db.rawQuery("Select * from appform",null); return cursor; 
} 
 
} 
 
Output: 
 
 
  
