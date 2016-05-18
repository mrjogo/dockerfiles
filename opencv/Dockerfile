# xhost + && docker run --rm -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY --device /dev/video0:/dev/video0 mrjogo/opencv && xhost -
FROM ubuntu:16.04
MAINTAINER Ruddick Lawrence <mrjogo@gmail.com>

# Install dependencies to build OpenCV
RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y \
  wget \
  unzip \
  build-essential \
  cmake \
  pkg-config \
  libjpeg-dev \
  libtiff-dev \
  libjasper-dev \
  libpng-dev \
  libgtk2.0-dev \
  libavcodec-dev \
  libavformat-dev \
  libswscale-dev \
  libv4l-dev \
  python-dev \
  python-numpy \
  libtbb2 \
  libtbb-dev \
  libdc1394-22-dev \
  libavutil-dev \
  v4l-utils \
  libcanberra-gtk-module \
  && rm -rf /var/lib/apt/lists/*

# Build OpenCV with opencv_contrib
WORKDIR /root
# Note: use single RUN command to prevent caching of source
RUN wget 'https://github.com/Itseez/opencv/archive/3.1.0.zip' -O opencv-3.1.0.zip \
  && unzip opencv-3.1.0.zip \
  && wget 'https://github.com/Itseez/opencv_contrib/archive/3.1.0.zip' -O opencv_contrib-3.1.0.zip \
  && unzip opencv_contrib-3.1.0.zip \
  && mkdir -p opencv-3.1.0/release \
  && cd opencv-3.1.0/release \
  && cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-3.1.0/modules .. \
  && make \
  && make install \
  && cd ../.. \
  && rm -rf opencv-3.1.0* \
  && rm -rf opencv_contrib-3.1.0*

CMD ["bash"]
