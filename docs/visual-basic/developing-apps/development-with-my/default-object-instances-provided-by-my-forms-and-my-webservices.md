---
title: My.Forms と My.WebServices が提供する既定のオブジェクト インスタンス
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 141f2f5f98499498d3c6732f7ae8d0abe6259ed9
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990239"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="deb5e-102">My.Forms および My.WebServices が提供する既定のオブジェクト インスタンス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="deb5e-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="deb5e-103">[My.Forms](../../language-reference/objects/my-forms-object.md) オブジェクトと [My.WebServices](../../language-reference/objects/my-webservices-object.md) オブジェクトを使用すると、アプリケーションで使用されるフォーム、データ ソース、および XML Web サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="deb5e-103">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="deb5e-104">アクセスは、各オブジェクトの "*既定のインスタンス*" のコレクションを通じて行われます。</span><span class="sxs-lookup"><span data-stu-id="deb5e-104">They provide access through collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="deb5e-105">既定のインスタンス</span><span class="sxs-lookup"><span data-stu-id="deb5e-105">Default Instances</span></span>  

 <span data-ttu-id="deb5e-106">既定のインスタンスは、ランタイムによって提供されるクラスのインスタンスであり、`Dim` および `New` ステートメントを使用して宣言およびインスタンス化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="deb5e-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="deb5e-107">次の例では、`Form1` という名前の <xref:System.Windows.Forms.Form> クラスのインスタンスを宣言およびインスタンス化し、`My.Forms` を使用してこの <xref:System.Windows.Forms.Form> クラスの既定のインスタンスを取得できるようになった方法を示します。</span><span class="sxs-lookup"><span data-stu-id="deb5e-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="deb5e-108">`My.Forms` オブジェクトにより、プロジェクト内に存在するすべての `Form` クラスの既定のインスタンスのコレクションが返されます。</span><span class="sxs-lookup"><span data-stu-id="deb5e-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="deb5e-109">同様に、`My.WebServices` により、アプリケーション内で参照を作成したすべての Web サービスに対して、プロキシ クラスの既定のインスタンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="deb5e-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb5e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="deb5e-110">See also</span></span>

- [<span data-ttu-id="deb5e-111">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="deb5e-111">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="deb5e-112">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="deb5e-112">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="deb5e-113">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="deb5e-113">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
