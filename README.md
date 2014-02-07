bugfree-andy
============

Loginscreen

strings.xml

<?xml version="1.0" encoding="utf-8"?>
<resources>

    <string name="hello">Hello World, LoginActivity!</string>
    <string name="app_name">LoginExample</string>
      <string name="login_title">Login Screen</string>
      <string name="username">Username</string>
      <string name="password">Password</string>
      <string name="login">Login</string>
</resources>


login.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >
    
     <TextView
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:text="@string/login_title"
        android:gravity="center_horizontal"
        android:textSize="20dp" 
        />
        
     <ImageView
        android:layout_width="fill_parent"
        android:layout_height="0dp"
        android:gravity="center_horizontal"
        android:src="@drawable/ic_launcher"
        android:layout_weight="1.1"
        android:padding="20dp"
        />
      <LinearLayout
            android:layout_width="fill_parent"
      android:layout_height="wrap_content"
      android:orientation="horizontal"
      android:layout_weight="0.01"
      android:padding="10dp">
     
        <TextView
            android:layout_height="wrap_content"
            android:layout_width="0dp"
            android:layout_weight="1.0"
            android:text="@string/username"
            android:textSize="18dp"
            />
        <EditText
            android:id="@+id/username"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1.0"
            android:ems="10"
            android:inputType="text" >

            <requestFocus />
        </EditText>

    </LinearLayout>  
    
     <LinearLayout
            android:layout_width="fill_parent"
      android:layout_height="wrap_content"
      android:orientation="horizontal"
      android:layout_weight="0.01"
      android:padding="10dp"
      >
        <TextView
            android:layout_height="wrap_content"
            android:layout_width="0dp"
            android:layout_weight="1.0"
            android:text="@string/password"
            android:textSize="18dp"
            />
        <EditText
            android:id="@+id/password"
            android:layout_height="wrap_content"
            android:layout_width="0dp"
            android:layout_weight="1.0"
            android:inputType="textPassword"
            />
    </LinearLayout>
    <Button
        android:id="@+id/login"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/login"
        android:layout_margin="10dp"
        />
</LinearLayout>


LoginActivity.java

package com.manoj.login;
import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
public class LoginActivity extends Activity {
      String userName, passWord;
      EditText username, password;
      Button login;    
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.login);
        // UI elements gets bind in form of Java Objects
        username = (EditText)findViewById(R.id.username);
        password = (EditText)findViewById(R.id.password);
        login = (Button)findViewById(R.id.login);
        // now we have got the handle over the UI widgets
        // setting listener on Login Button
        // i.e. OnClick Event
        login.setOnClickListener(loginListener);  
    }
    private OnClickListener loginListener = new OnClickListener() {
      public void onClick(View v) {
//getting inputs from user and performing data operations
                   
            if(username.getText().toString().equals("manoj") &&
                        password.getText().toString().equals("KIT")){
// responding to the User inputs
                  Toast.makeText(getApplicationContext(), "Login Successfully !!!", Toast.LENGTH_LONG).show();      
            }else
                  Toast.makeText(getApplicationContext(), "Login Not Successful !!!", Toast.LENGTH_LONG).show();                           
      }
    };
}
