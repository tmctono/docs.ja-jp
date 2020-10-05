---
title: フレンド アセンブリ参照 <reference> は無効です
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874090"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="b83bb-102">フレンド アセンブリ参照 \<reference> は無効です</span><span class="sxs-lookup"><span data-stu-id="b83bb-102">Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="b83bb-103">フレンド アセンブリ参照 \<reference> は無効です。</span><span class="sxs-lookup"><span data-stu-id="b83bb-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="b83bb-104">厳密な名前の署名つきアセンブリはその InternalsVisibleTo 宣言内で公開キーを指定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b83bb-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="b83bb-105"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性コンストラクターに渡されたアセンブリ名は、厳密な名前のアセンブリを識別しますが、`PublicKey` 属性を含みません。</span><span class="sxs-lookup"><span data-stu-id="b83bb-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="b83bb-106">**エラー ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="b83bb-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b83bb-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b83bb-107">To correct this error</span></span>  
  
1. <span data-ttu-id="b83bb-108">厳密な名前のフレンド アセンブリの公開キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="b83bb-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="b83bb-109">`PublicKey` 属性を使用して <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性コンストラクターに渡されるアセンブリ名の一部として、公開キーを含めます。</span><span class="sxs-lookup"><span data-stu-id="b83bb-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83bb-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b83bb-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="b83bb-111">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="b83bb-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
