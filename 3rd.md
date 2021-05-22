genrsa -out BDU.key 4096
req -new -x509 -days 365 -key BDU.key -out BDU.crt

genrsa -out poly.key 4096
req -new -key poly.key -out poly.csr
x509 -req -days 365 -in poly.csr -CA BDU.crt -CAkey BDU.key -set_serial 01 -out poly.crt

genrsa -out Electrical.key 4096
req -new -key Electrical.key -out Electrical.csr
x509 -req -days 365 -in Electrical.csr -CA poly.crt -CAkey poly.key -set_serial 01 -out Electrical.crt

genrsa -out elec_user.key 4096
req -new -key elec_user.key -out elec_user.csr
x509 -req -days 365 -in elec_user.csr -CA Electrical.crt -CAkey Electrical.key -set_serial 01 -out elec_user.crt

genrsa -out Mechanical.key 4096
req -new -key Mechanical.key -out Mechanical.csr
x509 -req -days 365 -in Mechanical.csr -CA poly.crt -CAkey poly.key -set_serial 01 -out Mechanical.crt

genrsa -out mec_user.key 4096
req -new -key mec_user.key -out mec_user.csr
x509 -req -days 365 -in mec_user.csr -CA Mechanical.crt -CAkey Mechanical.key -set_serial 01 -out mec_user.crt

genrsa -out Chemical.key 4096
req -new -key Chemical.key -out Chemical.csr
x509 -req -days 365 -in Chemical.csr -CA poly.crt -CAkey poly.key -set_serial 01 -out Chemical.crt

genrsa -out chem_user.key 4096
req -new -key chem_user.key -out chem_user.csr
x509 -req -days 365 -in chem_user.csr -CA Chemical.crt -CAkey Chemical.key -set_serial 01 -out chem_user.crt

genrsa -out Civil.key 4096
req -new -key Civil.key -out Civil.csr
x509 -req -days 365 -in Civil.csr -CA poly.crt -CAkey poly.key -set_serial 01 -out Civil.crt

genrsa -out civil_user.key 4096
req -new -key civil_user.key -out civil_user.csr
x509 -req -days 365 -in civil_user.csr -CA Civil.crt -CAkey Civil.key -set_serial 01 -out civil_user.crt

genrsa -out cotm_user.key 4096
req -new -key cotm_user.key -out cotm_user.csr
x509 -req -days 365 -in cotm_user.csr -CA Civil.crt -CAkey Civil.key -set_serial 01 -out cotm_user.crt

genrsa -out Computing.key 4096
req -new -key Computing.key -out Computing.csr
x509 -req -days 365 -in Computing.csr -CA poly.crt -CAkey poly.key -set_serial 01 -out Computing.crt

genrsa -out comput_user.key 4096
req -new -key comput_user.key -out comput_user.csr
x509 -req -days 365 -in comput_user.csr -CA Computing.crt -CAkey Computing.key -set_serial 01 -out comput_user.crt
-----------------------------------------------------------------------------------------------------------------------------
genrsa -out peda.key 4096
req -new -key peda.key -out peda.csr
x509 -req -days 365 -in peda.csr -CA BDU.crt -CAkey BDU.key -set_serial 01 -out peda.crt

genrsa -out Medicine.key 4096
req -new -key medicine.key -out Medicine.csr
x509 -req -days 365 -in Medicine.csr -CA peda.crt -CAkey peda.key -set_serial 01 -out Medicine.crt

genrsa -out medi_user.key 4096
req -new -key medi_user.key -out medi_user.csr
x509 -req -days 365 -in medi_user.csr -CA Medicine.crt -CAkey Medicine.key -set_serial 01 -out medi_user.crt

genrsa -out Social.key 4096
req -new -key Social.key -out Social.csr
x509 -req -days 365 -in Social.csr -CA peda.crt -CAkey peda.key -set_serial 01 -out Social.crt

genrsa -out amha_user.key 4096
req -new -key amha_user.key -out amha_user.csr
x509 -req -days 365 -in amha_user.csr -CA Social.crt -CAkey Social.key -set_serial 01 -out amha_user.crt

genrsa -out antro_user.key 4096
req -new -key antro_user.key -out antro_user.csr
x509 -req -days 365 -in antro_user.csr -CA Social.crt -CAkey Social.key -set_serial 01 -out antro_user.crt

genrsa -out Bueco.key 4096 
req -new -key Bueco.key -out Bueco.csr
x509 -req -days 365 -in Bueco.csr -CA peda.crt -CAkey peda.key -set_serial 01 -out Bueco.crt

genrsa -out eco_user.key 4096
req -new -key eco_user.key -out eco_user.csr
x509 -req -days 365 -in eco_user.csr -CA Bueco.crt -CAkey Bueco.key -set_serial 01 -out eco_user.crt

genrsa -out mgt_user.key 4096
req -new -key mgt_user.key -out mgt_user.csr
x509 -req -days 365 -in mgt_user.csr -CA Bueco.crt -CAkey Bueco.key -set_serial 01 -out mgt_user.crt
------------------------------------------------------------------------------------------------------------
genrsa -out Zenzelma.key 4096
req -new -key Zenzelma.key -out Zenzelma.csr
x509 -req -days 365 -in Zenzelma.csr -CA BDU.crt -CAkey BDU.key -set_serial 01 -out Zenzelma.crt

genrsa -out Agriculture.key 4096
req -new -key Agriculture.key -out Agriculture.csr 
x509 -req -days 365 -in Agriculture.csr -CA Zenzelma.crt -CAkey Zenzelma.key -set_serial 01 -out Agriculture.crt

genrsa -out plant_user.key 4096
req -new -key plant_user.key -out plant_user.csr
x509 -req -days 365 -in plant_user.csr -CA Agriculture.crt -CAkey Agriculture.key -set_serial 01 -out plant_user.crt

genrsa -out animal_user.key 4096
req -new -key animal_user.key -out animal_user.csr
x509 -req -days 365 -in animal_user.csr -CA Agriculture.crt -CAkey Agriculture.key -set_serial 01 -out animal_user.crt
------------------------------------------------------------------------------------------------------------------------------------------------
genrsa -out Yibab.key 4096
req -new -key Yibab.key -out Yibab.csr
x509 -req -days 365 -in Yibab.csr -CA BDU.crt -CAkey BDU.key -set_serial 01 -out Yibab.crt

genrsa -out Law.key 4096
req -new -key Law.key -out Law.csr 
x509 -req -days 365 -in Law.csr -CA Yibab.crt -CAkey Yibab.key -set_serial 01 -out Law.crt

genrsa -out law_user.key 4096
req -new -key law_user.key -out law_user.csr
x509 -req -days 365 -in law_user.csr -CA Law.crt -CAkey Law.key -set_serial 01 -out law_user.crt

genrsa -out Archla.key 4096
req -new -key Archla.key -out Archla.csr
x509 -req -days 365 -in Archla.csr -CA Yibab.crt -CAkey Yibab.key -set_serial 01 -out Archla.crt 

genrsa -out arch_user.key 4096
req -new -key arch_user.key -out arch_user.csr
x509 -req -days 365 -in arch_user.csr -CA Archla.crt -CAkey Archla.key -set_serial 01 -out arch_user.crt

genrsa -out land_user.key 4096
req -new -key land_user.key -out land_user.csr
x509 -req -days 365 -in land_user.csr -CA Archla.crt -CAkey Archla.key -set_serial 01 -out land_user.crt


