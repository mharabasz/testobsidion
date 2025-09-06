# Skrypt PowerShell do konfiguracji statycznego adresu IP na Windows Server # Zmienne konfiguracyjne $interfaceName = "Ethernet" # Domyślna nazwa interfejsu sieciowego 
$ipAddress = "192.168.10.100" 
$subnetMask = "255.255.255.0" 
$gateway = "192.168.10.1" 
$dns = "192.168.10.1" Write-Host "Ustawianie statycznego adresu IP dla interfejsu $interfaceName..." # Ustawienie statycznego adresu IP New-NetIPAddress -InterfaceAlias $interfaceName -IPAddress $ipAddress -PrefixLength 24 -DefaultGateway $gateway # Ustawienie adresu serwera DNS Set-DnsClientServerAddress -InterfaceAlias $interfaceName -ServerAddresses $dns Write-Host "Adres IP i DNS zostały ustawione."