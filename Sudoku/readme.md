MReeks_COMP225
==============

This is a finished version of the Sudoku app from the "Hello, Android" book. I have successfully integrated music, animations, and save games, and have added a digital clock and options to the main menu.

General Program Structure
---------------------------
The app consists of two main activities, a menu and the Sudoku game itself. The menu provides options for starting a new game or continuing an old one, adjusting the music, and learning about Sudoku. Additionally, I've added a clock here for convenience, with a second counter to keep more precise measurements of the time spent to complete puzzles. The menu screen is created in the main activity within the onCreate() method: 
super.onCreate(savedInstanceState);
      setContentView(R.layout.main);

      View continueButton = findViewById(R.id.continue_button);
      continueButton.setOnClickListener(this);
      View newButton = findViewById(R.id.new_button);
      newButton.setOnClickListener(this);
      View aboutButton = findViewById(R.id.about_button);
      aboutButton.setOnClickListener(this);
      View exitButton = findViewById(R.id.exit_button);
      exitButton.setOnClickListener(this);
      
      DigitalClock dc = (DigitalClock) findViewById(R.id.digitalClock1);
   }
 This section of code initializes the four buttons and refers to the layout file for the menu, R.layout.main. In this main layout file, the background color and text for the buttons is identified by referring to values within the /res/values/strings.xml and /res/values/colors.xml files. The individual events for clicking each button are defined separately in the Sudoku file, after which further action is carried out in Game.java to create a puzzle, draw it, and handle the input to the game. 
 
 The game has a built-in hints system: if a square has only one valid choice for a number, it is highlighted in bright green; if there are multiple valid choices, it is highlighted in light green; and if there are no possible valid choices to place in that square, it is highlighted in red. This allows the game to proceed smoothly even if hints are required. Future work could seek to identify better choices for certain squares, in order to avoid impossible positions; however, this would require a subroutine to solve the puzzle, which would add a good deal of complexity to the app. With that capability, adding the hints would be a simple matter of adding colors to the /res/values/colors.xml file, and applying this style to squares when appropriate.
 

Clock Object
---------------------------
The game has an analog clock on the front screen displaying the current system time (though other times could easily be given to it). The clock is a widget built into Android. In order to use it, I initialized an AnalogClock object:
AnalogClock ac = (AnalogClock) findViewById(R.id.analogClock1);
This references a view in the R file, which requires that I create a corresponding style in the /res/layout/main file. I additionally added layout specifications for a digital clock to the layout-land/main.xml, so that there is a fitting clock on that view. Both of these required rearrangement of the layout file to allow a comfortable fit; the whole experience has given me more experience with editing the Android interface than I had expected. However, I succeeded in getting both clocks to fit and function properly, so the experience was worthwhile. 

Other explored elements
---------------------------
I continued exploring aspects of the interface, changing all of the default colors to values I found more visually pleasing. I also changed the style of the buttons slightly so that they faded against the background, creating a less jarring effect. However, this was less effective than I hoped. I would like to continue exploring this avenue and discovering better methods of designing attractive interfaces, as I find this aspect of Android most exciting. 

Overall, this app is simple, but demonstrates most of what I have learned about Android since the beginning of the semester. I created working activities with functional buttons, a working savegame feature, a semi-attractive interface, and several options. Additionally, I learned to implement chronometers (omitted because of layout concerns) and clock objects of different types, and to link these into the layout of the app. I'd like to implement a button to switch between analog and digital clocks in either landscape or normal layout. 
