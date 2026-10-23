# ANSWERS - IGFU3_ACA-AC_JASON

## 1. GitHub repository
https://github.com/jase-jason22/flutter_basics_lab

## 2. Activity 2: last three build() lines
build() called: 4 glasses
build() called: 5 glasses
build() called: 6 glasses

## 3. Observations

*Activity 2 (moved _glasses++ outside setState):*
I removed setState from _addGlass and pressed the + button. The displayed number remained at 0, and no new "build() called" message appeared in the Debug Console. This showed that the variable was updating in memory, but Flutter was not notified to rebuild the UI. When I pressed the - button, which still used setState, the screen updated and displayed the correct value. After testing, I restored the original code.

*Activity 3 (removed Expanded from a StatBox):*
I removed Expanded from the Humidity box. It became smaller and only occupied the space needed by its content, while the other boxes expanded to fill the remaining space. When I resized the window, the Humidity box maintained its width, while the other boxes adjusted. After observing the changes, I added Expanded back.

*Activity 5 (changed buildTheme):*
I modified the corner radius of the ElevatedButton from 8 to 20 in buildTheme(). This made the Elevated button more rounded. However, the Outlined and Save buttons remained unchanged because the theme modification only applied to ElevatedButton.

## 4. Review questions

1. A StatelessWidget stays the same after it is displayed, while a StatefulWidget can store changing data and update the screen when needed. ProfileCard uses StatelessWidget, while WaterTrackerPage uses StatefulWidget.

2. The widget class is immutable and is responsible for creating the State object. The State class stores the changing data, such as _glasses, and contains the build() method. This allows the data to remain even when the widget is recreated.

3. When I modified _glasses outside setState(), the screen did not change and build() was not called. The value updated in memory, but Flutter was not notified to refresh the UI.

4. The build() method runs when the widget first appears and whenever setState() is called. For example, it runs again when I tap the +, -, or Reset button.

5. In a Row, the main axis goes horizontally, while the cross axis goes vertically. In a Column, the main axis goes vertically, and the cross axis goes horizontally.

6. After removing Expanded, the Humidity box became smaller and only used the space needed for its content. Expanded allows a widget to occupy the available space along the main axis and share it with other Expanded widgets.

7. GridView.builder creates items only when they are needed and visible, making it efficient for displaying many items. It also supports scrolling and automatically organizes the grid. In contrast, a Column creates all its children at once and does not provide scrolling by itself.

8. A Stack allows widgets to overlap each other. The card content serves as the background, while Positioned places the Best seller badge in the corner using its top and left values. The if (item.bestSeller) condition ensures that the badge appears only on items marked as best sellers.

9. ThemeData allows me to apply styles throughout the application from one place, such as configuring elevatedButtonTheme in buildTheme(), which sets the shape and padding of every ElevatedButton. Meanwhile, styling a specific widget affects only that widget. For example, the CircleAvatar inside the ListTile has its own backgroundColor and foregroundColor, which apply only to that avatar.

10. _ThemeDemoAppState manages the _isDark variable. When the switch is toggled, it calls onDarkChanged, which triggers _setDark. The method uses setState() to update the state, causing the app to rebuild and pass the updated themeMode to MaterialApp.