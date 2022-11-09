---
created: Sunday, October 30th 2022 - 24.42
updated: Sunday, October 30th 2022 - 24.42
---
### Static Methods
Within a JavaScript class, the static keyword defines a static method for a class. Static methods are not called on individual instances of the class, but are called on the class itself. Therefore, they tend to be general (utility) methods.
```js
class Dog {
  constructor(name) {
    this._name = name;  
  }
  
  // A static method
  static bark() {
    console.log('Woof!');  
  }
}
const myDog = new Dog('Buster');

// Calling the static method
Dog.bark();

// Calling from instances return error
// myDog.bark();
```

### Normal methods
```js
class Song {
  constructor(author) {
    this._author = author;
  }

  // A normal method
  play() {
    console.log('Song playing!');
  }
}
const mySong = new Song('Ahmad Dhani');

// Calling the normal method
mySong.play();
```

### Class Constructor
```js
class Song {
  constructor(title, artist) {
    this.title = title;
    this.artist = artist;
  }
}

const mySong = new Song('Bohemian Rhapsody', 'Queen');
console.log(mySong.title);
```

### Extends Class
Child classes have access to all of the instance properties and methods of the parent class. They can add their own properties and methods in addition to those. A child class constructor calls the parent class constructor using the `super()` method.
```js
// Parent class
class Media {
  constructor(info) {
    this.publishDate = info.publishDate;
    this.name = info.name;
  }
}

// Child class
class Song extends Media {
  constructor(songData) {
    super(songData);
    this.artist = songData.artist;
  }
}

const mySong = new Song({ 
  artist: 'Queen', 
  name: 'Bohemian Rhapsody', 
  publishDate: 1975
});
```