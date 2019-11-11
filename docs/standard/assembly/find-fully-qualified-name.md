---
title: '方法: アセンブリの完全修飾名を検索する'
ms.date: 08/20/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: bf24db03ca1dc4fbf3041f5e83d740029d87928f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740501"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a><span data-ttu-id="74187-102">方法: アセンブリの完全修飾名を検索する</span><span class="sxs-lookup"><span data-stu-id="74187-102">How to: Find an assembly's fully qualified name</span></span>

<span data-ttu-id="74187-103">グローバル アセンブリ キャッシュ内の .NET Framework アセンブリの完全修飾名を検出するには、グローバル アセンブリ キャッシュ ツール ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="74187-103">To discover the fully qualified name of a .NET Framework assembly in the global assembly cache, use the Global Assembly Cache tool ([Gacutil.exe](../../framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="74187-104">「[方法:グローバル アセンブリ キャッシュの内容を表示する](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74187-104">See [How to: View the contents of the global assembly cache](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>

<span data-ttu-id="74187-105">.NET Core アセンブリの場合、およびグローバル アセンブリ キャッシュにない .NET Framework アセンブリの場合、完全修飾アセンブリ名をいくつかの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="74187-105">For .NET Core assemblies, and for .NET Framework assemblies that aren't in the global assembly cache, you can get the fully qualified assembly name in a number of ways:</span></span>

- <span data-ttu-id="74187-106">コードを使用しコンソールや変数に情報を出力したり、[Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) を使用して完全修飾名を含むアセンブリのメタデータを調べたりできます。</span><span class="sxs-lookup"><span data-stu-id="74187-106">You can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>

- <span data-ttu-id="74187-107">アセンブリがアプリケーションによって既に読み込まれている場合、<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> プロパティの値を取得して、完全修飾名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="74187-107">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="74187-108">アセンブリに定義されている <xref:System.Type> の <xref:System.Type.Assembly> プロパティを使用して、<xref:System.Reflection.Assembly> オブジェクトへの参照を取得できます。</span><span class="sxs-lookup"><span data-stu-id="74187-108">You can use the <xref:System.Type.Assembly> property of a <xref:System.Type> defined in that assembly to retrieve a reference to the <xref:System.Reflection.Assembly> object.</span></span> <span data-ttu-id="74187-109">具体的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74187-109">The example provides an illustration.</span></span>

- <span data-ttu-id="74187-110">アセンブリのファイル システム パスがわかっている場合は、`static` (C#) または `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> メソッドを呼び出して、完全修飾アセンブリ名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="74187-110">If you know the assembly's file system path, you can call the `static` (C#) or `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="74187-111">単純な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74187-111">The following is a simple example.</span></span>

  ```csharp
  using System;
  using System.Reflection;

  public class Example
  {
     public static void Main()
     {
        Console.WriteLine(AssemblyName.GetAssemblyName(@".\UtilityLibrary.dll"));
     }
  }
  // The example displays output like the following:
  //   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

  ```vb
  Imports System.Reflection

  Public Module Example
     Public Sub Main
        Console.WriteLine(AssemblyName.GetAssemblyName(".\UtilityLibrary.dll"))
     End Sub
  End Module
  ' The example displays output like the following:
  '   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

- <span data-ttu-id="74187-112">[Ildasm.exe (IL 逆アセンブラー)](../../framework/tools/ildasm-exe-il-disassembler.md) を使用して、アセンブリのメタデータを使用できます。これには完全修飾名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="74187-112">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>

<span data-ttu-id="74187-113">バージョン、カルチャ、アセンブリ名などのアセンブリ属性の設定の詳細については、「[アセンブリ属性の設定](set-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74187-113">For more information about setting assembly attributes such as version, culture, and assembly name, see [Set assembly attributes](set-attributes.md).</span></span> <span data-ttu-id="74187-114">アセンブリに厳密な名前を指定する方法の詳細については、「[厳密な名前付きアセンブリの作成と使用](create-use-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74187-114">For more information about giving an assembly a strong name, see [Create and use strong-named assemblies](create-use-strong-named.md).</span></span>

## <a name="example"></a><span data-ttu-id="74187-115">例</span><span class="sxs-lookup"><span data-stu-id="74187-115">Example</span></span>

<span data-ttu-id="74187-116">指定したクラスを含むアセンブリの完全修飾名をコンソールに表示する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="74187-116">The following example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="74187-117"><xref:System.Type.Assembly?displayProperty=nameWithType> プロパティを使用して、そのアセンブリで定義されている型からアセンブリへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="74187-117">It uses the <xref:System.Type.Assembly?displayProperty=nameWithType> property to retrieve a reference to an assembly from a type that's defined in that assembly.</span></span>

```cpp
#using <System.dll>
#using <System.Data.dll>

using namespace System;
using namespace System::Reflection;

ref class asmname
{
public:
    static void Main()
    {
        Type^ t = System::Data::DataSet::typeid;
        String^ s = t->Assembly->FullName->ToString();
        Console::WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
};

int main()
{
    asmname::Main();
}
```

```csharp
using System;
using System.Reflection;

class asmname
{
    public static void Main()
    {
        Type t = typeof(System.Data.DataSet);
        string s = t.Assembly.FullName.ToString();
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
}
```

```vb
Imports System
Imports System.Reflection

Class asmname
    Public Shared Sub Main()
        Dim t As Type = GetType(System.Data.DataSet)
        Dim s As String = t.Assembly.FullName.ToString()
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s)
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="74187-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="74187-118">See also</span></span>

- [<span data-ttu-id="74187-119">アセンブリ名</span><span class="sxs-lookup"><span data-stu-id="74187-119">Assembly names</span></span>](names.md)
- [<span data-ttu-id="74187-120">アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="74187-120">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="74187-121">厳密な名前付きアセンブリの作成と使用</span><span class="sxs-lookup"><span data-stu-id="74187-121">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="74187-122">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="74187-122">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="74187-123">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="74187-123">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
