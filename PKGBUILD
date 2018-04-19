# Script generated with Bloom
pkgdesc="ROS - This package contains a class for converting from a 2D laser scan as defined by sensor_msgs/LaserScan into a point cloud as defined by sensor_msgs/PointCloud or sensor_msgs/PointCloud2. In particular, it contains functionality to account for the skew resulting from moving robots or tilting laser scanners."
url='http://ros.org/wiki/laser_geometry'

pkgname='ros-kinetic-laser-geometry'
pkgver='1.6.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'eigen3'
'ros-kinetic-angles'
'ros-kinetic-catkin>=0.5.68'
'ros-kinetic-cmake-modules'
'ros-kinetic-roscpp'
'ros-kinetic-rosunit'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

depends=('boost'
'eigen3'
'python2-numpy'
'ros-kinetic-angles'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=laser_geometry
source=()
md5sums=()

prepare() {
    cp -R $startdir/laser_geometry $srcdir/laser_geometry
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

