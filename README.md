# Deploying resources with Azure Resource Manager

**Zadanie 3.1 - Konwencja nazewnicza**

## Grupa zasobów
```
<service-short-name>-<environment>-rg<number>
 ```
service-short-name - skrócona nazwa usługi

environment - skrócona nazwa środowiska (prod, dev, test, staging)

number - numer grupy zasobów

## Sieci wirtualne
```
<service-short-name>-vnet<number>
 ```
service-short-name - skrócona nazwa usługi

number - numer sieci wirtualnej

## Subnety
```
<vnetname>-subnet<number>
 ```
vnetname - nazwa vnet'a

number - numer subnet'a

## Maszyny wirtualne
```
<service-short-name>-<role>-vm<number>
 ```
service-short-name - skrócona nazwa usługi
 
role - przeznaczenie maszyny wirtualnej

number - numer maszyny wirtualnej

## Dyski - OS
```
<vm-name>-osdisk
```
vm-name - nazwa maszyny wirtualnej

## Dyski - pozostałe
```
<vm-name>-vmdisk-<number>
 ```
vm-name - nazwa maszyny wirtualnej

number - numer dysku

## Dyski storage'owe
```
<short-service-name>-<role>-st<number>
 ```
service-short-name - skrócona nazwa usługi

role - przeznaczenie np. grafiki, dane

number - numer dysku

**Zadanie 3.2 - ARM Template**

Skrypt tworzący całość to zadanie3.json, korzysta on z linked templates:

 + vnet.json
 
 + subnet.json
 
 + vm.json
 
 + nsg.json
 
