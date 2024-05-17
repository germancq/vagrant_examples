# vagrant_examples:

- **Instalacion en debian/ubuntu**

    1. *[Vagrant](https://www.vagrantup.com/)*

        ```
        sudo apt update
        sudo apt install vagrant
        ```

    2. *Herramienta de Virtualizacion*

        Existen varias opciones, en este documento se detallaran dos de ellas.

        - *[VirtualBox](https://www.virtualbox.org/)*

            1. **Ubuntu 22.04**

                ```
                sudo apt update
                sudo apt install virtualbox
                sudo reboot
                ```

            2. Debian 12


                ```
                sudo apt update

                sudo apt install lsb-release


                echo "deb http://deb.debian.org/debian $(lsb_release -cs)-backports main contrib" |
                sudo tee /etc/apt/sources.list.d/backports.list

                sudo apt install fasttrack-archive-keyring

                echo "deb http://fasttrack.debian.net/debian-fasttrack/ $(lsb_release -cs)-fasttrack main contrib" | sudo tee /etc/apt/sources.list.d/fasttrack.list
                echo "deb http://fasttrack.debian.net/debian-fasttrack/ $(lsb_release -cs)-backports-staging main contrib" | sudo tee -a /etc/apt/sources.list.d/fasttrack.list

                sudo apt update

                sudo apt install virtualbox virtualbox-ext-pack

                sudo apt install virtualbox-guest-utils

                sudo usermod -a -G vboxusers $USER

                sudo reboot
                ```


        - *KVM*

            1. Ubuntu 22.04
                ```
                sudo apt install qemu libvirt-daemon-system libvirt-clients libxslt-dev libvirt-dev zlib1g-dev ruby-dev ruby-libvirt ebtables dnsmasq-base
                ```

            2. **Debian 12**

                ```
                sudo apt update

                sudo apt install qemu-system libvirt-daemon-system virt-manager libvirt-dev ruby-libvirt build-essential libvirt-clients ebtables dnsmasq-base libxslt1-dev libxml2-dev zlib1g-dev ruby-dev libguestfs-tools

                sudo adduser $USER libvirt



                ```



            ```
            vagrant plugin install vagrant-libvirt
            vagrant plugin install vagrant-mutate

            sudo reboot
            ```
