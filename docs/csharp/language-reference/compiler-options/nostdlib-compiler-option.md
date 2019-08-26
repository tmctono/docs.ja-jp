---
title: -nostdlib (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 486539d7abdc3e65847a0bc0e228b1b20a2b2c37
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602688"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="634e9-102">-nostdlib (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="634e9-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="634e9-103">**-nostdlib** は、System 名前空間の全体を定義する mscorlib.dll がインポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="634e9-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="634e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="634e9-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="634e9-105">コメント</span><span class="sxs-lookup"><span data-stu-id="634e9-105">Remarks</span></span>

<span data-ttu-id="634e9-106">独自の System 名前空間およびオブジェクトを定義または作成する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="634e9-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="634e9-107">**/nostdlib** を指定しない場合、( **-nostdlib-** を指定したことと同じで) mscorlib.dll がプログラムにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="634e9-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="634e9-108">**-nostdlib** を指定することは、 **-nostdlib+** を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="634e9-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="634e9-109">このコンパイラ オプションを Visual Studio で使用するには</span><span class="sxs-lookup"><span data-stu-id="634e9-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="634e9-110">次の手順は、Visual Studio 2015 (および以前のバージョン) のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="634e9-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="634e9-111">**Do not reference mscorlib.dll** ビルド プロパティは、Visual Studio 2017 には存在しません。</span><span class="sxs-lookup"><span data-stu-id="634e9-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="634e9-112">プロジェクトの **[プロパティ]** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="634e9-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="634e9-113">**[ビルド]** プロパティ ページをクリックします。</span><span class="sxs-lookup"><span data-stu-id="634e9-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="634e9-114">**[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="634e9-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="634e9-115">**[mscorlib.dll を参照しない]** プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="634e9-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="634e9-116">このコンパイラ オプションをコードから設定するには</span><span class="sxs-lookup"><span data-stu-id="634e9-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="634e9-117">このコンパイラ オプションをプログラムで設定する方法については、「 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="634e9-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="634e9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="634e9-118">See also</span></span>

- [<span data-ttu-id="634e9-119">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="634e9-119">C# Compiler Options</span></span>](./index.md)
