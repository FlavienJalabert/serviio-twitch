Twitch implementation for Serviio v2.3

Install serviio using https://wiki.serviio.org/doku.php?id=howto:linux:install:ubuntu18-04
(works fine for me on ubuntu-server24 LTS)

Install custom ffmpeg build for serviio using this link https://wiki.serviio.org/doku.php?id=build_ffmpeg_linux
Be carefull to not install librtmp0 on ubuntu as it will not work or even damage important files
You will need to install nasm as well using sudo apt install nasm -y
It will be necessary for x254 latest at this link https://code.videolan.org/videolan/x264.git

During the build for FFMPEG please note that libfaac and x11grab are deprecated and that you'll need to install optional libraries beforehand and add the --enable-{optional-library-name} in the ./configure CLI

You will need then to recompile and rebuild x264 with newer FFMPEG configuration to enable compatibility
And then you can update serviio.sh to use the custom FFMPEG build by modifying the JAVA_OPTS line : -Dffmpeg.location=/home/username/src/ffmpeg/ffmpeg (change username to your actual username)

Now you can add the twitch.groovy file into the serviio/plugins folder and reboot your computer
