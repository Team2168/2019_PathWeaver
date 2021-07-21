# 2019_PathWeaver
a copy of the 2019 pathweaver code base, revised to include local maven deps which are no longer available on the web

Original source from [PathWeaver, v2019.2.1](https://github.com/wpilibsuite/PathWeaver/releases/tag/v2019.2.1)


## Updating the field images

* Add a new picture (jpg) of the field below `src\main\resources\edu\wpi\first\pathweaver`
* Add a new json file below `src\main\resources\edu\wpi\first\pathweaver`

  like the following:
  ```
  {
    "game": "2021 Skills Challenge",
    "field-image": "2021-skills.jpg",
    "field-corners": {
      "top-left": [248, 76],
      "bottom-right": [1935, 922]
    },
    "field-size": [30, 15],
    "field-unit": "feet"
  }
  ```

  Where:

  * `game` is the name of the game that will show up when selecting the game
    type when creating new PathWeaver projects
  * `field-image` is the name of the image that depicts the field
  * the `field-corners` are the x,y pixel coordinate positions that define
    the edges of the playable area within the image
  * the `field-size` is the width and height of the field in `field-unit`'s

* Edit `src\main\java\edu\wpi\first\pathweaver\Game.java`, creating a new
  instance of a `Game` object referencing the json file you created.
  e.g.:

  ```java
  public static final Game SKILLS_2021 = loadGameFromResource("2021-skills.json");
  ```


## Building the project

From a terminal:

* Run pathweaver:
  ```sh
  ./gradlew.bat run
  ```

* Build the project:
  ```sh
  ./gradlew.bat build
  ```

  Distributable zip & tar files will be created below the following directory:
  `\build\distributions`

  You can run the project by launching the `bin/pathweaver.bat` file within the
  archive. If it doesn't work, you likely need to address a problem with your
  Java Runtime either not being the right version, or not being in your Path
  variable. Run the bat file in a command prompt to see any error messages
  produced.


# Original PathWeaver Readme

Everything below is from the upstream project's readme file

<hr>

[![Build Status](https://dev.azure.com/wpilib/DesktopTools/_apis/build/status/wpilibsuite.PathWeaver)](https://dev.azure.com/wpilib/DesktopTools/_build/latest?definitionId=10)
# PathWeaver

PathWeaver is a front end motion planning program. It is primarily designed for FRC teams using [Pathfinder](https://github.com/JacisNonsense/Pathfinder). For more instructions on using PathWeaver, refer to the [WPILib instructions](https://wpilib.screenstepslive.com/s/currentCS/m/84338).

## Commenting
For bugs or feature suggestions, make a github issue.

## Building

To run PathWeaver use the command `./gradlew run`


### Requirements
- [JDK 11](http://jdk.java.net/11/)
