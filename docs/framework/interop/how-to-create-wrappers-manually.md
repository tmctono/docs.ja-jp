---
title: '方法: ラッパーを手動で作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db0ec9050c74b27d3ee25a99dcf8e2319835ffb
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894219"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="dadf8-102">方法: ラッパーを手動で作成する</span><span class="sxs-lookup"><span data-stu-id="dadf8-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="dadf8-103">マネージド ソース コード内で COM の型を手動で宣言することにした場合、まず既存のインターフェイス定義言語 (IDL: Interface Definition Language) ファイルまたはタイプ ライブラリを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dadf8-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="dadf8-104">IDL ファイルがないか、またはタイプ ライブラリ ファイルを生成できない場合には、マネージド宣言を作成してその結果のアセンブリをタイプ ライブラリにエクスポートすることで、COM の型をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="dadf8-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="dadf8-105">マネージド ソースから COM の型をシミュレートするには</span><span class="sxs-lookup"><span data-stu-id="dadf8-105">To simulate COM types from managed source</span></span>  
  
1. <span data-ttu-id="dadf8-106">共通言語仕様 (CLS: Common Language Specification) に準拠した言語を使用して型を宣言してからファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="dadf8-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2. <span data-ttu-id="dadf8-107">[タイプ ライブラリ エクスポーター (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) を使用して、その型を含むアセンブリをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="dadf8-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3. <span data-ttu-id="dadf8-108">エクスポートした COM タイプ ライブラリを、COM 指向のマネージド型を宣言するための基礎として使用します。</span><span class="sxs-lookup"><span data-stu-id="dadf8-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="dadf8-109">ランタイム呼び出し可能ラッパー (RCW: Runtime Callable Wrapper) を作成するには</span><span class="sxs-lookup"><span data-stu-id="dadf8-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1. <span data-ttu-id="dadf8-110">IDL ファイルまたはタイプ ライブラリ ファイルがあることを前提として、カスタム RCW に含めるクラスとインターフェイスを決定します。</span><span class="sxs-lookup"><span data-stu-id="dadf8-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="dadf8-111">アプリケーション内で直接にも間接にも使用される予定がない型がある場合は、それらを除外できます。</span><span class="sxs-lookup"><span data-stu-id="dadf8-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2. <span data-ttu-id="dadf8-112">CLS 準拠言語でソース ファイルを作成し、型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="dadf8-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="dadf8-113">インポート変換プロセスの詳しい説明については、「[タイプ ライブラリからアセンブリへの変換の要約](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dadf8-113">See [Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="dadf8-114">実際には、カスタム RCW を作成する場合は、[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) によって提供される型変換機能を手動で実行していることになります。</span><span class="sxs-lookup"><span data-stu-id="dadf8-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="dadf8-115">次のセクションの例では、IDL またはタイプ ライブラリ ファイル内の型と、C# コード内でそれぞれに対応する型について示します。</span><span class="sxs-lookup"><span data-stu-id="dadf8-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3. <span data-ttu-id="dadf8-116">宣言が完成したら、他のマネージド ソース コードのコンパイルと同様に、このファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="dadf8-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4. <span data-ttu-id="dadf8-117">Tlbimp.exe でインポートする型と同様に、追加情報が必要となる場合があります。その場合には、コードに直接追加できます。</span><span class="sxs-lookup"><span data-stu-id="dadf8-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="dadf8-118">詳細については、「[方法: 相互運用機能アセンブリ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dadf8-118">For details, see [How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dadf8-119">例</span><span class="sxs-lookup"><span data-stu-id="dadf8-119">Example</span></span>  
 <span data-ttu-id="dadf8-120">IDL に含まれる `ISATest` インターフェイスおよび `SATest` クラスの例と、C# ソース コードのそれらに対応する型を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="dadf8-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="dadf8-121">**IDL またはタイプ ライブラリ ファイル**</span><span class="sxs-lookup"><span data-stu-id="dadf8-121">**IDL or type library file**</span></span>  
  
```cpp
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="dadf8-122">**マネージド ソース コード内のラッパー**</span><span class="sxs-lookup"><span data-stu-id="dadf8-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dadf8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dadf8-123">See also</span></span>

- <span data-ttu-id="dadf8-124">[ランタイム呼び出し可能ラッパーのカスタマイズ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dadf8-124">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="dadf8-125">[COM のデータ型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dadf8-125">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="dadf8-126">[方法: 相互運用機能アセンブリ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dadf8-126">[How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="dadf8-127">[タイプ ライブラリからアセンブリへの変換の要約](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dadf8-127">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="dadf8-128">Tlbimp.exe (タイプ ライブラリ インポーター)</span><span class="sxs-lookup"><span data-stu-id="dadf8-128">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="dadf8-129">Tlbexp.exe (タイプ ライブラリ エクスポーター)</span><span class="sxs-lookup"><span data-stu-id="dadf8-129">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
