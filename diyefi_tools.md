### Setting up tools on mac 10.8.2

1. update xcode in app store
2. installed command line tools using preferences
```bash
sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer
```
3. download from [sourceforge - Fink](http://sourceforge.net/projects/fink/)
4. 
```bash
tar -xvf fink-0.34.7.tar.gz
cd fink-0.34.7
./bootstrap
``` 
5. 
```bash
vi /sw/etc/fink.conf
```
replaced this line:
```
Trees: local/main stable/main unstable/main unstable/crypto
```
5. Configure fink with mainly defaults, increased verbosity
```bash
/sw/bin/pathsetup.sh
```
4. Reload Bash.  I do think by opening a new tab in iTerm, some people use the following
```bash
source ~/.bash_profile
```
6.
```bash
sudo sh -c 'curl http://tools.diyefi.org/FreeEMS-ToolChain-MacOSX-Fink.zip > /sw/fink/dists/local/main/finkinfo/FreeEMS-ToolChain-MacOSX-Fink.zip'
cd /sw/fink/dists/local/main/finkinfo
sudo unzip /sw/fink/dists/local/main/finkinfoFreeEMS-ToolChain-MacOSX-Fink.zip -d /sw/fink/dists/local/main/finkinfo
fink selfupdate
fink selfupdate-rsync
fink index -f
fink scanpackages
fink install mc9xgate-binutils m68hc1x-newlib m68hc1x-binutils m68hc1x-gcc
fink install make
```
7. Now what?