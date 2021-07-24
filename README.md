# Installing and configuring NS3 and NetAnim Simulator in Ubuntu

copy all commands line by line 
and paste it in terminal
make sure you are in home (~)
to verify type 
```
pwd
```
It shuld look like this

```
/home/<username>
```

if not type

```
cd
```
and press enter

## Update system
	
```
sudo apt update && sudo apt upgrade 
```
Enter password when prompted

press ```y``` and press enter when prompted.

## List of Packages for Installing ns-3 in Ubantu Systems
These packages are required to run the NS3 and Netanimator
Refermain documentation for step by step insrtructions with explanation
https://www.nsnam.org/wiki/Installation

### Option 1
copy the fillowing and paste it in terminal, it will install all required packages in a single command

```
sudo apt install g++ python3 python3-dev pkg-config sqlite3 qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools qt5-default mercurial gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 gdb valgrind  doxygen graphviz imagemagick texlive texlive-extra-utils texlive-latex-extra texlive-font-utils dvipng latexmk python3-sphinx dia tcpdump sqlite sqlite3 libsqlite3-dev
  ```
Generally it will install all the requied packages in a single command. It may take a little time depending upon the internet connection.

### Option 2
In case of any error in option 1, try intalling each packages step by step (as per official documenttion)


```
sudo apt install g++ python3 python3-dev pkg-config sqlite3 
  ```
  ```
sudo apt install qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools
  ```
  ```
sudo apt-get install qt5-default mercurial
  ```
  ```
sudo apt install gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 
  ```
  ```
sudo apt install gdb valgrind 
  ```
  ```
sudo apt install doxygen graphviz imagemagick
  ```
  ```
sudo apt install texlive texlive-extra-utils texlive-latex-extra texlive-font-utils dvipng latexmk
  ```
  ```
sudo apt install python3-sphinx dia 
  ```
  ```
sudo apt install tcpdump
  ```
  ```
sudo apt install sqlite sqlite3 libsqlite3-dev
  ```
  ```
sudo apt install libgtk-3-dev
  ```
Now, all the dependencies should be ready and we can proceed with ns3 and NetaAnim installation. 

## Configure directory
```
mkdir workspace
cd workspace
```

## Download NS3 all in one (I am using latest version here)

### make sure wget is installed
run following command, if already installaed it will print  ``` wget is already the newest version (1.20.3-1ubuntu1).

```
sudo apt install wget
``` 
if not installed it will start installing wget

#### Download ns3 tar 

```
wget https://www.nsnam.org/releases/ns-allinone-3.33.tar.bz2
```

#### Unzipping tarball
```
tar -xf ns-allinone-3.33.tar.bz2 
```

### Compiling ns-3
	
  ```
cd ns-allinone-3.33 

./build.py --enable-examples --enable-tests
```
```
cd ns-3.33
  
./test.py
 ```

## Configuring NS 3 



```
./waf -d debug --enable-examples --enable-test configure
```

### Running first example
```
cd examples/tutorial/ 

cp first.cc ../../scratch/

cd ../..

./waf --run scratch/first
```

### running second example

```
cp examples/tutorial/second.cc scratch/
./waf --run scratch/second
```

## NetAnim3 installation -- GUI

#### verifying prerequisite 
	sudo apt install mercurial qt5-default
#### Download and configure NetAnim
	cd
	cd workspace/ns-allinone-3.33
	cd cd netanim-3.108/
	make clean
	qmake NetAnim.pro
	make

#### Verifying and starting NetAnim
	./NetAnim

## Installing Wirshark 

```
sudo apt install wireshark
```
