# Steps to clean install ffmpeg(neo)

## step 1
 sudo apt-get update -qq && sudo apt-get -y install \
  autoconf \
  automake \
  build-essential \
  cmake \
  git-core \
  libass-dev \
  libfreetype6-dev \
  libgnutls28-dev \
  libmp3lame-dev \
  libsdl2-dev \
  libtool \
  libva-dev \
  libvdpau-dev \
  libvorbis-dev \
  libxcb1-dev \
  libxcb-shm0-dev \
  libxcb-xfixes0-dev \
  meson \
  ninja-build \
  pkg-config \
  texinfo \
  wget \
  yasm \
  zlib1g-dev
  
  ## step 2
  sudo apt install libunistring-dev libaom-dev  (only for ubuntu 20 and above)
  
  ## prerequired installations:
  sudo apt-get install nasm
  sudo apt-get install libx264-dev
  sudo apt-get install libx265-dev libnuma-dev
  sudo apt-get install libvpx-dev
  sudo apt-get install libfdk-aac-dev
  sudo apt-get install libopus-dev
  
  ## step 3
  In home directory install ffmpeg build version
  run -----
  wget -O ffmpeg-snapshot.tar.bz2 https://ffmpeg.org/releases/ffmpeg-snapshot.tar.bz2 && \
  tar xjvf ffmpeg-snapshot.tar.bz2 && \
  cd ffmpeg && \
  
  NOW YOU"RE IN FFMPEG DIRECTORY(if not then proceed to ffmpeg directory)
   run --
   
   ./configure --prefix=/usr/local/ffmpeg --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-pthreads --enable-libmp3lame --enable-libtheora --enable-libx264 --enable-libxvid --enable-libvorbis --enable-gnutls  --enable-libaom --enable-libass  --enable-libfdk-aac --enable-libfreetype --enable-libopus --enable-libvpx --enable-libx265 
    
    sudo make 
    
    sudo make install
    
## configure the PATH param

echo "# Add FFMpeg bin & library paths:" >> ~/.bashrc

echo "export PATH=/usr/local/ffmpeg/bin:$PATH" >> ~/.bashrc

echo "export LD_LIBRARY_PATH=/usr/local/ffmpeg/lib:$LD_LIBRARY_PATH" >> ~/.bashrc

source ~/.bashrc

## Step 4
check where is ffmpeg is located, if its not in usr/local/bin then try to move ffmpeg to /usr/local/bin
eg:
In my case it was present in /usr/local/ffmpeg/bin/ffmpeg . so i've moved this file to /usr/local/bin to make it executable

 sudo mv /usr/local/ffmpeg/bin/ffmpeg /usr/local/bin
 
 same do this for ffprobe and ffplay which is present in ffmpeg build directory ...move them to /usr/local/bin
 eg:
 
 sudo mv /"pathtoffmpeg"/ffprobe /usr/local/bin
 
 sudo mv /"pathtoffmpeg"/ffplay /usr/local/bin
 
 ## QT-faststart
 
 cd ffmpeg
 make
 make test
 make tools/qt-faststart
 cp -a tools/qt-faststart /usr/local/bin
 
 
 
 DONE!!
 

    
  
  
  
