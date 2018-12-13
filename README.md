# TCC
### # ##  **INFRASTRUCTURE AS CODE**

**IaC - CFEngine Portal**</br>
Infrastructure as Code adalah proses penyediaan IT infrastruktur dimana sistem dibangun dan dikelola melalui kode secara automasi (otomatis), bukan secara manual. Atau bisa disebut juga bahasa kerennya Programmable Infrastructure.
Dengan menggunakan kode dan meng-automasi, proses setting dan konfigurasi baremetal, virtual mesin, cloud computing baik itu instalasi baru, perubahan konfigurasi dapat dilakukan secara cepat, mudah, dan berulang. Di sisi lain juga, ada manfaat lainnya yaitu dokumentasi. Jadi siapapun tahu konfigurasi server, kebutuhan aplikasi server dan sebagainya.
Untuk menerapkan IAC tools/alat yang digunakan adalah Packer (build image), Terraform (build vm dan privisioning instance/vm/server),Ansible,Chef,Puppet & Salt Stack (Configurations Management).
Dengan menggunakan fasilitas yang terdapat pada katacoda, akan kami coba untuk mengaplikasikan IaC pada CFEngine ("https://www.katacoda.com/nickanderson/scenarios/cfengine-hub-install"). CFEngine sendiri merupakan sistem manajemen konfigurasi yang menyediakan framework untuk pengelolaan infrastruktur IT secara otomatis.

**Step 1 - Configure the host**
Pertama, memastikan bahwa nama host yang kita minta ketika mengakses Portal Misi dapat diselesaikan dengan benar. 
$ sudo bash -c "echo 127.0.0.1 2886795350-443-ollie02.environments.katacoda.com >> /etc/hosts"

Selanjutnya memastikan host dan sertifikat ssl yang dihasilkan selama pemasangan tetap sesuai.
 $ sudo hostnamectl set-hostname 2886795350-443-ollie02.environments.katacoda.com

**Step 2 - Install Package**
Download dan instal Paket Hub Ubuntu. Kami menggunakan quick install script dan akan menginstal versi LTS terbaru dari CFEngine Enterprise secara default.
$ wget http://s3.amazonaws.com/cfengine.packages/quick-install-cfengine-enterprise.sh
![1](https://user-images.githubusercontent.com/42165699/49919363-ee58fb00-fed8-11e8-8f8f-f0d19c73422e.png)

**install CFEngin versi 3.11**
$ sudo CFEngine_Enterprise_Package_Version="3.11.0" bash ./quick-install-cfengine-enterprise.sh hub

**Step 3 - Bootstrap Hub**
Bootstrap hub
$ sudo /var/cfengine/bin/cf-agent --bootstrap 2886795306-443-frugo04.environments.katacoda.com

Menjalankan kebijakan/policy sampai instalasi selesai
$ sudo /var/cfengine/bin/cf-agent --no-lock –inform

**Step 4 - Collect Reports**
Selanjutnya, hub akan mengumpulkan reports dari kebijakan sebelumnya dan Portal akan diisi dengan data. 
$ sudo cf-hub -q delta -H $(hostname -f) –v







**Step 5 - Log in to Mission Portal**
Kemudian masuk ke Mission Portal  dengan user/password yaitu admin / admin.
![2](https://user-images.githubusercontent.com/42165699/49919462-47289380-fed9-11e8-9e9f-6b0b4c0ef110.png)

Tampilan Dashboard CFEngine
![3](https://user-images.githubusercontent.com/42165699/49919495-632c3500-fed9-11e8-840e-cc0885ca11a0.png)

Sekian dan Terimakasih 

