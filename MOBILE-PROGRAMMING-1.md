# Pertemuan Pertama Mobile-Android Doscom University 2019

Selamat anda mengambil Mobile-Android Doscom University 2019, pada akhir DU ini, anda akan paham bagaimana cara membuat single-screen Android app dengan tulisan and gambar.

![View](assets/View.png)

Dalam pelatihan ini, kita akan belajar step-by-step bagaimana untuk membuat sebuah aplikasi, seperti kartu ucapan selamat ulang tahun ini, dan bagaimana untuk menjalankannya pada sebuah android device.

![Card](assets/SSUltah.png)

Kemudian anda bisa untuk kostumisasi kartu ucapan untuk seseorang yang spesial pada masa mendatang. 
Pada pelatihan ini, anda akan belajar bagaimana menggunakan Android Studio, alat yang digunakan developers untuk membuat aplikasi.

## Inti dari Aplikasi Android

![View](assets/Diff.png)

## Views

![View](assets/View.png)

Pada android studio kita akan menggunakan style penulisan CamelCase, berbeda dengan html atau css yang menggunakan snake_case.
Contoh dari CamelCase
FedEx, iPod, PowerPoint, McDonalds

Pada Materi View, kita akan belajar
1. Layout
2. TextView
3. ImageView
4. Button

### 1. Layout
Layout pada android terdapat 3
1. ConstraintLayout
2. RelativeLayout
3. LinearLayout

### LinearLayout
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal" >
```
LinearLayout identik dengan android:orientation yaitu VERTICAL & HORIZONTAL

### RelativeLayout
```xml
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent" >
```
RelativeLayout identik dengan pemberian value = {id} pada tiap element

### 2. TextView
  
```xml
 <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/selamat_ulang_tahun"
        android:textSize="30sp"
        android:textColor="@color/putih"
        android:layout_alignParentTop="true"
        android:layout_alignParentLeft="true"/>
```

### 3. ImageView
```xml
<ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:src="@drawable/androidparty"
        android:scaleType="fitXY" />
```

### 4. Button
```xml
<Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Buka Kado"
        android:layout_centerInParent="true"
        android:onClick="kado"/>
```

Pada android studio user interface menggunakan bahasa XML, ukuran yang ditetapkan adalah:
1. Gambar = dp
2. Text = sp
3. layout_width/height = wrap_content / match_parent

---
#### ASSET
Download : - :bulb: [Asset BirthdayCard](https://s.id/BirthdayCard/)
#### XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scaleType="fitXY"
        android:src="@drawable/androidparty" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:text="Selamat Ulang Tahun"
        android:textColor="#FFF"
        android:textSize="30sp" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:text="From, DOSCOM"
        android:textColor="#FFF"
        android:textSize="25sp" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:onClick="kado"
        android:text="Buka Kado" />

</RelativeLayout>
```

### MainActivity
#### Penambahan OnClick Kado
```xml
public void kado(View view) {
            Toast.makeText(this,"Maaf belum ada kado untukmu",Toast.LENGTH_SHORT).show();

    }
```


---
## Hello Toast
![View](assets/Toast.png)
#### XML
```xml
<android.support.constraint.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.android.hellotoast.MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:text="@string/button_label_toast"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button_count"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginBottom="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginBottom="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="#FFFF00"
        android:gravity="center_vertical"
        android:text="@string/count_initial_value"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button_count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_toast" />
</android.support.constraint.ConstraintLayout>
```

#### MainActivity
```xml
public class MainActivity extends AppCompatActivity {

    private int mCount = 0;
    private TextView mShowCount;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mShowCount = (TextView) findViewById(R.id.show_count);
    }

    public void showToast(View view){
        Toast toast = Toast.makeText(this, R.string.toast_message,
                Toast.LENGTH_SHORT);
        toast.show();
    }
    
    public void countUp(View view){
        mCount++;
        if (mShowCount != null)
            mShowCount.setText(Integer.toString(mCount));
    }
    
}
```
---
### Git
```GIT
$ git config --global user.name "Doscom"
$ git config --global user.email Mobile@doscom.org
$ git init
$ git add .
$ git commit -m "first commit"
$ git remote add origin https://github.com/........./
$ git push -u origin master
```

---

## Referensi dan Tambahan
- :bulb: [Basic git dan github oleh hacktiv8](https://github.com/hacktiv8/phase-0-activities/blob/master/modules/git-github-basics.md)
- :bulb: [Tutorial interaktif Git dan Github oleh codesaya.com](https://codesaya.com/git/)
- :bulb: [UserInterface dan UserInput](https://www.udacity.com/)


---


---
credits:
- [Sololearn](https://www.sololearn.com/)
- [w3schools](https://www.w3schools.com/)
- [doscom](http://doscom.org/)
