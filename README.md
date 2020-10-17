# flutter-beginners-tutorial
All course files for the Flutter Beginners playlist on The Net Ninja YouTube channel.

## How to use these files
Each lesson in the playlist has it's own branch in this repository. To see the code for that lesson, choose the appropriate branch. E.g. to see the code for lesson 15, checkout the lesson-15 branch.

**important** - if you are cloning the repo to your desktop, you will need to perform a packages get / pub get to install any dependencies that the project may have at that point of the course.

**Link to playlist on YouTube**
https://www.youtube.com/watch?v=1ukSR1GRtMU&list=PL4cUxeGkcC9jLYyp2Aoh6hcWuxFDX6PBJ

**Mastering Markdown** 
https://guides.github.com/features/mastering-markdown/

## Lesson 4


## Lesson 5

````
void main() => runApp(MaterialApp(
  home: Scaffold(
    appBar: AppBar(
      title: Text('my first app'),
      centerTitle: true,
    ),
    body: Center(
      child: Text('hello, ninjas!'),
    ),
    floatingActionButton: FloatingActionButton(
      child: Text('click'),
    ),
  ),
));
````
where `Scaffold` is .....

## Lesson 6 Colours & Fonts

setting up the fonts
1. download ttf file from internet
2. insert ttf file inside `fonts` folder
3. update `pubspec.yaml` with font name and file name like this :
```
  fonts:
    - family: Raleway
      fonts:
        - asset: fonts/Raleway-Regular.ttf
        - asset: fonts/Raleway-Italic.ttf
          style: italic
    - family: RobotoMono
      fonts:
        - asset: fonts/RobotoMono-Regular.ttf
        - asset: fonts/RobotoMono-Bold.ttf
          weight: 700
```     

4. cmd `pubget`
5. refer to font `fontFamily: 'IndieFlower'`.

```
body: Center(
      child: Text(
        'hello, ninjas!',
        style: TextStyle(
          fontSize: 20.0,
          fontWeight: FontWeight.bold,
          letterSpacing: 2.0,
          color: Colors.grey[600],
          fontFamily: 'IndieFlower',
        ),
      ),
    ),
```

## Lesson 7 Stateless and Statefull

```
void main() => runApp(MaterialApp(
  home: Home(),
));

class Home extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
          title: Text('my first app'),
          centerTitle: true,
          backgroundColor: Colors.red[600]
      ),
      body: Center(
        child: Text(
          'hello again, ninjas!',
          style: TextStyle(
            fontSize: 20.0,
            fontWeight: FontWeight.bold,
            letterSpacing: 2.0,
            color: Colors.grey[600],
            fontFamily: 'IndieFlower',
          ),
        ),
      ),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Colors.red[600],
        child: Text('click'),
      ),
    );
  }
}

```

