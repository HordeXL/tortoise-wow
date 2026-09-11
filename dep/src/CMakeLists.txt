#
# Copyright (C) 2005-2011 MaNGOS project <http://getmangos.com/>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
#

if (MINGW)
    add_subdirectory(libseh)
endif()
add_subdirectory(g3dlite)
if(WIN32)
    add_subdirectory(zlib)
    # gsoap runtime linked from source on Windows: the checked-in
    # libgsoap++.a under dep/lib/gsoap is a Linux archive (ELF objects) that
    # MSVC's linker cannot read. The vendored stdsoap2.cpp carries the same
    # 2.8.135 runtime the archive was built from.
    add_subdirectory(gsoap)
endif()