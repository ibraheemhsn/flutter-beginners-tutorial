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

## Lesson 8 Images and Assets

here 
```
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
        child: Image.asset('assets/space-3.jpg'),
        // or NetworkImage('URL'),
      ),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Colors.red[600],
        child: Text('click'),
      ),
    );
  }
}
```

## Lesson 9 Buttons & Icons
us the following widgets : `RaisedButton`, `RaisedButton.icon`, `FlatButton`, or `Icon`, 
use onPressed with above widgets `onPressed: () {//code here;},`

```
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
        child: IconButton(
          onPressed: () {
            print('you clicked me');
          },
          icon: Icon(Icons.alternate_email),
          color: Colors.amber,
        ),
      ),
      floatingActionButton: FloatingActionButton(
        backgroundColor: Colors.red[600],
        child: Text('click'),
      ),
    );
  }
}

// snippets for icons and buttons

//  Icon(
//    Icons.airport_shuttle,
//    color: Colors.lightBlue,
//    size: 50.0
//  ),

//  RaisedButton(
//    onPressed: () {
//      print('you clicked me');
//    },
//    child: Text('click me'),
//    color: Colors.lightBlue,
//  ),

//  FlatButton(
//    onPressed: () {},
//    child: Text('click me again'),
//    color: Colors.amber
//  ),

//  RaisedButton.icon(
//    onPressed: () {},
//    icon: Icon(Icons.mail),
//    label: Text('mail me'),
//    color: Colors.amber,
//  ),
```

## Lesson 10 Containers & Padding
use `EdgeInsets` for `padding` and `margin`
```
 body: Padding(
        padding: EdgeInsets.all(20.0), // or use EdgeInsets.fromLTRB(x,x,x,x),
        child: Text('hello, again')
      ),
```
## Lesson 11 Rows
Row has array of children widgets inside : like this `children : <Widget>[//list of widgts here ]`

```
body: Row(
        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
        crossAxisAlignment: CrossAxisAlignment.end,
        children: <Widget>[
          Text('hello, world'),
          FlatButton(
            onPressed: () {},
            color: Colors.amber,
            child: Text('click me'),
          ),
          Container(
            color: Colors.cyan,
            padding: EdgeInsets.all(30.0),
            child: Text('inside container')
          ),
        ],
        ),
```
  
for MainAxisAlignment and CrossAxisAlignment 
![Image of alignment](https://miro.medium.com/max/700/0*nZsgn53lmVES-h1H)



## Lessson 12 Columns
exactly the same rows
```
body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        crossAxisAlignment: CrossAxisAlignment.start,
        children: <Widget>[
          Container(
            padding: EdgeInsets.all(20.0),
            color: Colors.cyan,
            child: Text('one'),
          ),
          Container(
            padding: EdgeInsets.all(30.0),
            color: Colors.pinkAccent,
            child: Text('two'),
          ),
          Container(
            padding: EdgeInsets.all(40.0),
            color: Colors.amber,
            child: Text('three'),
          ),
        ],
      ),
  ```
## Lesson 13 Flutter Outline & Shortcuts
no code here
## Lesson 14 Expanded
Expanded will be expand to take all area avliable for him.
use `flex:number` default =1 , just like CSS.
```
body: Row(
        children: <Widget>[
          Expanded(child: Image.asset('assets/space-2.jpg')),
          Expanded(
            flex: 3,
            child: Container(
              padding: EdgeInsets.all(30.0),
              color: Colors.cyan,
              child: Text('1'),
            ),
          ),
          Expanded(
            flex: 2,
            child: Container(
              padding: EdgeInsets.all(30.0),
              color: Colors.pinkAccent,
              child: Text('2'),
            ),
          ),
          Expanded(
            flex: 1,
            child: Container(
              padding: EdgeInsets.all(30.0),
              color: Colors.amber,
              child: Text('3'),
            ),
          ),
        ],
      ),
```

## Lesson 15 Ninja ID Project
full code :
```
import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(
  home: NinjaCard(),
));

class NinjaCard extends StatefulWidget {
  @override
  _NinjaCardState createState() => _NinjaCardState();
}

class _NinjaCardState extends State<NinjaCard> {

  int ninjaLevel = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.grey[900],
      appBar: AppBar(
        title: Text('Ninja ID Card'),
        centerTitle: true,
        backgroundColor: Colors.grey[850],
        elevation: 0.0,
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          setState(() {
            ninjaLevel += 1;
          });
        },
        backgroundColor: Colors.grey[800],
        child: Icon(Icons.add),
      ),
      body: Padding(
        padding: const EdgeInsets.fromLTRB(30.0, 40.0, 30.0, 0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: <Widget>[
            Center(
              child: CircleAvatar(
                radius: 40.0,
                backgroundImage: AssetImage('assets/thumb.jpg'),
              ),
            ),
            Divider(
              color: Colors.grey[800],
              height: 60.0,
            ),
            Text(
              'NAME',
              style: TextStyle(
                color: Colors.grey,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 10.0),
            Text(
              'Chun-Li',
              style: TextStyle(
                color: Colors.amberAccent[200],
                fontWeight: FontWeight.bold,
                fontSize: 28.0,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 30.0),
            Text(
              'HOMETOWN',
              style: TextStyle(
                color: Colors.grey,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 10.0),
            Text(
              'Beijing, China',
              style: TextStyle(
                color: Colors.amberAccent[200],
                fontWeight: FontWeight.bold,
                fontSize: 28.0,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 30.0),
            Text(
              'CURRENT NINJA LEVEL',
              style: TextStyle(
                color: Colors.grey,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 10.0),
            Text(
              '$ninjaLevel',
              style: TextStyle(
                color: Colors.amberAccent[200],
                fontWeight: FontWeight.bold,
                fontSize: 28.0,
                letterSpacing: 2.0,
              ),
            ),
            SizedBox(height: 30.0),
            Row(
              children: <Widget>[
                Icon(
                  Icons.email,
                  color: Colors.grey[400],
                ),
                SizedBox(width: 10.0),
                Text(
                  'chun.li@thenetninja.co.uk',
                  style: TextStyle(
                    color: Colors.grey[400],
                    fontSize: 18.0,
                    letterSpacing: 1.0,
                  ),
                )
              ],
            ),
          ],
        ),
      ),
    );
  }
}
```

- using 
``setState(() {
            variable += 1;
          });
``
- using `SizedBox()` to make space between widgts. 
- uising `Divider()` widget.
- use shortcut `stful` in editor to write Statefull widget.
- in summary the statefull widget written in 2 classes like this:
```
class NinjaCard extends StatefulWidget {
  @override
  _NinjaCardState createState() => _NinjaCardState();
}

class _NinjaCardState extends State<NinjaCard> {
  // note any class with _ before his name then he class is private for this .dart file and can no be accessed from outside the file.
  int varibale = 0;
  int varibale2 = 3;
  
  @override
  Widget build(BuildContext context) {
  // here we override build function
  return Scaffold (
  // here the UI);
  }
  } //end of class
```

## Lesson 16 Staefull widget
- use shortcode `stful`
- statefull widget includes 2 classes, firt for widget and second for state, you define data in second class, the build method is in second class and get called everytime the state updated.
- to disaply varibale inside string use $ sign
`` text : Text("my age is $age")``

## Lesson 17 Lists of data
- 1 to define list of quotes of type String ( inside state class )
``
List<String> quotes = ['item1','item2','item3'];
``
- 2 to cycle though this list of strings inside columns, use `map` function which is defined in list object
```
Column(
children : quotes.map(...function here...).toList(),
)
```
- 3 what is inside ...function here.... it is function with one parameter called quote :
```
(quote){
return Text(quote);
}
```
- 4 you can use lambda expression instead of block function
```
// (){return x}
// () => x
```

## Lesson 18 Custom Classes
- using named parameters 
```
//normal parameters. have to be sent in same sequence
myMethod(int x, String y)
myMethod (xx, yy)

//named parameters, optional and have to be sent with name
myMethod({int x, @required String y, int z})
myMethod (y:yy, x: xx)
```
- we can create class for quotes for hold data. quote includes text and author

```
class Quote {

  String text;
  String author;

  //  normal constructor, as we've already seen

  //  Quote(String author, String text){
  //    this.text = text;
  //    this.author = author;
  //  }

  //  constructor with named parameters

  //  Quote({ String author, String text }){
  //    this.text = text;
  //    this.author = author;
  //  }

  // constructor with named parameters
  // & automatically assigns named arguments to class properties

  Quote({ this.text, this.author });

}
```
- we call instansitate the class object using the constructure with named parameters. here we created List "quotes" which is of type <Quote>, so each item in the list is quote object.
```
List<Quote> quotes = [
    Quote(author: 'Oscar Wilde', text: 'Be yourself; everyone else is already taken'),
    Quote(author: 'Oscar Wilde', text: 'I have nothing to declare except my genius'),
    Quote(author: 'Oscar Wilde', text: 'The truth is rarely pure and never simple')
  ];
```
- to display the quote inside Text, call their parameters with $ sign
```
  Text('${quote.text} - ${quote.author}')
```

## Lesson 19 cards
  
Youtube link here
https://www.youtube.com/watch?v=XIxahpXU_QE

- 1. create widget named quoteTemplate inside state class. with one parameter "quote"
```
Widget quoteTemplate(quote) {
    return Card(
      margin: const EdgeInsets.fromLTRB(16.0, 16.0, 16.0, 0),
      child: Padding(
        padding: const EdgeInsets.all(12.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: <Widget>[
            Text(
              quote.text,
              style: TextStyle(
                fontSize: 18.0,
                color: Colors.grey[600],
              ),
            ),
            SizedBox(height: 6.0),
            Text(
              quote.author,
              style: TextStyle(
                fontSize: 14.0,
                color: Colors.grey[800],
              ),
            ),
          ],
        ),
      )
    );
  }
```
- 2. call this widget inside build function.
```
children: quotes.map((quote) => quoteTemplate(quote)).toList(),
```

## Lesson 20 Extracting Widgets
- move the Widget to class in separate file, extends StatelessWidget, define parameter and consructure. override build method. call this object from anywhere. (from Android studio click on Extract Widget, this will create the class)
  
```
  class QuoteCard extends StatelessWidget {

  final Quote quote;
  QuoteCard({ this.quote });

  @override
  Widget build(BuildContext context) {
    return Card( 
  // widget tree for card here 
  )
  }
  }
