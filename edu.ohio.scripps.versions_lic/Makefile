#
#   Copyright 2011 Ricky Chilcott <chilcotr@ohio.edu>
#
#   Licensed under the Apache License, Version 2.0 (the "License");
#   you may not use this file except in compliance with the License.
#       You may obtain a copy of the License at
#
#       http://www.apache.org/licenses/LICENSE-2.0
#
#   Unless required by applicable law or agreed to in writing, software
#   distributed under the License is distributed on an "AS IS" BASIS,
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#   See the License for the specific language governing permissions and
#   limitations under the License.
#
# 
#  Luggage makefile for installing Scripps College Versions Licenses

include /usr/local/share/luggage/luggage.make

TITLE=edu.ohio.scripps.versions_licenser
REVERSE_DOMAIN=edu.ohio.scripps
PAYLOAD=pack-Library-Management_versions_licenser-edu.ohio.scripps.versions_licenser-boot.sh\
		pack-Library-Management_versions_licenser-$(wildcard *.lic)\
		pack-Library-LaunchDaemons-edu.ohio.scripps.versions_licenser-boot.plist
PACKAGE_VERSION=1.2

# Create /Library/Management
l_Library_Management: l_Library
	@sudo mkdir -p ${WORK_D}/Library/Management
	@sudo chown root:wheel ${WORK_D}/Library/Management
	@sudo chmod 755 ${WORK_D}/Library/Management

# Create /Library/Management/versions_licenser
l_Library_Management_versions_licenser: l_Library_Management
	@sudo mkdir -p ${WORK_D}/Library/Management/versions_licenser
	@sudo chown root:wheel ${WORK_D}/Library/Management/versions_licenser
	@sudo chmod 755 ${WORK_D}/Library/Management/versions_licenser

# Install at /Library/Management/versions_licenser
pack-Library-Management_versions_licenser-%: % l_Library_Management_versions_licenser
	@sudo ${INSTALL} -m 644 -g wheel -o root $< ${WORK_D}/Library/Management/versions_licenser
	
# Install wildcard at /Library/Management/versions_licenser
pack-Library-Management_versions_licenser-%: % l_Library_Management_versions_licenser
	@sudo ${INSTALL} -m 644 -g wheel -o root $< ${WORK_D}/Library/Management/versions_licenser
	
