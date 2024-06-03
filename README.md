```
$vm = "虚拟机的名字"
```
```
Add-VMGpuPartitionAdapter -VMName $vm
```
```
Set-VMGpuPartitionAdapter -VMName $vm -MinPartitionVRAM 80000000 -MaxPartitionVRAM 100000000 -OptimalPartitionVRAM 100000000 -MinPartitionEncode 80000000 -MaxPartitionEncode 100000000 -OptimalPartitionEncode 100000000 -MinPartitionDecode 80000000 -MaxPartitionDecode 100000000 -OptimalPartitionDecode 100000000 -MinPartitionCompute 80000000 -MaxPartitionCompute 100000000 -OptimalPartitionCompute 100000000
```
```
Set-VM -GuestControlledCacheTypes $true -VMName $vm
```
```
Set-VM -LowMemoryMappedIoSpace 1Gb -VMName $vm
```
```
Set-VM -HighMemoryMappedIoSpace 32GB -VMName $vm
```
—————————-驱动拷贝目录——————————————–  
①宿主机驱动路径：C:\Windows\System32\DriverStore\FileRepository\  
①虚拟机拷贝路径：C:\Windows\System32\HostDriverStore\FileRepository\  

②N卡操作  
宿主机文件路径：C:\Windows\System32\nvapi64.dll  
虚拟机拷贝路径：C:\Windows\System32\nvapi64.dll  

②A卡操作  
所有宿主机，驱动管理器，显卡驱动信息里的文件都必须全部拷贝到虚拟机里（路径和宿主机相同）  
