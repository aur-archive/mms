# Contributor: Arturo <arturuk at gmail dot com>

pkgname=mms
pkgver=1.1.0
pkgrel=2291
pkgdesc="My Media System is an application that manages, displays and plays media content such as videos, music, pictures, and more. This package is geared towards vdr users"
arch=('i686' 'x86_64')
url="http://mymediasystem.org/"
license=('GPL')
groups=(multimedia)
depends=('xine-lib' 'lirc-utils' 'sqlite3' 'imlib2' 'boost' 'commoncpp2' 'taglib' 'libxfixes' 'mesa')
makedepends=('gcc' 'autoconf')
install=mms.install
backup=(
	'etc/mms/PictureConfig'
	'etc/mms/WeatherConfig'
	'etc/mms/RemoteConfig'
	'etc/mms/MplayerConfig'
	'etc/mms/TVConfig'
	'etc/mms/AlsaplayerConfig'
	'etc/mms/Config'
	'etc/mms/GenericPlayerConfig'
	'etc/mms/EPGConfig'
	'etc/mms/PythonConfig'
	'etc/mms/ClockAlarms'
	'etc/mms/AudioConfig'
	'etc/mms/input/lirc/vbox'
	'etc/mms/RadioConfig'
	'etc/mms/EvdevConfig'
	'etc/mms/LcdConfig'
	'etc/mms/OpenglConfig'
	'etc/mms/GameConfig'
	'etc/mms/XineConfig'
	'etc/mms/MovieConfig'
	'etc/mms/ClockConfig'
	'etc/mms/genericplayer.ops'
	'etc/mms/LircConfig'
	'etc/mms/input/lirc/audio_extend'
	'etc/mms/input/lirc/epg'
	'etc/mms/input/lirc/movie'
	'etc/mms/input/lirc/alarm'
	'etc/mms/input/lirc/python'
	'etc/mms/input/lirc/playlist'
	'etc/mms/input/lirc/default'
	'etc/mms/input/lirc/audio'
	'etc/mms/input/lirc/pictures'
	'etc/mms/input/lirc/search'
	'etc/mms/input/evdev/default'
	'etc/mms/input/keyboard/vbox'
	'etc/mms/input/keyboard/audio_extend'
	'etc/mms/input/keyboard/epg'
	'etc/mms/input/keyboard/movie'
	'etc/mms/input/keyboard/alarm'
	'etc/mms/input/keyboard/python'
	'etc/mms/input/keyboard/playlist'
	'etc/mms/input/keyboard/default'
	'etc/mms/input/keyboard/audio'
	'etc/mms/input/keyboard/pictures'
	'etc/mms/input/keyboard/search'
)
source=(http://mms.mymediasystem.net/mms110/nightly-snapshot/$pkgname-$pkgver-$pkgrel.tgz
        game_lower.patch
			         tv_top.patch)

md5sums=('787c8bf0634bbb5a18871c09d7c0ec0f'
         '969aa9f528b025aef48e3b0c5216f165'
         'a62bd4803ee6a36c60ae2edab782d8c3')


build() {
  cd $srcdir/$pkgname-$pkgver-$pkgrel
 patch -p0 -i $srcdir/game_lower.patch || return 1
 patch -p0 -i $srcdir/tv_top.patch || return 1
./configure --prefix=/usr --enable-opengl --disable-audio --enable-game --disable-fancy-game --disable-fancy-movie --disable-ffmpeg-thumb --disable-epg --enable-clock --enable-tv --enable-lirc --enable-notify-area --disable-inotify  
  make || return
  make DESTDIR=$pkgdir install || return 1
}

