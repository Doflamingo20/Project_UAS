# UAS_PEMROGRAMAN_MOBILE


Nama    : Dimas Aditya Putranto

NIM     : 312210489

Kelas   : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

Dosen Pengampu   : Donny Maulana, S.Kom., M.M.S.I.






# **Daftar Isi**
***Harap klik satu persatu agar update penjelasan dan hasil program terlihat berurutan***


- **[Tugas](#tugas)**



- **[Penjelasan & Hasil Program Tugas ](#penjelasan--hasil-program-tugas)**



- **[Demo Tugas](#demo-tugas)**


## Tugas
![Soal](https://github.com/Doflamingo20/Project_UAS/assets/130146099/6d167755-7c30-45e2-875d-88fa2c0b7d13)




> **Pada tugas kali saya juga akan menambahkan video trailer di setiap film**


## Penjelasan & Hasil Program Tugas

> Pada tugas kali ini saya melakukan perubahan pada nama aplikasi, lalu gambar icon aplikasi dan juga pada splashscreen, untuk cara dan isi code nya sama seperti pada tugas 2 hanya menyesuaikan saja dengan yang baru.

**Fill in All The Code in This Project :**
> 1. ***Gradle Script*** => `build.gradle.kts (Module :app)`
```
plugins {
    id("com.android.application")
}

android {
    namespace = "com.example.project_uas"
    compileSdk = 34

    defaultConfig {
        applicationId = "com.example.project_uas"
        minSdk = 24
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_1_8
        targetCompatibility = JavaVersion.VERSION_1_8
    }
}

dependencies {

    implementation("androidx.appcompat:appcompat:1.6.1")
    implementation("com.google.android.material:material:1.11.0")
    implementation("androidx.constraintlayout:constraintlayout:2.1.4")
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
}

```
- Setelah itu klik `Sync now`

> 2. ***AndroidManifest.xml***
- Lengkapi code ini pada `AndroidManifest.xml` yang sudah berisikan dengan code-code di project sebelumnya.
```
<activity android:name=".VideoPlayerActivity" />
```

> 3. ***Java***

=> Pada `MainActivity.java` saya melakukan penambahan code, yaitu isi code keseluruhannya adalah :
- `MainAcitivity.java`
```
package com.example.project_uas;

import android.annotation.SuppressLint;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import androidx.appcompat.app.AppCompatActivity;


public class MainActivity extends AppCompatActivity {

    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        findViewById(R.id.cdMenu5).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                setAlarm();
            }
        });

        findViewById(R.id.cdMenu1).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Ketika tombolSatu ditekan, pindah ke HelloActivity
                Intent helloworld = new Intent(MainActivity.this, HelloActivity.class);
                startActivity(helloworld);
            }
        });

        findViewById(R.id.cdMenu2).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Ketika tombolDua ditekan, lakukan aksi yang diinginkan
                // Misalnya, pindah ke aktivitas lain atau jalankan fungsi khusus
                Intent toast = new Intent(MainActivity.this, CountActivity.class);
                startActivity(toast);
            }
        });

        findViewById(R.id.cdMenu3).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Ketika tombolDua ditekan, lakukan aksi yang diinginkan
                // Misalnya, pindah ke aktivitas lain atau jalankan fungsi khusus
                Intent sianida = new Intent(MainActivity.this, SianidaActivity.class);
                startActivity(sianida);
            }
        });

        findViewById(R.id.cdMenu4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Ketika tombolDua ditekan, lakukan aksi yang diinginkan
                // Misalnya, pindah ke aktivitas lain atau jalankan fungsi khusus
                Intent twoactivity = new Intent(MainActivity.this, TwoActivity.class);
                startActivity(twoactivity);
            }
        });

        findViewById(R.id.cdMenu7).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Ketika tombolDua ditekan, lakukan aksi yang diinginkan
                // Misalnya, pindah ke aktivitas lain atau jalankan fungsi khusus
                Intent fragmentactivity = new Intent(MainActivity.this, FragmentActivity.class);
                startActivity(fragmentactivity);
            }
        });

        findViewById(R.id.cdMenu6).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Example location: Jakarta, Indonesia
                Uri geoLocation = Uri.parse("geo:-6.2088,106.8456");
                openMaps(geoLocation);
            }
        });
    }

    private void setAlarm() {
        Intent alarmIntent = new Intent(android.provider.AlarmClock.ACTION_SET_ALARM);
        // Add extra details for the alarm, e.g., alarm time, label, etc.
        // alarmIntent.putExtra(...
        startActivity(alarmIntent);
    }
    private void openMaps(Uri geoLocation) {
        Intent maps = new Intent(Intent.ACTION_VIEW);
        maps.setData(geoLocation);
        if (maps.resolveActivity(getPackageManager()) != null) {
            startActivity(maps);
        }
    }

}

```
> Note : Isi code pada keseluruhan tugas kali ini tetap sama seperti pada isi code tugas sebelumnya yaitu seperti *Java class* dan untuk *res/layout* hanya sedikit merubah design, pada tugas ini saya hanya mencantumkan dan menjelaskan code-code yang ditambahkan untuk `Fragment` saja.


- Untuk package name bisa di sesuaikan dengan package name project kita masing-masing, disini saya melanjutkan dari package name project sebelumnya.

=> `FragmentActivity.java`
```
package com.example.project_uas;

import android.annotation.SuppressLint;
import android.content.Context;
import android.graphics.drawable.ColorDrawable;
import android.os.Bundle;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentStatePagerAdapter;
import androidx.viewpager2.widget.ViewPager2;

import com.google.android.material.tabs.TabLayout;

import java.util.Objects;

public class FragmentActivity extends AppCompatActivity {

    TabLayout tabLayout;
    ViewPager2 viewPager2;
    ViewAdapter adapter;

    @SuppressLint({"NewApi", "MissingInflatedId"})
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_movie);

        Objects.requireNonNull(getSupportActionBar()).setBackgroundDrawable(new ColorDrawable(getColor(R.color.cream)));

        tabLayout = findViewById(R.id.tab);
        viewPager2 = findViewById(R.id.view);
        adapter = new ViewAdapter(this);
        viewPager2.setAdapter(adapter);

        tabLayout.addOnTabSelectedListener(new TabLayout.OnTabSelectedListener() {
            @Override
            public void onTabSelected(TabLayout.Tab tab) {
                viewPager2.setCurrentItem(tab.getPosition());
            }

            @Override
            public void onTabUnselected(TabLayout.Tab tab) {

            }

            @Override
            public void onTabReselected(TabLayout.Tab tab) {

            }
        });

        class Halaman extends FragmentStatePagerAdapter {
            Context context;
            int jumlah_tab;

            Halaman(Context context, FragmentManager fm, int jml_tab)
            {
                super(fm);
                this.context=context;
                this.jumlah_tab=jml_tab;
            }

            @NonNull
            @Override
            public Fragment getItem(int posisition){
                switch (posisition){
                    case 0:return new ActionFragment();
                    case 1:return new ComedyFragment();
                    case 2:return new RomanceFragment();
                }
                return null;
            }

            @Override
            public int getCount(){
                return jumlah_tab;
            }
        }

        viewPager2.registerOnPageChangeCallback(new ViewPager2.OnPageChangeCallback() {
            @Override
            public void onPageSelected(int position) {
                super.onPageSelected(position);
                tabLayout.getTabAt(position).select();
            }
        });

    }
}

```
=> Membuat file fragment dengan cara klik kanan pada `MainActivity.java` lalu pilih dan klik fragment, setelah itu kita pilih dan klik fragment (Blank), setelah itu kita beri nama `ActionFragment`, `ComedyFragment`, `RomanceFragment`. Untuk file fragment sudah sekaligus dengan file layout xml nya (code berada pada bagian res `layout`)

- `ActionFragment.java` :
```
package com.example.project_uas;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.Button;
import android.widget.Toast;

import androidx.fragment.app.Fragment;


public class ActionFragment extends Fragment {

    private static final String TAG = "ActionFragment";

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        // Inflate the layout for this fragment
        setHasOptionsMenu(true);
        View view = inflater.inflate(R.layout.fragment_action, container, false);

        // Find the button by its ID
        Button tensuraButton = view.findViewById(R.id.tensura);
        Button bokunoheroButton = view.findViewById(R.id.bokunohero);
        Button swordButton = view.findViewById(R.id.sword);
        Button cloverButton = view.findViewById(R.id.clover);
        Button fuutoButton = view.findViewById(R.id.fuuto);

        // Set click listener for each button
        tensuraButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Tensura button clicked");
                playVideo(R.raw.tensura);
            }
        });

        bokunoheroButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Transformers button clicked");
                playVideo(R.raw.bokunohero);
            }
        });

        swordButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Sword button clicked");
                playVideo(R.raw.sword);
            }
        });

        cloverButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Clover button clicked");
                playVideo(R.raw.clover);
            }
        });

        fuutoButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Fuuto button clicked");
                playVideo(R.raw.fuuto);
            }
        });

        return view;
    }

    @Override
    public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
        inflater.inflate(R.menu.menu_tab, menu);
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        if (item.getItemId() == R.id.tab_action) {
            Toast.makeText(getActivity(), "Clicked on " + item.getTitle(), Toast.LENGTH_SHORT)
                    .show();
        }
        return true;
    }
    private void playVideo(int videoResource) {
        String videoPath = "android.resource://" + getActivity().getPackageName() + "/" + videoResource;
        Intent intent = new Intent(getActivity(), VideoPlayerActivity.class);
        intent.putExtra("VIDEO_PATH", videoPath);
        startActivity(intent);
    }
}

```
- `ComedyFragment.java` :
```
package com.example.project_uas;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.Button;
import android.widget.Toast;

import androidx.fragment.app.Fragment;


public class ComedyFragment extends Fragment {

    private static final String TAG = "ComedyFragment";

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        // Inflate the layout for this fragment
        setHasOptionsMenu(true);
        View view = inflater.inflate(R.layout.fragment_comedy, container, false);

        // Find the button by its ID
        Button danshiButton = view.findViewById(R.id.danshi);
        Button gintamaButton = view.findViewById(R.id.gintama);
        Button grandButton = view.findViewById(R.id.grand);
        Button konosubaButton = view.findViewById(R.id.konosuba);
        Button saikiButton = view.findViewById(R.id.saiki);

        // Set click listener for each button
        danshiButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Danshi button clicked");
                playVideo(R.raw.danshi);
            }
        });

        gintamaButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Gintama button clicked");
                playVideo(R.raw.gintama);
            }
        });

        grandButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Grand button clicked");
                playVideo(R.raw.grand);
            }
        });

        konosubaButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Konosuba button clicked");
                playVideo(R.raw.konosuba);
            }
        });

        saikiButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Saiki button clicked");
                playVideo(R.raw.saiki);
            }
        });

        return view;
    }

    @Override
    public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
        inflater.inflate(R.menu.menu_tab, menu);
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        if (item.getItemId() == R.id.tab_comedy) {
            Toast.makeText(getActivity(), "Clicked on " + item.getTitle(), Toast.LENGTH_SHORT)
                    .show();
        }
        return true;
    }

    private void playVideo(int videoResource) {
        String videoPath = "android.resource://" + getActivity().getPackageName() + "/" + videoResource;
        Intent intent = new Intent(getActivity(), VideoPlayerActivity.class);
        intent.putExtra("VIDEO_PATH", videoPath);
        startActivity(intent);
    }
}

```

- `RomanceFragment.java` :
```
package com.example.project_uas;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.LayoutInflater;
import android.view.Menu;
import android.view.MenuInflater;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.Button;
import android.widget.Toast;

import androidx.fragment.app.Fragment;


public class RomanceFragment extends Fragment {

    private static final String TAG = "RomanceFragment";

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        // Inflate the layout for this fragment
        setHasOptionsMenu(true);
        View view = inflater.inflate(R.layout.fragment_romance, container, false);

        // Find the button by its ID
        Button dateButton = view.findViewById(R.id.date);
        Button goldenButton = view.findViewById(R.id.golden);
        Button gotoubunButton = view.findViewById(R.id.gotoubun);
        Button bokubenButton = view.findViewById(R.id.bokuben);
        Button oregairuButton = view.findViewById(R.id.oregairu);

        // Set click listener for each button
        dateButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Date button clicked");
                playVideo(R.raw.date);
            }
        });

        goldenButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Golden button clicked");
                playVideo(R.raw.golden);
            }
        });

        gotoubunButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Gotoubun button clicked");
                playVideo(R.raw.gotoubun);
            }
        });

        bokubenButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Bokuben button clicked");
                playVideo(R.raw.bokuben);
            }
        });

        oregairuButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Log.d(TAG, "Oregairu button clicked");
                playVideo(R.raw.oregairu);
            }
        });

        return view;
    }

    @Override
    public void onCreateOptionsMenu(Menu menu, MenuInflater inflater) {
        inflater.inflate(R.menu.menu_tab, menu);
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        if (item.getItemId() == R.id.tab_romance) {
            Toast.makeText(getActivity(), "Clicked on " + item.getTitle(), Toast.LENGTH_SHORT)
                    .show();
        }
        return true;
    }

    private void playVideo(int videoResource) {
        String videoPath = "android.resource://" + getActivity().getPackageName() + "/" + videoResource;
        Intent intent = new Intent(getActivity(), VideoPlayerActivity.class);
        intent.putExtra("VIDEO_PATH", videoPath);
        startActivity(intent);
    }
}

```

=> Lalu buat java class dengan nama `ViewAdapter.java`, yang berisi code :
```
package com.example.project_uas;

import androidx.annotation.NonNull;
import androidx.fragment.app.Fragment;
import androidx.fragment.app.FragmentActivity;
import androidx.viewpager2.adapter.FragmentStateAdapter;

public class ViewAdapter extends FragmentStateAdapter {
    public ViewAdapter(@NonNull FragmentActivity fragmentActivity) {
        super(fragmentActivity);
    }

    @NonNull
    @Override
    public Fragment createFragment(int position) {
        switch (position){
            case 0:
                return new ActionFragment();
            case 1:
                return new ComedyFragment();
            case 2:
                return new RomanceFragment();
            default:
                return new ActionFragment();
        }
    }

    @Override
    public int getItemCount() {
        return 3;
    }
}
```

=> Setelah itu membuat java class untuk memutar video dengan nama `VideoPlayerActivity.java`, yang berisi code :
```
package com.example.project_uas;

import android.content.pm.ActivityInfo;
import android.net.Uri;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.MediaController;
import android.widget.RelativeLayout;
import android.widget.VideoView;

import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;


public class VideoPlayerActivity extends AppCompatActivity {

    private VideoView videoView; // Deklarasi VideoView sebagai variabel global
    private int originalOrientation;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_video_player);

        // Get the video URI from the intent
        String videoPath = getIntent().getStringExtra("VIDEO_PATH");
        Uri uri = Uri.parse(videoPath);

        // Set up VideoView
        videoView = findViewById(R.id.videoView); // Inisialisasi variabel videoView
        videoView.setVideoURI(uri);

        // Set up MediaController
        MediaController mediaController = new MediaController(this);
        mediaController.setAnchorView(videoView);
        videoView.setMediaController(mediaController);

        // Start playing the video
        videoView.start();

        // Get the original orientation
        originalOrientation = getResources().getConfiguration().orientation;

        // Adjust video layout based on the original orientation
        adjustVideoLayout(originalOrientation);
    }

    @Override
    protected void onResume() {
        super.onResume();
        // Detect orientation changes and adjust VideoView layout
        int currentOrientation = getResources().getConfiguration().orientation;
        if (currentOrientation != originalOrientation) {
            adjustVideoLayout(currentOrientation);
            originalOrientation = currentOrientation;
        }
    }

    private void adjustVideoLayout(int orientation) {
        if (orientation == ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE ||
                orientation == ActivityInfo.SCREEN_ORIENTATION_REVERSE_LANDSCAPE) {
            // Landscape mode
            setFullscreen(true);
        } else {
            // Portrait or other orientations
            setFullscreen(false);
        }
    }

    private void setFullscreen(boolean fullscreen) {
        if (fullscreen) {
            // Hide action bar
            if (getSupportActionBar() != null) {
                getSupportActionBar().hide();
            }

            // Set VideoView layout parameters for fullscreen
            RelativeLayout.LayoutParams params = new RelativeLayout.LayoutParams(
                    ViewGroup.LayoutParams.MATCH_PARENT,
                    ViewGroup.LayoutParams.MATCH_PARENT
            );
            params.addRule(RelativeLayout.CENTER_IN_PARENT);
            videoView.setLayoutParams(params);

            // Hide navigation bar and status bar
            getWindow().getDecorView().setSystemUiVisibility(
                    View.SYSTEM_UI_FLAG_FULLSCREEN |
                            View.SYSTEM_UI_FLAG_HIDE_NAVIGATION |
                            View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY);
        } else {
            // Show action bar
            if (getSupportActionBar() != null) {
                getSupportActionBar().show();
            }

            // Set VideoView layout parameters for normal mode
            RelativeLayout.LayoutParams params = new RelativeLayout.LayoutParams(
                    ViewGroup.LayoutParams.MATCH_PARENT,
                    ViewGroup.LayoutParams.WRAP_CONTENT
            );
            params.addRule(RelativeLayout.CENTER_IN_PARENT);
            videoView.setLayoutParams(params);

            // Show navigation bar and status bar
            getWindow().getDecorView().setSystemUiVisibility(
                    View.SYSTEM_UI_FLAG_VISIBLE);
        }
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        getMenuInflater().inflate(R.menu.menu_video_player, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        if (item.getItemId() == R.id.action_back) {
            // Tambahkan logika untuk kembali ke halaman sebelumnya atau finish activity
            finish();
            return true;
        }
        return super.onOptionsItemSelected(item);
    }
}

```


> 4. ***res***

=> Pada bagian `Drawable` saya menambahkan *Drawable Resource File* dengan nama `bg_cardview.xml`, yang berisikan code :
```
<!-- cardview_pressed_effect.xml -->
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_pressed="true">
        <shape android:shape="rectangle">
            <!-- Ganti warna latar belakang yang diinginkan saat CardView ditekan -->
            <solid android:color="#F6F7F9" />
            <corners android:radius="20dp"/>
        </shape>
    </item>
    <item>
        <!-- Warna latar belakang default saat tidak ditekan -->
        <shape android:shape="rectangle">
            <solid android:color="#008BD7EE" />\

        </shape>
    </item>
</selector>
```

=> `values`

- `colors.xml` :
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="blue">#3700B3</color>
    <color name="pink">#FFC0CB</color>
    <color name="colorPrimary">#3F5185</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
    <color name="birumuda">#95AFD5</color>
    <color name="salem">#F8C6E6</color>
    <color name ="purple">#E3A2ED</color>
    <color name="hijau">#87986D</color>
    <color name="biru">#788A99</color>
    <color name="hijaumuda">#C2E69C</color>
    <color name="kuning">#FFEB3B</color>
    <color name="orange">#FF9800</color>
    <color name="cream">#E6C18A</color>
    <color name="hijautua">#3F4A2F</color>
    <color name="hijausoft">#9FC17C</color>
    <color name="coklat">#574545</color>
    <color name="choco">#A69E9E</color>
</resources>
```

=> `strings.xml` (tambahkan code strings.xml dibawah ini dengan code strings.xml pada project sebelumnya yaitu tugas 2) :
```
<resources>
 <string name="app_name">UAS</string>
    <!-- TODO: Remove or change this placeholder text -->
<string name="hello_blank_fragment">Hello blank fragment</string>
</resources>
```
=> `themes`

- `themes.xml` dan `themes.xml(night)` (sama isi code nya) :
```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="SplashScreen" parent="Theme.MaterialComponents.DayNight.NoActionBar">
        <item name="android:windowBackground">@drawable/splash</item>
        <item name="android:statusBarColor">?attr/colorOnPrimary</item>
    </style>

    <!-- Base application theme. -->
    <style name="Base.Theme.TabExperiment" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryVariant">@color/cream</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/hijau</item>
        <item name="colorSecondaryVariant">@color/hijaumuda</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor">@color/choco</item>
        <item name="android:navigationBarColor">@color/choco</item>
        <!-- Customize your light theme here. -->
    </style>

    <style name="Theme.TabExperiment" parent="Base.Theme.TabExperiment" />
</resources>
```

=> Untuk menambahkan video pada Android Studio disini saya memakai `res/raw/video_kita.mp4`, yaitu caranya yang pertama kita klik kanan terlebih dahulu di bagian `res` lalu kita pilih dan klik `new` lalu pilih dan klik bagian `Android Resource Directory`, setelah itu ada bagian    `Resource type` kita pilih `raw` lalu kita klik OK. Lalu setelah itu langsung saja kita copy paste video yang kita ingin masukkan ke dalam project kita ke dalam `raw`.

=> `layout`

=> Pada `activity_main.xml` saya melakukan penambahan dan perubahan code untuk design nya, yaitu isi code keseluruhannya adalah :
- `activity_main.xml` :
```
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/bg2"
    tools:context=".MainActivity">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <TextView
            android:id="@+id/title_view"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:text="Menu Program"
            android:fontFamily="serif"
            android:textColor="@color/white"
            android:textStyle="bold"
            android:textSize="35sp"
            android:layout_marginTop="35dp"/>

        <GridLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:layout_below="@+id/title_view"
            android:layout_marginStart="35dp"
            android:layout_marginTop="45dp"
            android:layout_marginEnd="40dp"
            android:layout_marginBottom="35dp"
            android:columnCount="10"
            android:rowCount="10">

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu1"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="0"
                android:layout_rowWeight="1"
                android:layout_column="0"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/hello" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="sans-serif"
                        android:text="HELLO WORLD!"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu2"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="0"
                android:layout_rowWeight="1"
                android:layout_column="1"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/math" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="FIBONACCI"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu3"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="1"
                android:layout_rowWeight="1"
                android:layout_column="0"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/scroll" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="SIANIDA"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu4"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="1"
                android:layout_rowWeight="1"
                android:layout_column="1"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/two" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="TWO ACTIVITY"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu5"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="2"
                android:layout_rowWeight="1"
                android:layout_column="0"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/alarm" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="ALARM"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu6"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="2"
                android:layout_rowWeight="1"
                android:layout_column="1"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/maps" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="G-MAPS"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu7"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="3"
                android:layout_rowWeight="1"
                android:layout_column="0"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/movie" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="MOVIES"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu8"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="3"
                android:layout_rowWeight="1"
                android:layout_column="1"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/splash2" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="EMPTY"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu9"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="4"
                android:layout_rowWeight="1"
                android:layout_column="0"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/splash2" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="EMPTY"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <androidx.cardview.widget.CardView
                android:id="@+id/cdMenu10"
                android:layout_width="80dp"
                android:layout_height="100dp"
                android:layout_row="4"
                android:layout_rowWeight="1"
                android:layout_column="1"
                android:layout_columnWeight="1"
                android:layout_gravity="fill"
                android:layout_margin="8dp"
                app:cardCornerRadius="8dp"
                app:cardElevation="8dp">

                <LinearLayout
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center_vertical|center_horizontal"
                    android:gravity="center"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:src="@drawable/splash2" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:fontFamily="serif"
                        android:text="EMPTY"
                        android:textAlignment="center"
                        android:textColor="@color/black"
                        android:textStyle="bold" />
                </LinearLayout>
            </androidx.cardview.widget.CardView>

        </GridLayout>

        <TextView
            android:id="@+id/bottom_text"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginBottom="35dp"
            android:layout_alignParentBottom="true"
            android:layout_centerHorizontal="true"
            android:fontFamily="monospace"
            android:text="© 2024 Dimas Aditya"
            android:textColor="@color/white"
            android:textSize="15sp"
            android:textStyle="italic" />

    </RelativeLayout>

</ScrollView>

```

- `activity_movie.xml` :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    tools:context=".FragmentActivity">


    <com.google.android.material.tabs.TabLayout
        android:id="@+id/tab"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/choco"
        app:tabSelectedTextColor="@color/white"
        app:tabIndicatorColor="@color/white"
        tools:layout_editor_absoluteX="1dp"
        tools:layout_editor_absoluteY="3dp"
        tools:ignore="MissingConstraints">

        <com.google.android.material.tabs.TabItem
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Action"
            tools:layout_editor_absoluteX="0dp"
            tools:layout_editor_absoluteY="3dp" />

        <com.google.android.material.tabs.TabItem
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Comedy" />

        <com.google.android.material.tabs.TabItem
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Romance" />
    </com.google.android.material.tabs.TabLayout>

    <androidx.viewpager2.widget.ViewPager2
        android:id="@+id/view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginTop="50dp"
        android:background="@color/white"
        tools:layout_editor_absoluteX="1dp"
        tools:layout_editor_absoluteY="52dp" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

- `activity_video_player.xml` :
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <VideoView
        android:id="@+id/videoView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</RelativeLayout>
```

- `fragment_action.xml` :
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    xmlns:tools="http://schemas.android.com/tools"
    android:padding="25dp"
    tools:context=".ActionFragment">
    
<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

 <LinearLayout
     android:layout_width="match_parent"
     android:layout_height="wrap_content"
     android:orientation="vertical">

    <ImageView
        android:id="@+id/imgMovie"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:src="@drawable/anime1" />

    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="331dp"
        android:layout_height="wrap_content"
        android:layout_marginHorizontal="100dp"
        android:layout_marginStart="20dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:text="Tensei shitara Slime Datta Ken Movie: Guren no Kizuna-hen"
        android:textColor="@color/black"
        android:textSize="18sp"
        android:textStyle="bold"/>

    <TextView
        android:id="@+id/Deskription"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Movie Tensei shitara Slime Datta Ken : Guren no Kizuna-hen atau That Time I Got Reincarnated as a Slime the Movie: Scarlet Bond bercerita Rimuru dan teman-temannya terlibat dalam konspirasi lama di negara baru bernama Razha terkait dengan seorang gadis yang memiliki kekuatan misterius. Rimuru dan Benimaru bertemu dengan ogre lain bernama Hiiro yang dulu sangat menghormati Benimaru."
        />


    <Button
        android:id="@+id/tensura"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/Deskription"
        android:text="Watch Trailer Here"
        android:onClick="playTensuraTrailer"/>


    <ImageView
        android:id="@+id/imgMovie2"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_marginTop="20dp"
        android:src="@drawable/anime2" />

    <TextView
        android:id="@+id/tvTitle2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_marginStart="16dp"
        android:layout_marginTop="20dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Boku no Hero Academia: World Heroes’ Mission"/>

    <TextView
        android:id="@+id/Deskription2"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Menceritakan tentang doktrin Teori Kiamat Bakat, kelompok ideologis Humarise yakin bahwa semua manusia yang memiliki bakat adalah penyakit dan harus dibasmi. Untuk membangun kembali dunia, kelompok ekstremis telah menciptakan perangkat mematikan yang dikenal sebagai “Bom Pemicu” yang menyebabkan orang-orang yang memikili bakat akan kehilangan kendali dan mati." />
    <Button
        android:id="@+id/bokunohero"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_below="@id/Deskription2"
        android:text="Watch Trailer Here"
        android:onClick="playBokunoheroTrailer"/>

    <ImageView
        android:id="@+id/imgMovie3"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_marginTop="20dp"
        android:src="@drawable/anime3" />

    <TextView
        android:id="@+id/tvTitle3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_marginStart="16dp"
        android:layout_marginTop="20dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Sword Art Online the Movie: Ordinal Scale"/>

    <TextView
        android:id="@+id/Deskription3"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Asuna, Lisbeth dan Silica mendorong Kirito untuk bermain OS setelah mendengar bahwa Aincrad boss telah muncul. Kirito bergabung Asuna dan Klein dalam pertarungan boss mana maskot game, pertama AI penyanyi idola Yuna, muncul dan memberikan pemain penyuka efek sambil bernyanyi. Kirito gagal untuk mencapai sesuatu karena kurangnya kekuatan fisik dan kecepatan. Eiji, nomor dua pemain, pembantu kelompok dalam mengalahkan boss. Sebelum Asuna membuat pukulan membunuh, Eiji berbisik kata “Switch,” montir permainan dari SAO bahwa dia mengakui."
        />

    <Button
        android:id="@+id/sword"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/Deskription3"
        android:text="Watch Trailer Here"
        android:onClick="playSwordTrailer" />

    <ImageView
        android:id="@+id/imgMovie4"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_marginTop="20dp"
        android:src="@drawable/anime4" />

    <TextView
        android:id="@+id/tvTitle4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_marginStart="16dp"
        android:layout_marginTop="20dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Black Clover: Mahou Tei no Ken"/>

    <TextView
        android:id="@+id/Deskription4"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Black Clover: Sword of the Wizard King atau Black Clover: Mahou Tei no Ken Ini adalah dunia di mana sihir adalah segalanya. Asta adalah anak laki-laki yang lahir tanpa bisa menggunakan sihir, telah bertarung melawan banyak musuh yang kuat bersama dengan rivalnya, Yuno. Keduanya berjuang untuk menjadi penyihir tinggi, “Kaisar Sihir”."
        />

    <Button
        android:id="@+id/clover"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie4"
        android:layout_below="@id/Deskription4"
        android:text="Watch Trailer Here"
        android:onClick="playCloverTrailer" />

    <ImageView
        android:id="@+id/imgMovie5"
        android:layout_width="match_parent"
        android:layout_height="170dp"
        android:layout_marginTop="20dp"
        android:src="@drawable/anime5" />

    <TextView
        android:id="@+id/tvTitle5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_marginStart="16dp"
        android:layout_marginTop="20dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Fuuto Tantei"/>

    <TextView
        android:id="@+id/Deskription5"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="5"
        android:textColor="@color/black"
        android:text="Detective Futo (Fuuto Tantei) atau Fuuto PI merupakan anime adaptasi manga serial Tokusatsu dengan judul yang sama. Manga sekaligus seri live action Kamen Rider W tersebut telah tayang pada tahun 2009 lalu."
        />

    <Button
        android:id="@+id/fuuto"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie5"
        android:layout_below="@id/Deskription5"
        android:text="Watch Trailer Here"
        android:onClick="playFuutoTrailer" />

 </LinearLayout>
</ScrollView>
</RelativeLayout>

```

- `fragment_comedy.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="25dp">

<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

  <LinearLayout
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:orientation="vertical">

      <ImageView
          android:id="@+id/imgMovie"
          android:layout_width="match_parent"
          android:layout_height="200dp"
          android:src="@drawable/anime6" />

    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Danshi Koukousei no Nichijou"/>

    <TextView
        android:id="@+id/Deskription"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Berkeliaran di aula SMA Sanada Utara yang khusus laki-laki adalah tiga kawan dekat: pemimpin eksentrik dengan imajinasi hiperaktif Hidenori, Yoshitake yang penuh gairah, dan Tadakuni yang rasional dan bijaksana. Kehidupan mereka dipenuhi dengan robot raksasa, cinta sejati, dan drama yang intens... setidaknya dalam imajinasi mereka yang penuh warna. Kenyataannya, mereka hanyalah trio pria biasa yang mencoba menghabiskan waktu, tapi siapa bilang kehidupan sehari-hari tidak menarik? Baik itu peragaan RPG yang rumit atau pertemuan romantis yang tak terduga di tepi sungai saat matahari terbenam, Danshi Koukousei no Nichijou penuh dengan situasi aneh namun lucu yang tidak biasa-biasa saja."
        />

    <Button
        android:id="@+id/danshi"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/Deskription"
        android:text="Watch Trailer Here"
        android:onClick="playDanshiTrailer"/>

      <ImageView
          android:id="@+id/imgMovie2"
          android:layout_width="match_parent"
          android:layout_height="200dp"
          android:layout_marginTop="20dp"
          android:src="@drawable/anime7" />

    <TextView
        android:id="@+id/tvTitle2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Gintama: The Final"/>

    <TextView
        android:id="@+id/Deskription2"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Dua tahun telah berlalu setelah invasi Tendoshuu ke Terminal Pusat O-Edo. Sejak itu, Yorozuya berpisah. Meramalkan kembalinya Utsuro, Gintoki Sakata mulai mengamati garis ley Bumi untuk mencari jejak Altana milik orang lain. Setelah bertemu dengan sisa-sisa Tendoshuu—yang terus mencari keabadian—Gintoki kembali ke Edo."
        />

    <Button
        android:id="@+id/gintama"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie2"
        android:layout_below="@id/Deskription2"
        android:text="Watch Trailer Here"
        android:onClick="playGintamaTrailer"/>

      <ImageView
          android:id="@+id/imgMovie3"
          android:layout_width="match_parent"
          android:layout_height="200dp"
          android:layout_marginTop="20dp"
          android:src="@drawable/anime8" />

    <TextView
        android:id="@+id/tvTitle3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Grand Blue"/>

    <TextView
        android:id="@+id/Deskription3"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Iori Kitahara pindah ke kota pesisir Izu untuk tahun pertamanya di universitas tersebut, dan bertempat tinggal di atas Grand Blue, toko selam scuba milik pamannya. Iori memiliki harapan dan impian yang tinggi untuk mendapatkan pengalaman kuliah yang ideal, tetapi ketika dia memasuki toko, dia tersedot ke dalam aktivitas alkoholik dari anggota Klub Selam yang riang dan sering mengunjungi tempat itu. Dibujuk oleh kakak kelas Shinji Tokita dan Ryuujirou Kotobuki, Iori dengan enggan bergabung dengan pesta aneh mereka. Sepupunya Chisa Kotegawa kemudian masuk dan memergokinya sedang beraksi, membuat Iori sangat meremehkannya."
        />

    <Button
        android:id="@+id/grand"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie3"
        android:layout_below="@id/Deskription3"
        android:text="Watch Trailer Here"
        android:onClick="playGrandTrailer"/>

      <ImageView
          android:id="@+id/imgMovie4"
          android:layout_width="match_parent"
          android:layout_height="200dp"
          android:layout_marginTop="20dp"
          android:src="@drawable/anime9" />

    <TextView
        android:id="@+id/tvTitle4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie4"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Kono Subarashii Sekai ni Shukufuku wo!"/>

    <TextView
        android:id="@+id/Deskription4"
        android:layout_toRightOf="@id/imgMovie4"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Setelah meninggal dalam kematian yang menggelikan dan menyedihkan dalam perjalanan kembali dari membeli permainan, siswa sekolah menengah dan pertapa Kazuma Satou menemukan dirinya duduk di hadapan dewi cantik namun menjengkelkan bernama Aqua. Dia memberi NEET dua pilihan: melanjutkan ke surga atau bereinkarnasi dalam impian setiap gamer—dunia fantasi nyata! Memilih untuk memulai hidup baru, Kazuma dengan cepat ditugaskan untuk mengalahkan Raja Iblis yang meneror desa. Tapi sebelum dia pergi, dia bisa memilih satu item apapun untuk membantunya dalam pencariannya, dan pahlawan masa depan memilih Aqua. Tapi Kazuma telah membuat kesalahan besar—Aqua sama sekali tidak berguna!"
        />

    <Button
        android:id="@+id/konosuba"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie4"
        android:layout_below="@id/Deskription4"
        android:text="Watch Trailer Here"
        android:onClick="playKonosubaTrailer"/>

      <ImageView
          android:id="@+id/imgMovie5"
          android:layout_width="match_parent"
          android:layout_height="200dp"
          android:layout_marginTop="20dp"
          android:src="@drawable/anime10" />

    <TextView
        android:id="@+id/tvTitle5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie5"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Saiki Kusuo no Ψ-nan"/>

    <TextView
        android:id="@+id/Deskription5"
        android:layout_toRightOf="@id/imgMovie5"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Bagi kebanyakan orang, kemampuan psikis mungkin tampak seperti sebuah berkah; namun bagi Kusuo Saiki, hal ini jauh dari kebenaran. Diberkahi dengan berbagai macam kemampuan supernatural mulai dari telepati hingga penglihatan x-ray, dia mendapati apa yang disebut sebagai berkah ini hanyalah sebuah kutukan. Karena semua ketidaknyamanan yang disebabkan oleh kekuatannya terus menumpuk, yang Kusuo inginkan hanyalah kehidupan biasa, tanpa kerumitan—kehidupan di mana ketidaktahuan adalah kebahagiaan."
        />

    <Button
        android:id="@+id/saiki"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie5"
        android:layout_below="@id/Deskription5"
        android:text="Watch Trailer Here"
        android:onClick="playSaikiTrailer"/>

  </LinearLayout>
</ScrollView>
</RelativeLayout>

```

- `fragment_romance.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="25dp">

<ScrollView
    android:layout_width="match_parent"
    android:layout_height="match_parent">

 <LinearLayout
     android:layout_width="match_parent"
     android:layout_height="wrap_content"
     android:orientation="vertical">

     <ImageView
         android:id="@+id/imgMovie"
         android:layout_width="match_parent"
         android:layout_height="200dp"
         android:src="@drawable/anime11" />

    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_toRightOf="@id/imgMovie"
        android:text="Date A Live Movie: Mayuri Judgment"
        android:textColor="@color/black"
        android:textSize="18sp"
        android:textStyle="bold"/>

    <TextView
        android:id="@+id/Deskription"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Perang(Kencan),dilanjutkan.Hari-hari damai Itsuka Shidou kembali tanpa harus menyelamatkan para Roh dari hari-hari pertempuran tanpa henti. Tapi, hari-hari damai itu terganggu oleh munculnya bola misterius yang memancarkan gelombang spiritual――serta seorang gadis misterius yang muncul di saat yang sama. Apa tujuannya mengawasi Shidou……? Misi yang dipercayakan kepada Shidou dalam situasi tegang adalah,“Berkencan dengan semua Roh, dan buat mereka jatuh cinta?!” Dengan nasib umat manusia yang dipertaruhkan, perang(kencan) berlanjut!"
        />

    <Button
        android:id="@+id/date"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/Deskription"
        android:text="Watch Trailer Here"
        android:onClick="playDateTrailer"/>

     <ImageView
         android:id="@+id/imgMovie2"
         android:layout_width="match_parent"
         android:layout_height="200dp"
         android:layout_marginTop="20dp"
         android:src="@drawable/anime12" />

    <TextView
        android:id="@+id/tvTitle2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Golden Time"/>

    <TextView
        android:id="@+id/Deskription2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/tvTitle"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="12dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:maxLines="15"
        android:textColor="@color/black"
        android:text="Akibat kecelakaan tragis, Banri Tada terkena amnesia, menghilangkan ingatan akan kampung halaman dan masa lalunya. Namun, setelah berteman dengan Mitsuo Yanagisawa, dia memutuskan untuk pindah dan memulai hidup baru di sekolah hukum di Tokyo. Namun ketika ia mulai menyesuaikan diri dengan kehidupan kampusnya, Kouko Kaga yang cantik secara dramatis menerobos kehidupan Banri, dan pertemuan mereka yang kebetulan menandai awal tahun yang tak terlupakan."
        />

    <Button
        android:id="@+id/golden"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/Deskription2"
        android:text="Watch Trailer Here"
        android:onClick="playGoldenTrailer"/>

     <ImageView
         android:id="@+id/imgMovie3"
         android:layout_width="match_parent"
         android:layout_height="200dp"
         android:layout_marginTop="20dp"
         android:src="@drawable/anime13" />

    <TextView
        android:id="@+id/tvTitle3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="5-toubun no Hanayome Movie"/>

    <TextView
        android:id="@+id/Deskription3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/tvTitle"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Fuutarou telah memimpin lima anak kembar lima hingga mereka bisa lulus dan mengejar impian mereka sendiri. Sekarang, akhirnya, mereka telah mencapai festival sekolah terakhir mereka. Setelah memutuskan untuk menjadikan peristiwa ini sebagai kenangan yang tak terlupakan, Fuutarou mencari perasaannya terhadap kelima kembar lima."
        />

    <Button
        android:id="@+id/gotoubun"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_below="@id/Deskription3"
        android:text="Watch Trailer Here"
        android:onClick="playGotoubunTrailer"/>

     <ImageView
         android:id="@+id/imgMovie4"
         android:layout_width="match_parent"
         android:layout_height="200dp"
         android:layout_marginTop="20dp"
         android:src="@drawable/anime14" />

    <TextView
        android:id="@+id/tvTitle4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Bokutachi wa Benkyou ga Dekinai"/>

    <TextView
        android:id="@+id/Deskription4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/tvTitle"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Nariyuki Yuiga, seorang siswa sekolah menengah tahun ketiga yang miskin, bekerja tanpa lelah untuk menerima nominasi VIP, sebuah beasiswa yang akan menutupi seluruh biaya kuliahnya. Sebagai pengakuan atas kerja kerasnya, Kepala Sekolah memberinya beasiswa terkenal."
        />

    <Button
        android:id="@+id/bokuben"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie4"
        android:layout_below="@id/Deskription4"
        android:text="Watch Trailer Here"
        android:onClick="playBokubenTrailer"/>

     <ImageView
         android:id="@+id/imgMovie5"
         android:layout_width="match_parent"
         android:layout_height="200dp"
         android:layout_marginTop="20dp"
         android:src="@drawable/anime15" />

    <TextView
        android:id="@+id/tvTitle5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/imgMovie"
        android:layout_marginStart="16dp"
        android:layout_marginTop="10dp"
        android:textSize="18sp"
        android:textStyle="bold"
        android:textColor="@color/black"
        android:text="Yahari Ore no Seishun Love Comedy wa Machigatteiru (Oregairu)"/>

    <TextView
        android:id="@+id/Deskription5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/tvTitle"
        android:layout_marginStart="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie"
        android:maxLines="10"
        android:textColor="@color/black"
        android:text="Hachiman Hikigaya adalah siswa SMA apatis dengan kecenderungan narsis dan semi nihilistik. Dia sangat percaya bahwa masa muda yang penuh kegembiraan hanyalah sebuah lelucon, dan siapa pun yang mengatakan sebaliknya hanyalah berbohong pada diri mereka sendiri."
        />

    <Button
        android:id="@+id/oregairu"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp"
        android:layout_toRightOf="@id/imgMovie5"
        android:layout_below="@id/Deskription5"
        android:text="Watch Trailer Here"
        android:onClick="playOregairuTrailer"/>

 </LinearLayout>
</ScrollView>
</RelativeLayout>

```
=> Pada directory `drawable` kita bisa tambahkan gambar seperti poster film yang ingin kita tampilkan, dan jangan lupa untuk menambahkan icon `baseline_more_vert_24.xml` dengan cara klik kanan pada `drawable` lalu klik New, setelah itu kita pilih dan klik Vector Asset. Setelah itu kita klik clip art lalu kita pilih icon nya, jika sudah ketemu kita klik OK lalu kita klik next. Sama halnya ketika kita ingin menambahkan menu kembali pada halaman `VideoPlayerActivity` yaitu dengan langkah-langkah yang sama seperti sebelumnya dan jangan lupa untuk menambahkan icon `baseline_arrorw_circle_left_24.xml` lalu klik OK dan kita klik next.

=> Selanjutnya kita klik kanan pada `res` lalu pilih dan klik `Android Resource Directory` setelah itu kita beri nama "menu" lalu klik OK. Setelah itu kita buat Menu Resource File dengan nama `menu_tab.xml` lalu isi dengan code :
```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
        android:id="@+id/tab_action"
        android:icon="@drawable/baseline_more_vert_24"
        android:title="Action"/>

    <item
        android:id="@+id/tab_comedy"
        android:icon="@drawable/baseline_more_vert_24"
        android:title="Comedy"/>

    <item
        android:id="@+id/tab_romance"
        android:icon="@drawable/baseline_more_vert_24"
        android:title="Romance"/>
</menu>
```

=> Sama halnya ketika ingin menambahkan code menu untuk kembali, dengan cara kita klik kanan pada directory `menu` dan buat Menu Resource File dengan nama `menu_video_player.xml` lalu isi dengan code :
```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/action_back"
        android:icon="@drawable/baseline_arrow_circle_left_24"
        android:title="Back"
        app:showAsAction="always" />
</menu>
```

> **Hasil Program Tugas:**

![Home](https://github.com/Doflamingo20/Project_UAS/assets/130146099/2eafdd05-0afb-45f9-bdf4-50c0b6427207)
![Action1](https://github.com/Doflamingo20/Project_UAS/assets/130146099/bd5fa1e5-203f-4706-b8e9-2040e75029cf)
![Action2](https://github.com/Doflamingo20/Project_UAS/assets/130146099/da8f81cc-3c7c-417e-8791-1ab4488a9fc3)
![Comedy1](https://github.com/Doflamingo20/Project_UAS/assets/130146099/40abb18f-84ad-4f4c-9602-d7bbfdf09fe2)
![Comedy2](https://github.com/Doflamingo20/Project_UAS/assets/130146099/6993ff80-7225-42a3-a994-853c560091de)
![Romance1](https://github.com/Doflamingo20/Project_UAS/assets/130146099/199facbd-2bff-45e1-8168-38a0fbb1d5c0)
![Romance2](https://github.com/Doflamingo20/Project_UAS/assets/130146099/140e6822-7d84-420c-9b19-c325a6de03b2)



## Demo Tugas



https://github.com/Doflamingo20/Project_UAS/assets/130146099/a669a6ab-d663-4fc2-89a7-69f8b494f4a9





## Semoga Bermanfaat, Terima Kasih 
