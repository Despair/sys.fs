``` fsharp
let (<++|) device bytes size =
    let unmanagedPtr = Marshal.AllocHGlobal(size : int)
    Marshal.Copy( (bytes : byte array), 0, unmanagedPtr, size)
    Marshal.PtrToStructure(unmanagedPtr, (device : obj))
    Marshal.FreeHGlobal(unmanagedPtr)
```
