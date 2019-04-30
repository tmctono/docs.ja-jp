---
title: My.Resources と My.Settings による Rapid Application Development (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4a9021af23200323397cc49fa1a44a0cc48b5a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014441"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="c8213-102">My.Resources と My.Settings による Rapid Application Development (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8213-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="c8213-103">`My.Resources`オブジェクトは、アプリケーションのリソースへのアクセスを提供し、アプリケーションのリソースを動的に取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c8213-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="c8213-104">リソースの取得</span><span class="sxs-lookup"><span data-stu-id="c8213-104">Retrieving Resources</span></span>  
 <span data-ttu-id="c8213-105">多数のオーディオ ファイル、アイコン、イメージ、および文字列などのリソースを使用して取得できる、`My.Resources`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c8213-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="c8213-106">たとえば、アプリケーションのカルチャ固有のリソース ファイルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8213-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="c8213-107">次の例では、フォームのアイコンを設定するという名前のアイコン`Form1Icon`アプリケーションのリソース ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="c8213-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="c8213-108">`My.Resources`オブジェクトはグローバル リソースのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8213-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="c8213-109">フォームに関連付けられているリソース ファイルへのアクセスは行いません。</span><span class="sxs-lookup"><span data-stu-id="c8213-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="c8213-110">フォームのフォーム リソースにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8213-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="c8213-111">同様に、`My.Settings`オブジェクトは、アプリケーションの設定へのアクセスを提供し、動的に格納し、プロパティの設定と、アプリケーションの他の情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c8213-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="c8213-112">詳細については、次を参照してください。 [My.Resources オブジェクト](../../../visual-basic/language-reference/objects/my-resources-object.md)と[My.Settings オブジェクト](../../../visual-basic/language-reference/objects/my-settings-object.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8213-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8213-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8213-113">See also</span></span>

- [<span data-ttu-id="c8213-114">My.Resources オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c8213-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="c8213-115">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c8213-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="c8213-116">アプリケーション設定へのアクセス</span><span class="sxs-lookup"><span data-stu-id="c8213-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
