---
title: My.Forms と My.WebServices が提供する既定のオブジェクト インスタンス
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330215"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="9f1f7-102">My.Forms および My.WebServices が提供する既定のオブジェクト インスタンス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f1f7-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="9f1f7-103">My.forms オブジェクトと[My](../../../visual-basic/language-reference/objects/my-webservices-object.md) Web Web サービス[オブジェクトは、](../../../visual-basic/language-reference/objects/my-forms-object.md)アプリケーションで使用されるフォーム、データソース、および XML Web サービスへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="9f1f7-104">これらの操作は、これらの各オブジェクトの*既定のインスタンス*のコレクションを提供することによって行います。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="9f1f7-105">既定のインスタンス</span><span class="sxs-lookup"><span data-stu-id="9f1f7-105">Default Instances</span></span>  

 <span data-ttu-id="9f1f7-106">既定のインスタンスは、ランタイムによって提供されるクラスのインスタンスであり、`Dim` および `New` ステートメントを使用して宣言およびインスタンス化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="9f1f7-107">次の例では、`Form1`と呼ばれる <xref:System.Windows.Forms.Form> クラスのインスタンスを宣言およびインスタンス化し、`My.Forms`を通じてこの <xref:System.Windows.Forms.Form> クラスの既定のインスタンスを取得できるようになった方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="9f1f7-108">`My.Forms` オブジェクトは、プロジェクトに存在するすべての `Form` クラスの既定のインスタンスのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="9f1f7-109">同様に、`My.WebServices` は、アプリケーションで参照を作成したすべての Web サービスに対して、プロキシクラスの既定のインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f1f7-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1f7-110">参照</span><span class="sxs-lookup"><span data-stu-id="9f1f7-110">See also</span></span>

- [<span data-ttu-id="9f1f7-111">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9f1f7-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="9f1f7-112">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9f1f7-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="9f1f7-113">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="9f1f7-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
