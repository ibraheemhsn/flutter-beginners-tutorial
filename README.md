# Youtube link here
https://www.youtube.com/watch?v=XIxahpXU_QE

## Cards

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

