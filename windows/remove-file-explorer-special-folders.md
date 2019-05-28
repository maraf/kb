# Remove File Explorer special folders

Special folders are listed in the Windows Registry.

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace
```

Each can be removed by removing its key.

#### 3D Objects

```
{0DB7E03F-FC29-4DC6-9020-FF41B59E513A}
```

# Remove duplicated File Explorer hard drives

In the Windows Registry, open:

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\DelegateFolders
```

Than remove key:

```
{F5FB2C77-0E2F-4A16-A381-3E560C68BC83}
```
