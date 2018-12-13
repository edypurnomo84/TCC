# TCC
IaC - CFEngine Portal</br>
Infrastructure as Code</br>
</br>
Infrastructure as Code adalah proses penyediaan IT infrastruktur dimana sistem dibangun dan dikelola melalui kode secara automasi (otomatis), bukan secara manual. Atau bisa disebut juga bahasa kerennya Programmable Infrastructure.

Dengan menggunakan kode dan meng-automasi, proses setting dan konfigurasi baremetal, virtual mesin, cloud computing baik itu instalasi baru, perubahan konfigurasi dapat dilakukan secara cepat, mudah, dan berulang. Di sisi lain juga, ada manfaat lainnya yaitu dokumentasi. Jadi siapapun tahu konfigurasi server, kebutuhan aplikasi server dan sebagainya.

Untuk menerapkan IAC tools/alat yang digunakan adalah Packer (build image), Terraform (build vm dan privisioning instance/vm/server),Ansible,Chef,Puppet & Salt Stack (Configurations Management).

Pada kesempatan ini kita menggunakan Terraform untuk build VM sampai provisioning di OpenStack.

Provider yang disupport Terraform adalah:
<li>Atlas (Hashicorp workflow engine)</li>
<li>AWS, GCE, Azure, OpenStack, DigitalOcean, Docker, CloudStack, Heroku, vSphere, vCloud (Cloud Infrastructure)</li>
<li>Chef, Rundeck (Configuration Management)</li>
<li>CloudFlare, DNSMadeEasy, Dyn, DNSimple (DNS provider)</li>
<li>Mailgun (Email)</li>
<li>Consul, PowerDNS (DNS and service registry)</li>
<li>MySQL, PostgreSQL (Database)</li>
<li>StatusCake (Monitoring)</li>
<li>TLS (Certificates)</li>

Dengan menggunakan fasilitas yang terdapat pada katacoda, akan kami coba untuk mengaplikasikan IaC pada CFEngine ("https://www.katacoda.com/nickanderson/scenarios/cfengine-hub-install").
CFEngine sendiri merupakan sistem manajemen konfigurasi yang menyediakan framework untuk pengelolaan infrastruktur IT secara otomatis.</br>
Step 1 - Configure the host</br>

