---
title: '方法: その他のアプリケーション (Visual Basic) とアセンブリを共有します。'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 520fe69d30ca55251ae7a19dcd7a1ea0c11e7bd5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302220"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="d070c-102">方法: その他のアプリケーション (Visual Basic) とアセンブリを共有します。</span><span class="sxs-lookup"><span data-stu-id="d070c-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="d070c-103">アセンブリはプライベートまたは共有にすることができます。既定では、ほとんどの単純なプログラムは、他のアプリケーションによって使われることを意図されていないので、プライベート アセンブリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d070c-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="d070c-104">他のアプリケーションとアセンブリを共有するには、[グローバル アセンブリ キャッシュ](../../../../framework/app-domains/gac.md) (GAC) にアセンブリを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d070c-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="d070c-105">アセンブリの共有</span><span class="sxs-lookup"><span data-stu-id="d070c-105">Sharing an assembly</span></span>  
  
1. <span data-ttu-id="d070c-106">アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d070c-106">Create your assembly.</span></span> <span data-ttu-id="d070c-107">詳しくは、「[アセンブリの作成](../../../../framework/app-domains/create-assemblies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d070c-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2. <span data-ttu-id="d070c-108">アセンブリに厳密な名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d070c-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="d070c-109">詳細については、「[方法 :厳密な名前でアセンブリに署名する](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d070c-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3. <span data-ttu-id="d070c-110">アセンブリにバージョン情報を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d070c-110">Assign version information to your assembly.</span></span> <span data-ttu-id="d070c-111">詳細については、「[アセンブリのバージョン管理](../../../../framework/app-domains/assembly-versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d070c-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4. <span data-ttu-id="d070c-112">グローバル アセンブリ キャッシュにアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d070c-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="d070c-113">詳細については、「[方法 :アセンブリをグローバル アセンブリ キャッシュにインストールする](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d070c-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5. <span data-ttu-id="d070c-114">他のアプリケーションからアセンブリに含まれる型にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d070c-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="d070c-115">詳細については、「[方法 :厳密な名前のアセンブリを参照する](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d070c-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d070c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d070c-116">See also</span></span>

- [<span data-ttu-id="d070c-117">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="d070c-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="d070c-118">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="d070c-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="d070c-119">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="d070c-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
