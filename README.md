# Call-App
Introduction   Android is one of the most popular operating systems for mobile. In this article, I will show you how to create a Calling Application in Android Using Android Studio.   Requirements Android Studio version 2.3.3 Little bit XML and JAVA knowledge. Android Emulator (or) Android mobile Download link (Android Studio)
package abu.call;  
  
import android.Manifest;  
import android.content.pm.PackageManager;  
import android.net.Uri;  
import android.os.Bundle;  
import android.app.Activity;  
import android.content.Intent;  
import android.support.v4.app.ActivityCompat;  
import android.view.Menu;  
import android.view.View;  
import android.view.View.OnClickListener;  
import android.widget.Button;  
import android.widget.EditText;  
  
public class MainActivity extends Activity  
{  
    EditText et;  
    Button call_btn;  
    @Override  
    protected void onCreate(Bundle savedInstanceState)  
    {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
        et=(EditText)findViewById(R.id.editText1);  
        call_btn=(Button)findViewById(R.id.button1);  
        call_btn.setOnClickListener(new OnClickListener()  
        {  
            @Override  
            public void onClick(View v)  
            {  
                // TODO Auto-generated method stub  
                Intent i = new Intent(Intent.ACTION_CALL);  
                i.setData(Uri.parse("tel:"+et.getText().toString()));  
                startActivity(i);  
            }  
        });  
    }  
}  
