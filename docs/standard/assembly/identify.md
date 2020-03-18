---
title: '方法: ファイルがアセンブリであるかどうかを確認する'
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1d66c0c166724f195a3cafd9bcbe3c7414c08ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159508"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="d1566-102">方法: ファイルがアセンブリであるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="d1566-102">How to: Determine if a file is an assembly</span></span>

<span data-ttu-id="d1566-103">ファイルが管理されていて、ファイルのメタデータにアセンブリ エントリが含まれている場合、そのファイルはアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="d1566-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="d1566-104">アセンブリとメタデータの詳細については、「[アセンブリ マニフェスト](manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1566-104">For more information on assemblies and metadata, see [Assembly manifest](manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="d1566-105">ファイルがアセンブリかどうかを手動で確認する方法</span><span class="sxs-lookup"><span data-stu-id="d1566-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="d1566-106">[Ildasm.exe (IL 逆アセンブラー)](../../framework/tools/ildasm-exe-il-disassembler.md) を起動します。</span><span class="sxs-lookup"><span data-stu-id="d1566-106">Start the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="d1566-107">テストするファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d1566-107">Load the file you want to test.</span></span>  
  
3. <span data-ttu-id="d1566-108">**ILDASM** で、そのファイルが移植可能な実行可能 (PE) ファイルではないと報告された場合、そのファイルはアセンブリでありません。</span><span class="sxs-lookup"><span data-stu-id="d1566-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="d1566-109">詳細については、トピック「[方法: アセンブリの内容を表示する](view-contents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1566-109">For more information, see the topic [How to: View assembly contents](view-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="d1566-110">ファイルがアセンブリかどうかをプログラムによって確認する方法</span><span class="sxs-lookup"><span data-stu-id="d1566-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="d1566-111">テストするファイルの完全パスと名前を渡して、<xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d1566-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="d1566-112"><xref:System.BadImageFormatException> 例外がスローされた場合、ファイルはアセンブリでありません。</span><span class="sxs-lookup"><span data-stu-id="d1566-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1566-113">例</span><span class="sxs-lookup"><span data-stu-id="d1566-113">Example</span></span>  
<span data-ttu-id="d1566-114">次の例では、DLL がアセンブリかどうかをテストして確認します。</span><span class="sxs-lookup"><span data-stu-id="d1566-114">This example tests a DLL to see if it is an assembly.</span></span>  

```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  

```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```

<span data-ttu-id="d1566-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> メソッドはテスト ファイルを読み込み、情報が読み取られた時点で解放します。</span><span class="sxs-lookup"><span data-stu-id="d1566-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1566-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1566-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="d1566-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d1566-117">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d1566-118">プログラミングの概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1566-118">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="d1566-119">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="d1566-119">Assemblies in .NET</span></span>](index.md)
