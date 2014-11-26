# docker-gitlist-demo
===================
Demo docker dengan menjalankan [gitlist](https://github.com/klaussilveira/gitlist)  
Langkah-langkah berikut telah diuji pada OS Ubuntu 14.04

# Instalasi
* _Install_ [Docker](https://docs.docker.com/installation/), `curl -sSL https://get.docker.com/ubuntu/ | sudo sh`
* _Install_ [Fig](http://www.fig.sh/install.html), `sudo apt-get install -y python-pip && sudo pip install -U fig`
* _Clone_ repositori, `git clone https://github.com/ringanta/docker-gitlist-demo`
* Buat direktori untuk menampung repo yang akan ditampilkan dengan gitlist, `cd docker-gitlist-demo && mkdir repositories`
* Isi direktori dengan daftar repo, misalkan repositori gitlist sendiri, `cd git clone https://github.com/klaussilveira/gitlist repositories/gitlist`
* Jalankan perintah fig, `sudo fig up`
* Hasilnya dapat diakses di http://localhost:8080/
