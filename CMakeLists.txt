#  mrosconf: MikroTik RouterOS(TM) Configuration Downloader
#  Copyright (C) 2020  Niels Penneman
#
#  This file is part of mrosconf.
#
#  mrosconf is free software: you can redistribute it and/or modify it under the
#  terms of the GNU Affero General Public License as published by the Free
#  Software Foundation, either version 3 of the License, or (at your option) any
#  later version.
#
#  mrosconf is distributed in the hope that it will be useful, but WITHOUT ANY
#  WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR
#  A PARTICULAR PURPOSE. See the GNU Affero General Public License for more
#  details.
#
#  You should have received a copy of the GNU Affero General Public License
#  along with mrosconf. If not, see <https://www.gnu.org/licenses/>.
#
#  Mikrotik and RouterOS are trademarks of Mikrotikls SIA.


cmake_minimum_required (VERSION 3.7.2 FATAL_ERROR)

project (mrosconf)


set (SRC_DIR "${PROJECT_SOURCE_DIR}/src")


install (PROGRAMS ${SRC_DIR}/mrosconf DESTINATION bin)


set (CPACK_GENERATOR "DEB")
set (CPACK_DEBIAN_PACKAGE_DEPENDS "bash, openssh-client")
set (CPACK_DEBIAN_PACKAGE_MAINTAINER "Niels Penneman")
set (CPACK_PACKAGE_VERSION_MAJOR 0)
set (CPACK_PACKAGE_VERSION_MINOR 9)
set (CPACK_PACKAGE_VERSION_PATCH 1)
set (CPACK_DEBIAN_PACKAGE_RELEASE 1)

include (CPack)
