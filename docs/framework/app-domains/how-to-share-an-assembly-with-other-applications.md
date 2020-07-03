---
title: '方法: アセンブリを他のアプリケーションと共有する'
description: .NET でアセンブリを他のアプリケーションと共有する方法を参照します。 アセンブリはプライベート (既定) または共有にすることができます。 アセンブリを共有するには、アセンブリを GAC に配置します。
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 9cef25059968875f17ce5dc77b04c44a2f3945f6
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104649"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="c30bc-105">方法: アセンブリを他のアプリケーションと共有する</span><span class="sxs-lookup"><span data-stu-id="c30bc-105">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="c30bc-106">アセンブリはプライベートまたは共有にすることができます。既定では、ほとんどの単純なプログラムは、他のアプリケーションによって使われることを意図されていないので、プライベート アセンブリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c30bc-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="c30bc-107">他のアプリケーションとアセンブリを共有するには、[グローバル アセンブリ キャッシュ (GAC)](gac.md) にアセンブリを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="c30bc-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="c30bc-108">アセンブリを共有するには:</span><span class="sxs-lookup"><span data-stu-id="c30bc-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="c30bc-109">アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c30bc-109">Create your assembly.</span></span> <span data-ttu-id="c30bc-110">詳しくは、「[アセンブリを作成する](../../standard/assembly/create.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c30bc-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="c30bc-111">アセンブリに厳密な名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c30bc-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="c30bc-112">詳細については、「[方法:厳密な名前でアセンブリに署名する](../../standard/assembly/sign-strong-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30bc-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="c30bc-113">アセンブリにバージョン情報を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c30bc-113">Assign version information to your assembly.</span></span> <span data-ttu-id="c30bc-114">詳細については、「[アセンブリのバージョン管理](../../standard/assembly/versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30bc-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="c30bc-115">グローバル アセンブリ キャッシュにアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c30bc-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="c30bc-116">詳細については、「[方法:アセンブリをグローバル アセンブリ キャッシュにインストールする](install-assembly-into-gac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30bc-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="c30bc-117">他のアプリケーションからアセンブリに含まれる型にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c30bc-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="c30bc-118">詳細については、「[方法:厳密な名前のアセンブリを参照する](../../standard/assembly/reference-strong-named.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30bc-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30bc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c30bc-119">See also</span></span>

- [<span data-ttu-id="c30bc-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c30bc-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="c30bc-121">プログラミングの概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c30bc-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="c30bc-122">アセンブリを使用したプログラム</span><span class="sxs-lookup"><span data-stu-id="c30bc-122">Program with assemblies</span></span>](../../standard/assembly/index.md)
