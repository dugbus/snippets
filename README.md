# Snippets

Collecting bits and pieces in one place

## HTML

### Protect target blank from mischief

```
<a href="https://hacks.mozilla.org/2022/04/mdn-plus-now-available-in-more-markets" target="_blank" rel="noopener noreferrer">Learn more</a>
```

### Datalist

```
<label for="exampleDataList" class="form-label">Datalist example</label>
<input class="form-control" list="datalistOptions" id="exampleDataList" placeholder="Type to search...">
<datalist id="datalistOptions">
  <option value="San Francisco">
  <option value="New York">
  <option value="Seattle">
  <option value="Los Angeles">
  <option value="Chicago">
</datalist>
```

## CSS

### Debug
```
* {
  background: rgba(0 100 0 / 0.05);
  outline: 1px solid limegreen;
}
```

### Sticky Footer

```
html {
  height: 100%;
}

body {
  height: 100%;
}

footer {
  position: sticky;
  top: 100%;
}
```

### Container Without Inner Div

```
.content {
  padding: var(--gap) max(var(--edge), calc(50% - var(--width-xl)/2));
}
```


### Autogrid

```
.results {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(var(--card-width), 1fr));
    gap: var(--gap);
    max-width: var(--max-width);
    padding: 0 var(--edge);
    margin: 0 auto;
}
```

### Breakpoints

688px - 992px - 1312px

## JavaScript

### Console Log

```
console.log("(◡‿◡)")
```

const person = {name: 'Joe', age: 30. pets: ['cat','fish','dog']}

//old faithful
console.log(person)

//nicely formats objects
console.dir(person)

//displays message if the assertion fails
console.assert(person.pets.find(pet => pet === 'hamster'), 'Person does not own a hamster')

//increment a counter
person.pets.forEach(pet => console.count('Pets'))

//pretty table
console.table(person)

//start a timer, log the progress, show total elapsed
console.time() / timeLog() / timeEnd()

//
console.trace()

//group messages to avoid spamming the console
console.group()
console.groupCollapsed()

//styling
console.log('%c I am a logging master', 'font-weight: bold; background-color: cyan; color: navy; padding: 15px')

//specific styling
console.log(
  'CSS can make %cyour console logs%c %cawesome%c!',  // String to format
  // Each string is the CSS to apply for each consecutive %c
  'color: #fff; background: #1e90ff; padding: 4px',   // Apply styles
  '',                                                 // Clear any styles
  'color: #f00; font-weight: bold',                   // Apply styles
  ''                                                  // Clear any styles
);


// {x: 1, y: 2, z: 3}
console.log({x, y, z});

//threat levels
console.debug('Debug message');
console.info('Useful information');
console.warn('This is a warning');
console.error('Something went wrong!');
