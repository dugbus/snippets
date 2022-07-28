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
```

### Simple Feed

```
let jsonData = JSON.parse(jobs);

const FEED_URL = `https://www.peoplebank.com/pb3/corporate/jksrestaurants/feed.php`;

let jobList = [];

fetch(FEED_URL)
  .then(response => response.json())
  .then(data => {

    data.sort((a, b) => (a.title.rendered > b.title.rendered) ? 1 : -1);

    console.log(data);

    let content = `<div class="headings"><div class="role">Role</div><div class="location">Location</div><div class="date">Date</div></div><div class="result"><div class="title">${data[0].title.rendered}</div><div class="location"><a href="${data[0].link}">${data[0].related_venue.title}</a>`;

    let currentTitle = data[0].title.rendered;

    for (let i = 1; i < data.length; i++) {
      if (data[i].title.rendered == currentTitle) {
        content = content + `<a href="${data[i].link}">${data[i].related_venue.title}</a>`;
      } else {
        content = content + `</div><div class="salary">${data[i].date}</div></div><div class="result"><div class="title">${data[i].title.rendered}</div><div class="location"><a href="${data[i].link}">${data[i].related_venue.title}</a>`;
        currentTitle = data[i].title.rendered;
      }
    }

    content = content + `</div><div class="salary">${data[data.length-1].date}</div></div>`;

    document.querySelector('#app').innerHTML = content;

  });
```
