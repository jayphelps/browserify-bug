# browserify-bug

First confirm everything works as a regular npm-installed module

```
git clone https://github.com/jayphelps/browserify-bug.git
cd browserify-bug
npm install
npm start
# no errors
```

Now `npm link anti-use-strict-mock` and try it again

```
cd ..
npm install anti-use-strict-mock
cd anti-use-strict-mock
npm link
cd ../browserify-bug
npm link anti-use-strict-mock
npm start
# Now it should error with "TypeError: Cannot set property 'foo' of undefined"
# If you examine output.js you'll see the module was transformed differently
# and a "use strict" added at the top.
```