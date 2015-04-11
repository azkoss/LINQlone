## **LINQlone** ##

LINQlone is a re-implementation of *LINQ to Objects* for Microsoft .NET Framework 2.0 providing all the standard query operators of Microsoft .NET Framework 3.5. With *C# 2.0+* LINQlone also activates *extension methods* and *lambda expressions*. The aim of this open source project is not to replace or improve Microsoft LINQ, but is to provide the same functionality and behavior for projects targeting .NET Framework 2.0. 

LINQlone is a single dll file containing standard LINQ namespace, method names and signitures. Thus, LINQlone can be easly removed from the project. The project can easly be upgraded to .NET Framework 3.5. Upgrade only requires LINQlone reference to be removed. *Without any code edits*, all the query operators will be binded to Microsoft LINQ.

## **Namespace** ##

Namespaces contained within *LINQlone.dll*
```c#
using System; //Func and Action delegates
using System.Linq; //Standard query operators
using System.Runtime.CompilerServices; //ExtensionAttribute providing extension method usage
```
## **Using LINQlone Query Operators** ##

**C# 2.0**
```c#
IEnumerable<string> customerNames = Enumerable.Select(customers, delegate(Customer x) { return x.Name; });
```
**C# 2.0+**
```c#
//Fluent Syntax
IEnumerable<string> customerNames = customers.Select(x => x.Name);

//Query Syntax
IEnumerable<string> customerNames = from customer in customers select customer.Name;
```
**VB 9.0**
```vb
Dim customerNames As IEnumerable(Of String) = Enumerable.Select(customers, Function(x) x.Name)
```
**VB 9.0+**
```vb
'Fluent Syntax
Dim customerNames As IEnumerable(Of String) = customers.Select(Function(x) x.Name)

'Query Syntax
Dim customerNames As IEnumerable(Of String) = From customer As Customer In customers Select customer.Name
```

## **Samples** ##

LINQlone does not include samples. *LINQlone.Test* project can be an example of LINQ query operator usage. For more samples, check the samples below:
* [MSDN LINQ101](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (Query Syntax)
* [Nilzor's LINQ101](http://linq101.nilzorblog.com/linq101-lambda.php) (Fluent Syntax)

## **How to** ##

### How to use query or fleunt syntax? ###
In order to be able to use query syntax, *C# 2.0+* or *VB 9.0+* is required. Using *Visual Studio 2008* or above, extension methods and standard delegates defined in *LINQlone* assembly will be enabled.

### How to replace *LINQlone* with *Microsoft LINQ* when upgraded to .NET 3.5? ###
Replacing *LINQlone* with *Microsoft LINQ* can be easily done removing *LINQlone* reference (LINQlone.dll) from the project. Since all the namespace, method names and signitures match *no code edit is required*. All query operators will be binded to *Microsoft LINQ*.

### Will LINQlone work just as Microsoft LINQ does? ###
With some slight difference, it will function as *Microsoft LINQ* does. All summeries, namespace, method names and signitures, functionality, behavior and exceptions match.

## **Limitations** ##

Altho all summeries, exception types and properties are supported, *LINQlone* does not support localized exception messages. Exception messages are in *English* only

## **Authors** ##

* Saro Taşciyan (Zefnus)
* Bedir Yılmaz (3Yanlis1Bos)