---
title: -warn (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602405"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="d4f89-102">-warn (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="d4f89-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="d4f89-103">**-warn** オプションは、コンパイラが表示する警告レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f89-104">構文</span><span class="sxs-lookup"><span data-stu-id="d4f89-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4f89-105">引数</span><span class="sxs-lookup"><span data-stu-id="d4f89-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="d4f89-106">コンパイルで表示する警告レベル:数値が小さいほど重要度が高い警告のみが表示され、数値が大きいほど多くの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f89-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="d4f89-107">有効な値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="d4f89-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="d4f89-108">警告レベル</span><span class="sxs-lookup"><span data-stu-id="d4f89-108">Warning level</span></span>|<span data-ttu-id="d4f89-109">説明</span><span class="sxs-lookup"><span data-stu-id="d4f89-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="d4f89-110">0</span><span class="sxs-lookup"><span data-stu-id="d4f89-110">0</span></span>|<span data-ttu-id="d4f89-111">すべての警告メッセージの出力をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d4f89-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="d4f89-112">1</span><span class="sxs-lookup"><span data-stu-id="d4f89-112">1</span></span>|<span data-ttu-id="d4f89-113">重大な警告メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="d4f89-114">2</span><span class="sxs-lookup"><span data-stu-id="d4f89-114">2</span></span>|<span data-ttu-id="d4f89-115">レベル 1 の警告に加え、クラス メンバーの非表示に関する警告など、より重大度の低い特定の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="d4f89-116">3</span><span class="sxs-lookup"><span data-stu-id="d4f89-116">3</span></span>|<span data-ttu-id="d4f89-117">レベル 2 の警告に加え、常に `true` または `false` に評価される式に関する警告など、より重大度の低い特定の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="d4f89-118">4 (既定)</span><span class="sxs-lookup"><span data-stu-id="d4f89-118">4 (the default)</span></span>|<span data-ttu-id="d4f89-119">レベルの 3 の警告に加え、情報のための警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4f89-120">解説</span><span class="sxs-lookup"><span data-stu-id="d4f89-120">Remarks</span></span>  
 <span data-ttu-id="d4f89-121">エラーまたは警告に関する情報を取得するには、ヘルプの索引でエラー コードを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="d4f89-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="d4f89-122">エラーまたは警告に関する情報を取得する他の方法については、「[C# コンパイラ エラー](../compiler-messages/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f89-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="d4f89-123">すべての警告をエラーとして扱う場合は [-warnaserror](./warnaserror-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-123">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="d4f89-124">特定の警告を無効にするには、[-nowarn](./nowarn-compiler-option.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-124">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="d4f89-125">**-w** は **-warn** の省略形です。</span><span class="sxs-lookup"><span data-stu-id="d4f89-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d4f89-126">Visual Studio 開発環境でこのコンパイラ オプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="d4f89-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="d4f89-127">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d4f89-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="d4f89-128">**[ビルド]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f89-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="d4f89-129">**警告レベル** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="d4f89-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="d4f89-130">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4f89-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f89-131">例</span><span class="sxs-lookup"><span data-stu-id="d4f89-131">Example</span></span>  
 <span data-ttu-id="d4f89-132">`in.cs` をコンパイルして、コンパイラにレベル 1 の警告のみを表示させます。</span><span class="sxs-lookup"><span data-stu-id="d4f89-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4f89-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4f89-133">See also</span></span>

- [<span data-ttu-id="d4f89-134">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="d4f89-134">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d4f89-135">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="d4f89-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
