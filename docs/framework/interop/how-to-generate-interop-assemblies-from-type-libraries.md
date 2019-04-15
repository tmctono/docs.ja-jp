---
title: '方法: 相互運用機能アセンブリをタイプ ライブラリから生成する'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a3ee82a9091f0caeee010ec79632ce703efb589
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338840"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="25105-102">方法: 相互運用機能アセンブリをタイプ ライブラリから生成する</span><span class="sxs-lookup"><span data-stu-id="25105-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="25105-103">[タイプ ライブラリ インポーター (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) は、COM タイプ ライブラリに含まれているコクラスとインターフェイスをメタデータに変換するコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="25105-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="25105-104">このツールは、型情報の相互運用機能アセンブリと名前空間を自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="25105-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="25105-105">クラスのメタデータが使用可能になった後、マネージド クライアントは COM 型のインスタンスを作成し、.NET インスタンスの場合と同じように、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="25105-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="25105-106">Tlbimp.exe は、タイプ ライブラリ全体を一度にメタデータに変換しますが、タイプ ライブラリで定義されている型のサブセットの型情報は生成できません。</span><span class="sxs-lookup"><span data-stu-id="25105-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="25105-107">タイプ ライブラリから相互運用機能アセンブリを生成するには</span><span class="sxs-lookup"><span data-stu-id="25105-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="25105-108">次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="25105-108">Use the following command:</span></span>  
  
     <span data-ttu-id="25105-109">**tlbimp** \<*type-library-file*></span><span class="sxs-lookup"><span data-stu-id="25105-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="25105-110">**/out:** スイッチを追加することによって、LOANLib.dll などの別の名前で相互運用機能アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="25105-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="25105-111">相互運用機能アセンブリの名前を変更しておくと、元の COM DLL との区別が付きやすくなり、名前の重複によって発生する可能性のある問題を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="25105-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25105-112">例</span><span class="sxs-lookup"><span data-stu-id="25105-112">Example</span></span>  
 <span data-ttu-id="25105-113">次のコマンドでは、`Loanlib` 名前空間で Loanlib.dll アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="25105-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="25105-114">次のコマンドでは、別の名前 (LOANLib.dll) で相互運用機能アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="25105-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="25105-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="25105-115">See also</span></span>

- [<span data-ttu-id="25105-116">タイプ ライブラリのアセンブリとしてのインポート</span><span class="sxs-lookup"><span data-stu-id="25105-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="25105-117">.NET Framework への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="25105-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)
