---
title: My.Resources と My.Settings による Rapid Application Development
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349264"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="b4ee1-102">My.Resources と My.Settings による Rapid Application Development (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4ee1-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="b4ee1-103">`My.Resources` オブジェクトは、アプリケーションのリソースへのアクセスを提供し、アプリケーションのリソースを動的に取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="b4ee1-104">リソースの取得</span><span class="sxs-lookup"><span data-stu-id="b4ee1-104">Retrieving Resources</span></span>  

 <span data-ttu-id="b4ee1-105">`My.Resources` オブジェクトを使用して、オーディオファイル、アイコン、画像、文字列などのさまざまなリソースを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="b4ee1-106">たとえば、アプリケーションのカルチャ固有のリソースファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="b4ee1-107">次の例では、フォームのアイコンを、アプリケーションのリソースファイルに格納されている `Form1Icon` という名前のアイコンに設定します。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="b4ee1-108">`My.Resources` オブジェクトは、グローバルリソースのみを公開します。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="b4ee1-109">フォームに関連付けられたリソースファイルへのアクセスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="b4ee1-110">フォームリソースには、フォームからアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="b4ee1-111">同様に、`My.Settings` オブジェクトを使用すると、アプリケーションの設定にアクセスして、アプリケーションのプロパティ設定やその他の情報を動的に格納および取得することができます。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="b4ee1-112">詳細については、「 [My.resources オブジェクト](../../../visual-basic/language-reference/objects/my-resources-object.md)」と「 [my.settings オブジェクト](../../../visual-basic/language-reference/objects/my-settings-object.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4ee1-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ee1-113">参照</span><span class="sxs-lookup"><span data-stu-id="b4ee1-113">See also</span></span>

- [<span data-ttu-id="b4ee1-114">My.Resources オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b4ee1-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="b4ee1-115">My.Settings オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b4ee1-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="b4ee1-116">Accessing Application Settings</span><span class="sxs-lookup"><span data-stu-id="b4ee1-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
