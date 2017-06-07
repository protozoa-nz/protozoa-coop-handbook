# Sbot on Android

## My phone
Samsung galaxy s5 cyanogen mod 13.0. 

## Linux Deploy

- Install [Linux deploy](https://play.google.com/store/apps/details?id=ru.meefik.linuxdeploy)
  - Note: needs rooted android device. I've played with other alternatives like debkit etc but they use PRoot. PRoot simulates root access but we need ACTUAL root access.

### Configure linux deploy
Some defaults need changing. This is just what I did, your mileage may vary.

Change distribution to ubuntu.
Change the image size to something bigger than default (I went 5000mb)
Tick the ssh box so that ubuntu has a ssh server.
Then install (takes 10 minutes)
Run

### Connect
`ssh android@<ip in app title bar>` 

Password is found under the menu in the bottom right of the screen.

Install build tools:

`sudo apt-get install build-essential python python2.7 curl`

Install nvm:

`curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash`
`bash`
`nvm install --lts` (could use more modern node probably)
`npm i -g npm@latest`
`npm i -g node-gyp`
`npm i -g scuttlebot` (takes 15mins)

## Gossip!
`sbot server`

## Grow the fs:
I ran out of diskspace and had to grow the image:
Grow the image by 1GB (make sure image isn't running)
```
adb shell
su root
cd <image-dir>
dd if=/dev/zero of=linux.img count=1 bs=1GB
e2fsck -f -y linux.img
```

## Run a client:
I got [patchlite](https://github.com/ssbc/patchlite) running ok. It was a bit slow, possibly from the js crypto libs being slower than native.

## Issues and where to from here
- My sbot is crashing with bad block errors. This might be because the resize didn't work properly.
- Hooking up sbot to run on image boot.
- Try out running the built sbot in a proot image so we don't need actual root.
- Investigate publishing prebuilt versions of the crypto libs.
- Look at moving the sync js crypto to async to free up the ui.
  - could use webworkers
  - could work on doing it in the native layer.
- Measure battery / cpu use. (important for making solar powered pub)
- Investigate sbot api to see if it's easy to switch gossip / on and off to save power and bandwidth. 
  - Sbot bandwidth counter and limiting will be needed for mobile.
- Make a chroot dev environment that runs (half done but breaks coz no /dev directory)

