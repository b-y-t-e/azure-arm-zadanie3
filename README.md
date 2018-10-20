# Deploying resources with Azure Resource Manager

## Zadanie 3.1 - Konwencja nazewnicza

### Grupa zasobów
```
<service-short-name>-<environment>-rg<number>
 ```
service-short-name - skrócona nazwa usługi

environment - skrócona nazwa środowiska (prod, dev, test, staging)

number - numer grupy zasobów

### Sieci wirtualne
```
<service-short-name>-vnet<number>
 ```
service-short-name - skrócona nazwa usługi

number - numer sieci wirtualnej

### Subnety
```
<vnetname>-subnet<number>
 ```
vnetname - nazwa vnet'a

number - numer subnet'a

### Maszyny wirtualne
```
<service-short-name>-<role>-vm<number>
 ```
service-short-name - skrócona nazwa usługi
 
role - przeznaczenie maszyny wirtualnej

number - numer maszyny wirtualnej

### Dyski - OS
```
<vm-name>-osdisk
```
vm-name - nazwa maszyny wirtualnej

### Dyski - pozostałe
```
<vm-name>-vmdisk-<number>
 ```
vm-name - nazwa maszyny wirtualnej

number - numer dysku

### Dyski storage'owe
```
<short-service-name>-<role>-st<number>
 ```
service-short-name - skrócona nazwa usługi

role - przeznaczenie np. grafiki, dane

number - numer dysku

## Zadanie 3.2 - ARM Template

Skrypt tworzący całość to work.json, korzysta on z linked templates:

 + vnet.json (tworzy 1 vnet)
 
 + subnet.json (tworzy 1 subnet)
 
 + vm.json (tworzy 1 vm ubuntu 18.04 lts na standard b1s)
 
 + nsg.json (tworzy nsg z otwartymi portami 22, 80 i 443)
 

## Zadanie 3.3 - Custom rola - RBAC

Pozwala użytkownikowi uruchomić maszynę, zatrzymać ją i zgłosić zgłoszenie do supportu przez Portal Azure”
Skrypt tworzący to custom.role.json

## Zadanie 3.4 - Połączenie z key vaults

Połączenie odbywa się w pliku z paramtrami 'work.parameters.json', key vault w azure musi mieć włączone ustawienie --enabled-for-template-deployment true
