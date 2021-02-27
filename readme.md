# What The Flexbox?!

![](https://flexbox.io/images/WTF/share.png)

Exercises for the "What The Flexbox?!" video course. Videos available at <http://flexbox.io>

## Community What The Flexbox Content

Feel free to submit a PR adding a link to your own recaps, guides or reviews!

My [gh-page](https://herminiotorres.github.io/whattheflexbox) by [@herminiotorres](https://twitter.com/herminiotorres)

Notes on the Autoprefixer exercise:
You don't have to worry about using an autoprefixer with modern 2021 browsers but if you would like to follow along with Wes just for kicks, you just need a few changes to the `gulpfile.js` and your `package.json`.

**ES6** Syntax and newer **gulpjs** syntax for the `gulpfile.js`:
```
const gulp = require('gulp');
const autoprefixer = require('gulp-autoprefixer');

gulp.task('styles', () => {
  return gulp.src('css/styles.css')
  .pipe(autoprefixer())
  .pipe(gulp.dest('build'))
});

gulp.task('watch', () => {
  return gulp.watch(
    'css/styles.css',
    gulp.series('styles'));
});
```

To see the same thing Wes gets in his `build/styles.css` file, we need to target older browsers in the `package.json` using the `browserslist` key:
```
{
  "name": "autoprefixer",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "browserslist": [
    "< 0.2%"
  ],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "gulp": "^4.0.2",
    "gulp-autoprefixer": "^7.0.1"
  }
}
```
That's it, have fun!
