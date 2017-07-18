# sdran
Software Defined Radio Related Work
Ref-URL: https://gitlab.eurecom.fr/oai/openairinterface5g/wikis/HowToConnectCOTSUEwithOAIeNB

#Compile
#
cd ~/openairinterface
source oaienv
cd cmake_targets
./build_oai -I -g --eNB -x --install-system-files -w USRP 

#Execute
#
cd ~/openairinterface5g
source oaienv
./cmake_targets/build_oai -w USRP -x -c --eNB
cd cmake_targets/lte_build_oai/build
sudo -E ./lte-softmodem -O $OPENAIR_DIR/targets/PROJECTS/GENERIC-LTE-EPC/CONF/enb.band7.tm1.usrpb210.conf -d
sudo -E ./lte-softmodem -h #(to see help options)

