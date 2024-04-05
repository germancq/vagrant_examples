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

                sudo apt install gpg

                wget -O- -q https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --dearmour -o /usr/share/keyrings/oracle_vbox_2016.gpg

                echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle_vbox_2016.gpg] http://download.virtualbox.org/virtualbox/debian bookworm contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list

                sudo apt update

                sudo apt install virtualbox-7.0

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
