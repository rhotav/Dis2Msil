# Dis2MSIL

Dis2MSIL is disassembler for MSIL ByteCode

> This project is the developed and edited version of the "SDILReader"
> project on CodeProject.

# Usage

You can disassemble the bytecodes to be given as String or Byte[] using the **MethodBodyReader** class.
```csharp
public MethodBodyReader(Module module, string strilArray)
public MethodBodyReader(Module module, byte[] ilArray)
```
The "module" parameter here is required for metadata Tokens that need to be resolved.

## For Bytecodes Of Type String
```csharp
string testIl = "02-28-1C-00-00-0A-00-00-02-03-7D-11-00-00-04-2A";
string fileName = args[0];
MethodBodyReader mr = new MethodBodyReader(Assembly.LoadFrom(fileName).EntryPoint.Module, testIl);
Console.Write(mr.GetBodyCode());
```
  ![Screenshot_2](https://user-images.githubusercontent.com/54905232/127747413-31c88a55-3c38-44cb-ba67-a5af760a5c42.png)

## For Bytecodes Of Type Byte[]
```csharp
byte[] testIlByte = { 0x02, 0x28, 0x1C, 0x00, 0x00, 0x0A, 0x00, 0x00, 0x02, 0x03, 0x7D, 0x11, 0x00, 0x00, 0x04, 0x2A };
string fileName = args[0];
MethodBodyReader mrByte = new MethodBodyReader(Assembly.LoadFrom(fileName).EntryPoint.Module, testIlByte);
Console.Write(mrByte.GetBodyCode());
```
![Screenshot_2](https://user-images.githubusercontent.com/54905232/127747413-31c88a55-3c38-44cb-ba67-a5af760a5c42.png)

