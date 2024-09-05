phytec-dev-ca
=============

> [!WARNING]
> ### For demonstration purposes only!
> All passwords, keys, certificates and other files in this repository are for
> demonstration purposes only! Never use these keys and certificates in a
> productive environment! This repository is publicly available and is **not**
> meant for securing private devices!

Dependencies
------------
The phytec-dev-ca is created with the Tool xca from https://hohnstaedt.de/xca  
The password for the phytec-dev-ca: phytec-dev-ca  
The keys for NXP HAB v4 are created with the NXP script from the cst tool

Certificate Hierarchie
----------------------

* main-ca: PHYTEC-ROOT is a self signed certificate with RSA-4096
  * nxp_ahab_pki: NXP keys for AHAB secure boot with NIST P-521 (secp521r1)
    * bootloader/boot container: for i.MX93
    * Super root keys (SRK) 1, 2, 3 and 4
    * Certificates for SRKs signed by PHYTEC Root CA
  * nxp_habv4_pki:  NXP Keys for HABV4 (SRK 1..4) secure boot with RSA-4096  
                    bootloader /boot container: for i.MX6, i.MX6UL, i.MX8M (MNP)  
                    fitImage: with u-boot for i.MX8M (MNP)
    * CSF
    * IMG
  * fit:    PHYTEC-FIT4096 for signing FIT-Images with RSA-4096  
            is used for i.MX6, i.MX6UL with barebox
  * rauc-intermediate: PHYTEC-rauc Intermediate CA with RSA-2048
    * development-1: PHYTEC-RAUC-Dev1 for signing rauc update bundles with RSA-2048
  * rauc-intermediate-crypt: PHYTEC-RAUC-CRYPT Intermediate CA for signing crypt device certificates with RSA-4096
    * PHYTEC-RAUC-CRYPT-recipients: Device certificates for encrypting the rauc update bundle with RSA-4096
  * kernel_modsign: PHYTEC-modsign for signing kernel modules with RSA-4096
  
* rauc: own self-signed CA only for rauc (old one)
  *  development-1: PHYTEC-RAUC-Dev1 for signing rauc update bundles with RSA-2048


