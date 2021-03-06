# Lottie Bottom Navbar

A customisable bottom navigation bar with Lottie Animation

## Current Latest Version `1.0.8`


# Usage

### Add maven url Inside **Project Level build.gradle**
```bash
buildscript {
	...
    repositories {
    	...
        maven {
            url  "https://dl.bintray.com/subsub/maven"
        }
    }
    dependencies {
    	...
    }
}

...

allprojects {
    repositories {
    	...
        maven {
            url  "https://dl.bintray.com/subsub/maven"
        }
    }
}
```

### Add dependency into your app build.gradle
```bash
implementation "com.subkhansarif.libs:bottomnavbarlib:{latestVersion}"
```

# Sample

See sample project.

### Add LottieBottomNavbar to your layout
```xml
<com.subkhansarif.bottomnavbar.LottieBottomNavbar
        android:id="@+id/bottom_navbar"
        android:layout_width="0dp"
        android:layout_height="56dp"
        android:background="@color/colorWhite"
        android:elevation="15dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
```

### Setup menus for navbar
```java
ArrayList<BottomMenu> menu = ArrayList();
menu.add(new BottomMenu(0L, getString(R.string.lbl_menu_profile), R.drawable.ic_person_grey, "a_cup_of_coffee.json"));
menu.add(new BottomMenu(1L, getString(R.string.lbl_menu_pet), R.drawable.ic_pets_grey, "a_cup_of_coffee.json"));
menu.add(new BottomMenu(2L, getString(R.string.lbl_menu_Food), R.drawable.ic_restaurant_menu_grey, null));
```
BottomMenu constructor parameters:
- `id: Long`, id for your button
- `label: String`, label for this button. This will be shown below button icon
- `icon: drawable res`, image resource for this button
- `(optional) lottie_animation: String`, a String of json file name for Lottie Animation.

### Add menus to navbar
```java
LottieBottomNavbar bottom_navbar = findViewById(R.id.bottom_navbar)
bottom_navbar.setSelected(1)
bottom_navbar.setMenu(menu)
bottom_navbar.setMenuClickListener(this)
```