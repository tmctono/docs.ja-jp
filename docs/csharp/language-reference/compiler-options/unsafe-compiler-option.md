---
title: -unsafe (C# コンパイラ オプション)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4cfd7c82bc2cbf816164b235642c0647eeb7e5b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337332"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="cf992-102">-unsafe (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="cf992-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="cf992-103">**-unsafe** コンパイラ オプションは、[unsafe](../../../csharp/language-reference/keywords/unsafe.md) キーワードを使用するコードをコンパイルできるようにします。</span><span class="sxs-lookup"><span data-stu-id="cf992-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf992-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf992-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf992-105">解説</span><span class="sxs-lookup"><span data-stu-id="cf992-105">Remarks</span></span>  
 <span data-ttu-id="cf992-106">アンセーフ コードの詳細については、「[アンセーフ コードとポインター](../../../csharp/programming-guide/unsafe-code-pointers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf992-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cf992-107">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="cf992-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="cf992-108">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf992-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="cf992-109">**[ビルド]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf992-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="cf992-110">**[アンセーフ コードの許可]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf992-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="cf992-111">このオプションを csproj ファイルに追加するには</span><span class="sxs-lookup"><span data-stu-id="cf992-111">To add this option in a csproj file</span></span>

<span data-ttu-id="cf992-112">プロジェクトの .csproj ファイルを開き、次の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf992-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="cf992-113">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf992-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf992-114">例</span><span class="sxs-lookup"><span data-stu-id="cf992-114">Example</span></span>  
 <span data-ttu-id="cf992-115">unsafe モードで `in.cs` をコンパイルする場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf992-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf992-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf992-116">See also</span></span>

- [<span data-ttu-id="cf992-117">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="cf992-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="cf992-118">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="cf992-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
