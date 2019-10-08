---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002390"
---
# <a name="-baseaddress"></a><span data-ttu-id="5ac15-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="5ac15-102">-baseaddress</span></span>
<span data-ttu-id="5ac15-103">DLL を作成するときの既定のベースアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ac15-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac15-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ac15-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ac15-105">引数</span><span class="sxs-lookup"><span data-stu-id="5ac15-105">Arguments</span></span>  
  
|<span data-ttu-id="5ac15-106">項目</span><span class="sxs-lookup"><span data-stu-id="5ac15-106">Term</span></span>|<span data-ttu-id="5ac15-107">定義</span><span class="sxs-lookup"><span data-stu-id="5ac15-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="5ac15-108">必須。</span><span class="sxs-lookup"><span data-stu-id="5ac15-108">Required.</span></span> <span data-ttu-id="5ac15-109">DLL のベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="5ac15-109">The base address for the DLL.</span></span> <span data-ttu-id="5ac15-110">このアドレスは16進数として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ac15-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ac15-111">コメント</span><span class="sxs-lookup"><span data-stu-id="5ac15-111">Remarks</span></span>  
 <span data-ttu-id="5ac15-112">DLL の既定のベースアドレスは、.NET Framework によって設定されます。</span><span class="sxs-lookup"><span data-stu-id="5ac15-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="5ac15-113">このアドレスの下位ワードは丸められていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ac15-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="5ac15-114">たとえば、0x11110001 を指定すると、0x11110000 に丸められます。</span><span class="sxs-lookup"><span data-stu-id="5ac15-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="5ac15-115">DLL の署名プロセスを完了するには、厳密な名前付けツール (Sn.exe) の `–R` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ac15-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="5ac15-116">ターゲットが DLL でない場合、このオプションは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5ac15-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="5ac15-117">Visual Studio IDE で baseaddress を設定するには</span><span class="sxs-lookup"><span data-stu-id="5ac15-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="5ac15-118">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ac15-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5ac15-119">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ac15-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5ac15-120">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ac15-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5ac15-121">3. **[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ac15-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="5ac15-122">4。 **[DLL のベースアドレス:]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="5ac15-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="5ac15-123">**注:**     **Dll のベースアドレス:** box は、ターゲットが dll の場合を除き、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="5ac15-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ac15-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ac15-124">See also</span></span>

- [<span data-ttu-id="5ac15-125">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="5ac15-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5ac15-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ac15-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="5ac15-127">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="5ac15-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="5ac15-128">[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="5ac15-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
