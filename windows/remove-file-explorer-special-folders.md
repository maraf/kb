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

There is also a second way, desribed in https://www.thewindowsclub.com/remove-the-folders-from-this-pc-windows-10.

In Windows registry, open

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions
```

Than select GUID and under it, in `PropertyBag` change `ThisPCPolicy` value from `Show` to `Hide`.

#### Documents 

```
{f42ee2d3-909f-4907-8871-4c22fc0bf756}
```

#### Pictures 

```
{0ddd015d-b06c-45d5-8c4c-f59713854639}
```

#### Videos 

```
{35286a68-3c57-41a1-bbb1-0eae73d76c95}
```

#### Music 

```
{a0c69a99-21c8-4671-8703-7934162fcf1d}
```

#### Desktop  

```
{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
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
