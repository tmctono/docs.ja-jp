---
title: '方法: XAML で特殊文字を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918443"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="3b634-102">方法: XAML で特殊文字を使用する</span><span class="sxs-lookup"><span data-stu-id="3b634-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="3b634-103">で[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]作成されたマークアップファイルは、自動的[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]に utf-8 ファイル形式で保存されます。つまり、アクセントマークなどのほとんどの特殊文字は正しくエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="3b634-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="3b634-104">ただし、一般的に使用される一連の特殊文字で、別の方法で処理されるものがあります。</span><span class="sxs-lookup"><span data-stu-id="3b634-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="3b634-105">これらの特殊文字は[!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] 、 [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)]エンコードの標準に従います。</span><span class="sxs-lookup"><span data-stu-id="3b634-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="3b634-106">この一連の特殊文字をエンコードするための構文を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3b634-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="3b634-107">文字</span><span class="sxs-lookup"><span data-stu-id="3b634-107">Character</span></span>|<span data-ttu-id="3b634-108">構文</span><span class="sxs-lookup"><span data-stu-id="3b634-108">Syntax</span></span>|<span data-ttu-id="3b634-109">説明</span><span class="sxs-lookup"><span data-stu-id="3b634-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="3b634-110">より小さい記号</span><span class="sxs-lookup"><span data-stu-id="3b634-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="3b634-111">より大きい記号</span><span class="sxs-lookup"><span data-stu-id="3b634-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="3b634-112">アンパサンド記号</span><span class="sxs-lookup"><span data-stu-id="3b634-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="3b634-113">"</span><span class="sxs-lookup"><span data-stu-id="3b634-113">"</span></span>|`&quot;`|<span data-ttu-id="3b634-114">二重引用符記号</span><span class="sxs-lookup"><span data-stu-id="3b634-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="3b634-115">Windows メモ帳などのテキストエディターを使用してマークアップファイルを作成する場合は、エンコードされ[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]た特殊文字を保持するために、ファイルを utf-8 ファイル形式で保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b634-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="3b634-116">次の例では、マークアップを作成するときにテキストで特殊文字を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3b634-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b634-117">例</span><span class="sxs-lookup"><span data-stu-id="3b634-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
