## Intent
### Apa itu Intent?
Intent digunakan untuk berpindah ke activity lain pada android studio. Intent ini akan sering sekali dipakai nantinya didalam android studio.

Biar kebayang kita akan buat aplikasinya seperti dibawah ini, yang nantinya ada sebuat tombol yang ketika diklik maka akan berpindah ke Activity/halaman lainnya.

![Card](assets/intent1.png)
![Card](assets/Intent2.png)

### XML - 1
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/teks"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Ini Halaman Pertama"
        android:textSize="20sp" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/teks"
        android:layout_centerHorizontal="true"
        android:onClick="next"
        android:text="Next" />

</RelativeLayout>
```

### XML - 2
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Main2Activity">

    <TextView
        android:id="@+id/teks"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Ini Halaman Kedua"
        android:textSize="20sp" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/teks"
        android:layout_centerHorizontal="true"
        android:onClick="back"
        android:text="Back" />

</RelativeLayout>
```
## Intent
Intent bisa menggunkan 
1. [namaclass].this, [classTujuan].class
2. getApplicationContext(), [classTujuan].class

### Intent - 1
```xml
public void next(View view) {
        Intent i = new Intent(MainActivity.this,Main2Activity.class);
        startActivity(i);
    }
```

### Intent - 2
```xml
public void back(View view) {
        Intent i = new Intent(getApplicationContext(),MainActivity.class);
        startActivity(i);
    }
```

## GOJEK-CLONE
### Disini kita akan belajar cloning UI aplikasi GO-JEK 

![Card](assets/uigojek.png)

#### ASSET
Download : - :bulb: [Asset UI Gojek](https://s.id/UIGojekDU/)

### XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:layout_width="300dp"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:src="@drawable/logo" />

    <ImageView
        android:id="@+id/logo"
        android:layout_width="300dp"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:src="@drawable/logo_hitam" />

    <TextView
        android:id="@+id/service"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/logo"
        android:layout_centerHorizontal="true"
        android:text="PICK A SERVICE"
        android:textSize="24sp" />

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@+id/service">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gosend"
                    android:src="@drawable/menu_gosend" />

                <ImageView
                    android:id="@+id/goride"
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_marginLeft="0dp"
                    android:layout_weight="1"
                    android:onClick="goride"
                    android:src="@drawable/menu_goride" />
            </LinearLayout>
            //Gambar 1

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-SEND"
                    android:textAlignment="center" />

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-RIDE"
                    android:textAlignment="center" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gomart"
                    android:src="@drawable/menu_gomart" />

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gocar"
                    android:src="@drawable/car" />
                //Gambar 1
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Mart"
                    android:textAlignment="center" />

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Car"
                    android:textAlignment="center" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gobox"
                    android:src="@drawable/GoBox" />

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gosend"
                    android:src="@drawable/GoFood" />
                //Gambar 1
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Box"
                    android:textAlignment="center" />

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Food"
                    android:textAlignment="center" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gotix"
                    android:src="@drawable/GoTix" />

                <ImageView
                    android:layout_width="100dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:onClick="gopay"
                    android:src="@drawable/GoPay" />
                //Gambar 1
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Tix"
                    android:textAlignment="center" />

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:text="GO-Pay"
                    android:textAlignment="center" />
            </LinearLayout>

        </LinearLayout>
    </ScrollView>
</RelativeLayout>
```

### MainActivity
```xml
public void gosend(View view) {
        Toast.makeText(this, "Go-Send", Toast.LENGTH_SHORT).show();
    }

    public void goride(View view) {
        Toast.makeText(this, "Go-Ride", Toast.LENGTH_SHORT).show();
    }

    public void gomart(View view) {

        Toast.makeText(this, "Go-Mart", Toast.LENGTH_SHORT).show();
    }

    public void gocar(View view) {
        Toast.makeText(this, "Go-Car", Toast.LENGTH_SHORT).show();
    }

    public void gotix(View view) {
        Toast.makeText(this, "Go-Tix", Toast.LENGTH_SHORT).show();
    }

    public void gobox(View view) {
        Toast.makeText(this, "Go-Box", Toast.LENGTH_SHORT).show();
    }

    public void gopay(View view) {

        Toast.makeText(this, "Go-Pay", Toast.LENGTH_SHORT).show();
    }
```
