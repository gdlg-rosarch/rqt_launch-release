# Script generated with Bloom
pkgdesc="ROS - This rqt plugin ROS package provides easy view of .launch files. User can also start and end node by node that are defined in those files."
url='http://wiki.ros.org/rqt_launch'

pkgname='ros-lunar-rqt-launch'
pkgver='0.4.8_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-rqt-py-common'
)

depends=('ros-lunar-python-qt-binding>=0.2.19'
'ros-lunar-roslaunch'
'ros-lunar-rospy'
'ros-lunar-rqt-console'
'ros-lunar-rqt-gui'
'ros-lunar-rqt-gui-py'
'ros-lunar-rqt-py-common'
)

conflicts=()
replaces=()

_dir=rqt_launch
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_launch $srcdir/rqt_launch
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

