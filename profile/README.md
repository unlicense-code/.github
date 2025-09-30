## Node installer update

```sh
DIR=~/.local; SYSTEM=linux-x64; MIRROR=https://nodejs.org/dist; VERSION=$(curl -s $MIRROR/index.json | grep -m1 -o '"version":"v[0-9.]*"' | cut -d'"' -f4); curl -sL $MIRROR/$VERSION/node-$VERSION-$SYSTEM.tar.gz | tar -xvz --strip-components=1 -C $DIR --exclude='./*.md' --exclude='LICENSE'

VERSION=0.8.22 curl -L https://github.com/astral-sh/uv/releases/download/$VERSION/uv-x86_64-unknown-linux-gnu.tar.gz | tar --strip-components=1 -C ~/.local/bin -xzf -
```


## Big Update 
Microsoft now after more then a decade trys to do the right thing and turn monaco as also vscode into a edit able state!!!!

https://github.com/microsoft/vscode/issues/226260

This makes Microsoft less bad even if it took them millions of dollars that the open source community got solved in days. 

Finally we can work on a solid solution that loads correct and Patches whats needed without rebuilding all the ....... mess

- [ ] https://github.com/microsoft/vscode/issues/226260



## Hi there 👋
We make you more productive, by advising, empowering and teaching highly efficient software architectural fundamental concepts, 
that are tightly integrated with their existing tool chains. As also offer that under The Unlicense. So it is a fundamental part
of building unlicensed Software.

It bundels knowleg from Inovativ Companys and Open Source Projects into Fundamentals that will not break. To allow you to code software
with more confidence and a incremental upgrade path that always works. Get less often broken by changes from projects you depend on that
are not feature dependend like refactorings and other meta updates that are not realted to the code that you use.

## Quick

Latest nodejs in /usr/local and npx for the build
```
(MIRROR=https://nodejs.org/dist/latest; VERSION=; DIR=/usr/local; SYSTEM=linux-x64; curl -s -L ${MIRROR}${VERSION}/$(curl -s -L ${MIRROR}${VERSION} | grep 'tar.gz' | grep ${SYSTEM} | cut -d\" -f2) | tar -xvz --strip-components 1 -C ${DIR})
git clone https://github.com/microsoft/vscode
cd vscode
sed  -i '/npm_execpath/c\if (!process.env["npm_config_user_agent"].startsWith("yarn")) {' build/npm/preinstall.js
apt-get install -y libxkbfile-dev pkg-config libsecret-1-dev libkrb5-dev libxss1 dbus libgtk-3-0 libgbm1 
npx -p node@18.15 -p yarn -p node-gyp yarn
npx -p node@18.15 -p yarn -p node-gyp -p gulp yarn gulp vscode-web-min
```



## NPM Trick
creating the following file makes always your current directory the global prefix

~/etc/npmrc
```
prefix=
```

## How it all Starts?
```js
`https://github.com/oracle/graaljs/releases/download/vm-${version}/graaljs-${version}-${fileName}-amd64.${ext}`;
const filename = `${[macos,linux,windows].find(platform=>os.charCodeAt() === platform.charCodeAt())}-${[['arm','aarch64'], ['amd','amd64']].find(([contains,is])==>os.indexOf(contains))[1]}.${os.startsWith('win') ? 'zip' : 'tar.gz'}`;
// should adopt https://get.graalvm.org/jdk

```


```sh
## Install latest inside the current project
(MIRROR=https://nodejs.org/dist/latest; VERSION=-v19.x; DIR=.; SYSTEM=linux-x64; FILENAME=$(curl -s -L ${MIRROR}${VERSION} | grep 'tar.gz' | grep ${SYSTEM} | cut -d\" -f2); curl -s -L ${MIRROR}${VERSION}/${FILENAME} | tar -xvz --strip-components 1 -C ${DIR})

## but use a other nodejs version for the install
(PATH="./bin:$PATH"; npx -p node@16.4 -p yarn yarn install)

## shorter
(PATH="./bin:$PATH"; npx -p node@16.4 yarn install)

## True this will most time not run when you would execute it via node but your packaging for none nodejs usage 
## >This is the defacto way to do it
```

```ts
(MIRROR='https://nodejs.org/dist/latest'; VERSION='-v19.x'; DIR=.; SYSTEM='linux-x64'; FILENAME=${(await (await fetch(`${MIRROR}${VERSION}`)).text()).split('\n').find(line=>line.indexOf(SYSTEM) && line.indexOf('tar.gz')).split('"')[1]}; fetch(`${MIRROR}${VERSION}/${FILENAME}`).then(data=>data.body.pipeThrough(new DecompressionStream('gzip'))))
// TODO: No untar implemented.
```


when you get the below example working you can start using that output 
```
git clone github.com/microsoft/vscode
cd vscode
## the current version used comes from ./scripts/code-web.sh & code-server.sh 
## Error at the end can be fixed in ./build/gulpfile.js maybe
yarn add -D node 16.14.2
mkdir -p .build/node/v16.14.2
ln -s ../../../node_modules/node/bin .build/node/v16.14.2/linux-x64

## method one use patched yarn
PATH=$(pwd)/node_modules/node/bin:$PATH yarn compile-web
PATH=$(pwd)/node_modules/node/bin:$PATH ./scripts/code-web.sh

## use docker

```

the output is needed to build the next step the monaco-editor this did create monaco-editor-core

```
git clone github.com/microsoft/vscode
cd vscode
sudo docker run -it --rm -v $(pwd):/vscode -w /vscode -u $(id -u):$(id -u) node:16.14 yarn install 
sudo docker run -it --rm -v $(pwd):/vscode -w /vscode -u $(id -u):$(id -u) node:16.14 yarn run compile-web
sudo docker run -it --rm -v $(pwd):/vscode -w /vscode -u $(id -u):$(id -u) node:16.14 yarn add -D node@16.14
sudo docker run -it --rm -v $(pwd):/vscode -w /vscode -u $(id -u):$(id -u) node:16.14 yarn add -D node@16.14 ln -s ../../../node_modules/node/bin .build/node/v16.14.2/linux-x64
```


**Here are some ideas to get you started:**

- 🙋‍♀️ Main Offer The Unlicense Code Editor delivered as Devtools Extension.
- 🌈 Contribution guidelines - how can the community get involved?
Make a Pull Request see what happens.
- 👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
This is build on High Level Concepts to abstract the obvisios and keep the meaning full.
- 🍿 Fun facts - what does your team eat for breakfast?
I am on a diet.
- 🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

