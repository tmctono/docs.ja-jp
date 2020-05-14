---
title: フレンド アセンブリ参照 <reference> は無効です
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972389"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="4c8af-102">フレンド アセンブリ参照 \<reference> は使用できません</span><span class="sxs-lookup"><span data-stu-id="4c8af-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="4c8af-103">フレンド アセンブリ参照 \<reference> は使用できません。</span><span class="sxs-lookup"><span data-stu-id="4c8af-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="4c8af-104">厳密な名前の署名つきアセンブリはその InternalsVisibleTo 宣言内で公開キーを指定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4c8af-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="4c8af-105"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性コンストラクターに渡されたアセンブリ名は、厳密な名前のアセンブリを識別しますが、`PublicKey` 属性を含みません。</span><span class="sxs-lookup"><span data-stu-id="4c8af-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="4c8af-106">**エラー ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="4c8af-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c8af-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4c8af-107">To correct this error</span></span>  
  
1. <span data-ttu-id="4c8af-108">厳密な名前のフレンド アセンブリの公開キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="4c8af-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="4c8af-109">`PublicKey` 属性を使用して <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性コンストラクターに渡されるアセンブリ名の一部として、公開キーを含めます。</span><span class="sxs-lookup"><span data-stu-id="4c8af-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8af-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c8af-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="4c8af-111">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="4c8af-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
