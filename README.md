# Raspberry Pi LoRa P2P Node

## Comandos Iniciais

- Instalar o Raspberry Pi OS Lite [aqui](https://www.raspberrypi.com/software/).
- Habilitar a SPI, em Interface Options
```c++
sudo raspi-config
```
- Copiar o arquivo "spi-cs-extend.dts", e na mesma pasta, rodar:
```c++
sudo dtc -@ -I dts -O dtb -o spi-cs-extend.dtbo spi-cs-extend.dts
sudo cp spi-cs-extend.dtbo /boot/overlays
```
- Adicionar no final do arquivo "/boot/config.txt":
```c++
dtoverlay=spi-cs-extend
```
- Reiniciar o Raspberry
```c++
sudo reboot
```
- Com isso, tem uma nova spi em /dev/spi0.2, que será usada pelo Shield
- Para verificar:
```c++
ls -1 /dev/spidev0.*
```

## Instalando o Python
```c++
sudo apt-get install python-dev python3-dev
sudo apt-get install python-pip python3-pip
pip install RPi.GPIO
pip install spidev
pip install pyLoRa
```

## Clonando o repositório
```c++
sudo apt-get install git
sudo git clone --inserir nosso repositório
```

## Usando o Software
```c++
cd pySX127x
```
- Para usar o Server:
```c++
python3 ./LORA_SERVER.py
```
- Para usar o Client:
```c++
python3 ./LORA_CLIENT.py
```

## Mapeamento de Pinos

O mapeamento completo de pinos da BCM pode ser visto [aqui](https://github.com/fox-iot/Send_CPU_Rpi_LoRaWAN_Shield_Fox/blob/main/doc/Raspberry%20Pi%20GPIO%20Pins.png)

# Raspberry Pi LoRa P2P Node

## Comandos Iniciais

- Instalar o Raspberry Pi OS Lite [aqui](https://www.raspberrypi.com/software/).
- Habilitar a SPI, em Interface Options
```c++
sudo raspi-config
```
- Copiar o arquivo "spi-cs-extend.dts", e na mesma pasta, rodar:
```c++
sudo dtc -@ -I dts -O dtb -o spi-cs-extend.dtbo spi-cs-extend.dts
sudo cp spi-cs-extend.dtbo /boot/overlays
```
- Adicionar no final do arquivo "/boot/config.txt":
```c++
dtoverlay=spi-cs-extend
```
- Reiniciar o Raspberry
```c++
sudo reboot
```
- Com isso, tem uma nova spi em /dev/spi0.2, que será usada pelo Shield
- Para verificar:
```c++
ls -1 /dev/spidev0.*
```

## Instalando o Python
```c++
sudo apt-get install python-dev python3-dev
sudo apt-get install python-pip python3-pip
pip install RPi.GPIO
pip install spidev
pip install pyLoRa
```

## Clonando o repositório
```c++
sudo apt-get install git
sudo git clone --inserir nosso repositório
```

## Usando o Software
```c++
cd pySX127x
```
- Para usar o Server:
```c++
python3 ./LORA_SERVER.py
```
- Para usar o Client:
```c++
python3 ./LORA_CLIENT.py
```

## Mapeamento de Pinos

O mapeamento completo de pinos da BCM pode ser visto [aqui](https://github.com/fox-iot/Send_CPU_Rpi_LoRaWAN_Shield_Fox/blob/main/doc/Raspberry%20Pi%20GPIO%20Pins.png)

 | Raspberry 	| Descrição 	|
|:---:	|:---:	|
| BCM 17  	|  Reset 	|
| BCM 23  	|  DIO0 	|
| BCM 24  	|  DIO1 	|
| BCM 18  	|  DIO2 (Não utilizado) 	|
| BCM 10  	|  MOSI 	|
| BCM 9  	|  MISO 	|
| BCM 11  	|  SCK 	|
| BCM 25  	|  SS 	|
| BCM 27  	|  LED1 	|
| BCM 22  	|  LED2 	|
| GND  	|  GND 	|
| 3.3V  	|  +3.3V 	|

## Licença

O conteúdo está licenciado sob a licença MIT. Veja [License File](LICENSE) para mais informações.
