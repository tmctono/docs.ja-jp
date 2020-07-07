---
title: '方法: 相互運用機能アセンブリをタイプ ライブラリから生成する'
description: 相互運用機能アセンブリをタイプ ライブラリから生成します。 タイプライブラリ インポーター (Tlbimp.exe) を使用して、コクラスおよびインターフェイスを COM タイプライブラリからメタデータに変換します。
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 6f54875d6aadb1da18cf25a1bec0a0e451f4a24c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619560"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="7a545-104">方法: 相互運用機能アセンブリをタイプ ライブラリから生成する</span><span class="sxs-lookup"><span data-stu-id="7a545-104">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="7a545-105">[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) は、COM タイプ ライブラリに含まれているコクラスとインターフェイスをメタデータに変換するコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="7a545-105">The [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="7a545-106">このツールは、型情報の相互運用機能アセンブリと名前空間を自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="7a545-106">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="7a545-107">クラスのメタデータが使用可能になった後、マネージド クライアントは COM 型のインスタンスを作成し、.NET インスタンスの場合と同じように、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7a545-107">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="7a545-108">Tlbimp.exe は、タイプ ライブラリ全体を一度にメタデータに変換しますが、タイプ ライブラリで定義されている型のサブセットの型情報は生成できません。</span><span class="sxs-lookup"><span data-stu-id="7a545-108">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="7a545-109">タイプ ライブラリから相互運用機能アセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="7a545-109">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="7a545-110">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a545-110">Use the following command:</span></span>  
  
     <span data-ttu-id="7a545-111">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="7a545-111">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="7a545-112">**/out:** スイッチを追加することによって、LOANLib.dll などの別の名前で相互運用機能アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="7a545-112">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="7a545-113">相互運用機能アセンブリの名前を変更しておくと、元の COM DLL との区別が付きやすくなり、名前の重複によって発生する可能性のある問題を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="7a545-113">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a545-114">例</span><span class="sxs-lookup"><span data-stu-id="7a545-114">Example</span></span>  
 <span data-ttu-id="7a545-115">次のコマンドでは、`Loanlib` 名前空間で Loanlib.dll アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="7a545-115">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="7a545-116">次のコマンドでは、別の名前 (LOANLib.dll) で相互運用機能アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7a545-116">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a545-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a545-117">See also</span></span>

- [<span data-ttu-id="7a545-118">タイプ ライブラリのアセンブリとしてのインポート</span><span class="sxs-lookup"><span data-stu-id="7a545-118">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="7a545-119">.NET Framework への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="7a545-119">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
