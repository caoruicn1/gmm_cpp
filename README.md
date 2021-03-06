# gmm_cpp

Gaussian mixture model implementation in C++ with black box variational inference and control variates

This is heavily based on the deep exponential families repo, a beautiful piece of software: https://github.com/blei-lab/deep-exponential-families

## Requirements
On a mac:
```
# install developer tools
xcode-select --install
# install libraries
brew install gcc --without-multilib
brew install gsl
brew install homebrew/science/armadillo
brew install boost
```

For developing C++ on a Mac with waf as your build system, you need to be careful with your `wscript` waf configuration.

If you have installed libraries with homebrew, they are installed in `/usr/local/include` by default, whereas waf only searches for library headers in `/usr/include` by default. To fix this, you need to add `conf.env.INCLUDES_MYLIB = ['/usr/local/include']` to the waf configuration to be able to use libraries installed using homebrew.

On ubuntu: see my docker file [here](https://github.com/altosaar/dotfiles/blob/master/.docker/Dockerfile).

# Running

```
./waf configure
./waf build
./build/my_main
```

This runs black box variational inference to fit a gaussian mixture model to toy data.
